---
type: install-doc
unit: mcp-engine
session: 5
title: מסמך בנייה — מנוע המדיה (MCP סביב Gemini)
target: Claude Code
---

# מסמך בנייה — מנוע המדיה (MCP סביב Gemini)

## מה המסמך הזה

זה לא קובץ שלוחצים עליו. זה מסמך שנותנים לקלוד, וקלוד עושה את העבודה.
פותחים את Claude Code בתיקיית-הפרויקט שלכם, מדביקים לקלוד את המסמך הזה (או את הקישור אליו), ומבקשים ממנו: "תבנה לי לפי המסמך הזה" (או באנגלית: "Build it for me according to this document"). קלוד קורא את ההנחיות שלמטה, כותב את כל הקוד בעצמו, ומלווה אתכם בשני הרגעים שדורשים אתכם — הדבקת המפתח בקובץ, ופתיחת Claude Code מחדש.

מה נבנה כאן: **מנוע-מדיה שלם** — שרת MCP מקומי שעוטף את Gemini ונותן לקלוד שישה כלים חדשים: תמלול, ניתוח, תמונות, וידאו, דיבור ומוזיקה. זה המנוע שכל שלושת העולמות של השיעור — זומי, טוקי ופיקסי — רוכבים עליו. בונים אותו פעם אחת, והוא משרת הכול.

המפתח שהמנוע צריך הוא מפתח ה-Gemini שיצרתם בהכנת-הבית הראשונה, והוא שמור אצלכם ב-Bitwarden. המפתח הוא סוד, בדיוק כמו סיסמה — ולכן חוק אחד מלווה את כל הבנייה: **את המפתח מדביקים רק בקובץ שקלוד יפתח לכם, אף פעם לא בצ'אט.** מה שמודבק בצ'אט נשלח ונשמר בשיחה; מה שמודבק בקובץ נשאר במחשב שלכם.

עוד דבר אחד לפני שמתחילים: החלק שכתוב באנגלית למטה מיועד לקלוד, לא לכם. אתם קוראים עברית — קלוד מבצע אנגלית.

---

## מה המנוע יודע לעשות

| כלי | מה הוא עושה | כמה עולה שימוש |
|---|---|---|
| transcribe | מתמלל קובץ אודיו, כולל עברית | ‏~$0.003 לדקת-אודיו |
| analyze | מנתח או מסכם טקסט | זניח |
| generate_image | מייצר תמונה (‏Nano Banana 2) | ‏~$0.067 לתמונת-1K |
| generate_video | מייצר וידאו — ‏Veo 3.1 Lite כברירת-מחדל, ‏Omni למי שרוצה | קליפ-8-שניות ≈ ‏$0.40 |
| generate_speech | מקריא טקסט בקול, כולל עברית | סנטים בודדים לקטע |
| generate_music | מייצר קליפ-מוזיקה של 30 שניות (‏Lyria 3) | ‏$0.04 לקליפ |

ניסיון מלא של תמונה + וידאו + דיבור + מוזיקה עולה בערך חצי דולר. ה-15$ שטענתם בהכנה מכסים את כל תרגילי הקורס בשפע.

---

## Instructions for Claude

Claude — read this whole section before doing anything, then execute it step by step. After each step, tell the user briefly what happened. When a step requires a user action (pasting the key, reopening Claude Code) — stop and ask for it. The user-facing conversation is in Hebrew; these instructions are in English for you.

Goal: build a local Python MCP server named `gemini-engine` that wraps the Gemini API with six media tools, and register it in Claude Code so it is available in every future session.

Secrets rule (mandatory): the user's Gemini API key must NEVER pass through this chat. You do not ask for it, you do not read it back, you do not print the contents of `.env` at any point. The user pastes the key into the `.env` file themselves. If the user pastes the key into the chat by mistake — do not repeat it in any form, tell them to rotate it (create a new key in Google AI Studio, delete the old one, update Bitwarden), and continue with the new key.

Before you start — explain to the user in Hebrew, briefly, what you understood and what you are about to do, and wait for their approval.

### Step 1 — Preconditions

Check that Python 3.10+ is installed (`python --version`). It was installed in home-prep unit 5.5 with "Add to PATH" checked. If Python is missing — stop and tell the user to complete that unit first.

Check for `uv` (`uv --version`). If it is missing, install it with `pip install uv` and verify it is now available. If that fails, use the official installer: `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`, then have the user open a new terminal if needed.

### Step 2 — Scaffold the project

Inside the user's current project folder, create a subfolder named `gemini-engine` and initialize it:

```
uv init gemini-engine
cd gemini-engine
uv add fastmcp google-genai python-dotenv
```

### Step 3 — Write the server

Create `server.py` inside `gemini-engine` with EXACTLY the following content. Do not rewrite, "improve", or substitute model IDs — every model ID below was verified against ai.google.dev in July 2026. If the API later rejects a model ID, stop and report it; do not invent a replacement.

```python
import base64
import os
import time
import wave
from pathlib import Path

from dotenv import load_dotenv
from fastmcp import FastMCP

# override=True makes the .env file next to this server the single source of
# truth for the key, even if a GEMINI_API_KEY happens to exist in the machine
# environment.
load_dotenv(Path(__file__).parent / ".env", override=True)

mcp = FastMCP("gemini-engine")

PLACEHOLDER = "PASTE-YOUR-KEY-HERE"


def _client():
    key = os.environ.get("GEMINI_API_KEY", "")
    if not key or key == PLACEHOLDER:
        raise RuntimeError(
            "GEMINI_API_KEY is missing. Open the .env file next to server.py and "
            "replace the ENTIRE placeholder text after '=' with your key from Bitwarden."
        )
    from google import genai

    return genai.Client(api_key=key)


@mcp.tool
def transcribe(audio_path: str, language: str = "Hebrew") -> str:
    """Transcribe an audio file to text with Gemini. Cost: about $0.003 per audio minute."""
    client = _client()
    audio = client.files.upload(file=audio_path)
    response = client.models.generate_content(
        model="gemini-3.5-flash",
        contents=[
            f"Transcribe this audio in {language}. Return only the transcript text.",
            audio,
        ],
    )
    return response.text


@mcp.tool
def analyze(text: str, instruction: str = "Summarize the following text.") -> str:
    """Analyze or summarize text with Gemini Flash. Cost: negligible."""
    client = _client()
    response = client.models.generate_content(
        model="gemini-3.5-flash",
        contents=f"{instruction}\n\n{text}",
    )
    return response.text


@mcp.tool
def generate_image(
    prompt: str,
    output_path: str,
    resolution: str = "1K",
    aspect_ratio: str = "1:1",
    input_image_path: str = "",
) -> str:
    """Generate an image with Nano Banana 2 and save it as JPEG.
    resolution: 512px / 1K / 2K / 4K. Cost: about $0.067 per 1K image.
    optional input_image_path = a local image to edit / transform (image-to-image)."""
    client = _client()
    # Text-only by default. When a source image is given, the input becomes a
    # list of a text part + an image part (base64) so the model edits it. The
    # mime type is inferred from the extension; PNG and JPEG are both accepted.
    if input_image_path:
        with open(input_image_path, "rb") as src:
            image_bytes = src.read()
        mime = "image/png" if input_image_path.lower().endswith(".png") else "image/jpeg"
        model_input = [
            {"type": "text", "text": prompt},
            {
                "type": "image",
                "data": base64.b64encode(image_bytes).decode("utf-8"),
                "mime_type": mime,
            },
        ]
    else:
        model_input = prompt
    interaction = client.interactions.create(
        model="gemini-3.1-flash-image",
        input=model_input,
        response_format={
            # The engine standardizes on JPEG (verified in a live run 2026-07-21);
            # it never returns a PNG or a transparent background — ask for .jpg.
            "type": "image",
            "mime_type": "image/jpeg",
            "aspect_ratio": aspect_ratio,
            "image_size": resolution,
        },
    )
    # The bytes are always JPEG, so the file gets a .jpg name even when the
    # caller asked for another extension — a mislabelled extension breaks some viewers.
    saved_path = Path(output_path).with_suffix(".jpg")
    with open(saved_path, "wb") as f:
        f.write(base64.b64decode(interaction.output_image.data))
    return f"Image saved to {saved_path}"


@mcp.tool
def generate_video(
    prompt: str,
    output_path: str,
    model: str = "veo-lite",
    duration_seconds: int = 8,
    resolution: str = "720p",
    aspect_ratio: str = "16:9",
    image_path: str = "",
) -> str:
    """Generate a video and save it as MP4. model: 'veo-lite' (default,
    $0.05/second at 720p) or 'omni' (Gemini Omni Flash, about $0.10/second).
    Veo generation is asynchronous and can take a few minutes.
    optional image_path = local first-frame anchor image (veo path only)."""
    client = _client()
    if model == "omni":
        # The first-frame anchor is verified on the veo path only, not on omni.
        if image_path:
            raise RuntimeError(
                "image anchor is not supported on omni yet — "
                "leave image_path empty when model='omni'."
            )
        interaction = client.interactions.create(
            model="gemini-omni-flash-preview",
            input=prompt,
        )
        with open(output_path, "wb") as f:
            f.write(base64.b64decode(interaction.output_video.data))
    else:
        from google.genai import types

        # Optional first-frame anchor: a local keyframe passed as a top-level
        # image= argument (NOT inside the config). It conditions the motion; the
        # prompt must still describe it. Empty image_path = today's text-only run.
        image = types.Image.from_file(location=image_path) if image_path else None
        operation = client.models.generate_videos(
            model="veo-3.1-lite-generate-preview",
            prompt=prompt,
            image=image,
            config=types.GenerateVideosConfig(
                aspect_ratio=aspect_ratio,
                resolution=resolution,
                duration_seconds=str(duration_seconds),
            ),
        )
        while not operation.done:
            time.sleep(10)
            operation = client.operations.get(operation)
        generated = operation.response.generated_videos[0]
        client.files.download(file=generated.video)
        generated.video.save(output_path)
    return f"Video saved to {output_path}"


@mcp.tool
def generate_speech(text: str, output_path: str, voice: str = "Kore") -> str:
    """Read text aloud (Hebrew supported) with Gemini TTS and save it as WAV.
    Cost: a few cents per short passage."""
    client = _client()
    interaction = client.interactions.create(
        model="gemini-3.1-flash-tts-preview",
        input=text,
        response_format={"type": "audio"},
        generation_config={"speech_config": [{"voice": voice}]},
    )
    pcm = base64.b64decode(interaction.output_audio.data)
    with wave.open(output_path, "wb") as wf:
        wf.setnchannels(1)
        wf.setsampwidth(2)
        wf.setframerate(24000)
        wf.writeframes(pcm)
    return f"Audio saved to {output_path}"


@mcp.tool
def generate_music(prompt: str, output_path: str, length: str = "clip") -> str:
    """Generate music with Lyria 3 and save it as MP3. length: 'clip'
    (30 seconds, $0.04) or 'song' (full song, $0.08)."""
    client = _client()
    model_id = "lyria-3-clip-preview" if length == "clip" else "lyria-3-pro-preview"
    interaction = client.interactions.create(model=model_id, input=prompt)
    with open(output_path, "wb") as f:
        f.write(base64.b64decode(interaction.output_audio.data))
    return f"Music saved to {output_path}"


if __name__ == "__main__":
    mcp.run()
```

Also create `check_tools.py` inside `gemini-engine` with EXACTLY this content (it is the free smoke test):

```python
import asyncio

from fastmcp import Client
from server import mcp


async def main():
    async with Client(mcp) as client:
        tools = await client.list_tools()
        print("TOOLS:", sorted(t.name for t in tools))


asyncio.run(main())
```

### Step 4 — The key (user action, stop point)

Create a file named `.env` inside `gemini-engine` with exactly this single line:

```
GEMINI_API_KEY=PASTE-YOUR-KEY-HERE
```

Open the file for the user (for example `notepad .env`), then STOP and tell the user, in Hebrew: "פתחתי לך את הקובץ. שלוף את מפתח ה-Gemini מ-Bitwarden והדבק אותו במקום הכיתוב PASTE-YOUR-KEY-HERE — מחליפים את **כל** הטקסט הזה, את כל המילים כולל המקפים, כך שאחרי הסימן = נשאר רק המפתח עצמו. בלי מירכאות, בלי רווחים. שמור וסגור, ותגיד לי כשסיימת." Wait for the user's confirmation. Never open or print `.env` after this point.

### Step 5 — Free smoke test (costs nothing)

Run:

```
uv run python check_tools.py
```

Expected output — a single line listing exactly these six tools:

```
TOOLS: ['analyze', 'generate_image', 'generate_music', 'generate_speech', 'generate_video', 'transcribe']
```

If the list is different or the script fails — fix the scaffold before moving on. This test does not touch the API and costs nothing.

### Step 6 — Register the engine in Claude Code

Register the server at user scope so it is available in every project:

```
claude mcp add gemini-engine -s user -- uv run --directory <ABSOLUTE-PATH-TO-GEMINI-ENGINE-FOLDER> python server.py
```

Replace `<ABSOLUTE-PATH-TO-GEMINI-ENGINE-FOLDER>` with the real absolute path of the `gemini-engine` folder — the replacement swallows the WHOLE token, including the angle brackets `<` and `>`; no angle bracket may remain in the final command. You know the path because you created the folder; run the command yourself (it contains no secret).

Then verify the registration:

```
claude mcp list
```

`gemini-engine` must appear in the list and connect successfully. If it appears twice or shows "Failed to connect" — see the troubleshooting table below.

### Step 7 — The restart moment (user action, stop point)

Tell the user, in Hebrew: the new engine will be picked up only in a fresh session — close Claude Code completely and open it again in the same folder. This is an explicit step, not an optional one. After reopening, the six tools of `gemini-engine` should be visible to Claude.

### What not to invent

If a command fails in a way you do not understand, if the key is rejected, if a model ID is rejected by the API, or if the user is on an operating system other than Windows — do not guess and do not invent a command, endpoint, or model name. Stop, explain to the user what you tried and what happened, and ask them to post a screenshot in the course group.

---

## איך יודעים שהצליח

### בדיקה ראשונה — חינם

אחרי שסגרתם ופתחתם את Claude Code מחדש, שאלו את קלוד:

```text
אילו כלים יש לך מהמנוע gemini-engine?
```

או, אותו פרומפט באנגלית:

```text
What tools do you have from the gemini-engine server?
```

אם החיבור חי, קלוד ימנה את ששת הכלים: תמלול, ניתוח, תמונה, וידאו, דיבור ומוזיקה. הבדיקה הזאת לא עולה כלום.

### בדיקה שנייה — חיה וזולה

עכשיו מריצים קריאה אמיתית אחת. קודם ניתוח (עולה פחות מעשירית סנט):

```text
Use the analyze tool on this sentence: "The engine is alive." Ask it to reply in one short sentence.
```

ואז תמונה אחת (עולה בערך $0.067):

```text
Use the generate_image tool to create a small test image of a golden star on a purple background, and save it as test-star.jpg in the current folder.
```

נפתח קובץ תמונה בתיקייה? המנוע שלכם חי, מקצה לקצה. משלב זה כל שימוש בכלי-מדיה עולה כסף אמיתי — הסכומים בטבלה למעלה.

---

## אם נתקעתם

| מה קרה | מה עושים |
|---|---|
| קלוד מדווח ש-Python לא נמצא | כנראה לא סומנה תיבת ה-PATH בהתקנה. חוזרים ליחידת ההתקנות של ההכנה (צעד Python) ומתקינים מחדש עם הסימון |
| קלוד מדווח ש-uv לא נמצא גם אחרי ההתקנה | סוגרים ופותחים את הטרמינל (או את Claude Code) — הנתיב מתרענן — ומנסים שוב |
| המפתח נדחה או שמתקבלת שגיאת הרשאה | בודקים שהדבקתם את המפתח הנכון מ-Bitwarden, ושה-billing פעיל עם הקרדיט שטענתם בהכנה הראשונה. מפתח בלי billing מקבל אפס שימוש בכלי-המדיה |
| שגיאה שאומרת שהמפתח חסר, למרות שהדבקתם | פותחים את הקובץ ‎.env ובודקים שלא נשאר שום שריד מהכיתוב PASTE-YOUR-KEY-HERE — מחליפים את כל הטקסט הזה, לא מוסיפים לידו. אחרי הסימן = צריך להופיע רק המפתח, בלי מירכאות ובלי רווחים |
| הדבקתם בטעות את המפתח בצ'אט | מחליפים אותו: יוצרים מפתח חדש ב-Google AI Studio, מוחקים את הישן, מעדכנים את הרשומה ב-Bitwarden, ומדביקים את החדש בקובץ ‎.env |
| הכלים לא מופיעים אחרי הרישום | השרת נרשם אבל לא נטען. סוגרים לגמרי את Claude Code ופותחים מחדש — קלוד יזהה את החיבור בהפעלה. אפשר לבדוק עם claude mcp list שהשרת רשום |
| השרת מופיע פעמיים או מסומן Failed to connect | נשארה רשומה ישנה מניסיון קודם. מריצים claude mcp list, מוחקים את הרשומה השגויה עם claude mcp remove gemini-engine -s local (או ‎-s user, לפי מה שהאבחון מציע) ורושמים מחדש |
| יצירת וידאו נתקעת דקות ארוכות | זה תקין — Veo עובד ברקע וקלוד בודק את הסטטוס כל כמה שניות. קליפ יכול לקחת כמה דקות |
| נגמר הקרדיט | בודקים את היתרה ב-Google AI Studio תחת Billing. ה-15$ מההכנה מכסים את כל תרגילי הקורס — אם נגמר, טוענים סכום קטן נוסף |
| קלוד עונה בלי להשתמש בכלי | נסחו את הבקשה עם שם הכלי המפורש, למשל "עם הכלי generate_image", וקלוד יפנה אל המנוע |
