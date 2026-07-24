---
type: skill-instructions
unit: brand-skill
session: 5
title: מסמך הוראות — סקיל המותג
target: Banay (Claude Code)
---

# מסמך הוראות — סקיל המותג

## מה המסמך הזה

זה לא סקיל מוכן, וזה בכוונה: הסקיל הזה חייב להיות אישי — הלוגו שלכם, הצבעים שלכם, הקול שלכם. לכן אתם לא מקבלים אותו מאיתנו; אתם מקבלים את המסמך הזה, ומוסרים אותו לבנאי — הסוכן בונה-הסוכנים-והסקילים שבניתם בשיעור 2. בנאי קורא את ההוראות, מחפש את חומרי המותג שכבר יש לכם בתיקיית-הפרויקט, ובונה מהם סקיל שהוא ארט-דיירקטור אישי שלכם: מעכשיו, כל פעם שתבקשו תמונה, סרטון או קריינות — הסקיל כבר מכיר את העיצוב שלכם, ודואג שהתוצאה תצא על-המותג.

מה מקבלים בסוף: סקיל בתיקיית-הפרויקט שמחזיק את כל הידע העיצובי שלכם, ויודע להתאים את עצמו לבקשה — ביקשתם פרומפט, הוא מנסח פרומפט מלא ומדויק; ביקשתם תמונה או מדיה אחרת, הוא מפעיל ישירות את כלי המנוע שבניתם בכיתה.

## איך משתמשים במסמך

1. פותחים את Claude Code בתיקיית-הפרויקט שלכם — אותה תיקייה שבה יושבים הלוגו, קובץ DESIGN.md וחומרי המותג משיעורים 3 ו-4.
2. מעירים את בנאי: מדביקים לקלוד את ה-system prompt של בנאי (הוא שמור אצלכם בפרויקט "בניית מטא-סוכן" משיעור 2, בהוראות של הפרויקט).
3. נותנים לבנאי את המסמך הזה — מדביקים את הקישור אליו או את התוכן שלו — ומבקשים:

```text
בנאי — תבנה לי את סקיל המותג לפי מסמך ההוראות הזה. תסביר מה הבנת ותחכה לאישור שלי לפני שאתה בונה.
```

או, אותו פרומפט באנגלית:

```text
Banay — build my brand skill from this instructions document. Explain what you understood and wait for my approval before you build.
```

בנאי יעבוד לפי החלק האנגלי שלמטה: יחפש את החומרים בתיקייה, ישאל אתכם רק על מה שחסר, ויבנה את הסקיל.

**אין לכם את בנאי זמין בתוך Claude Code?** אולי בניתם אותו בשיחה אחרת, או שהוא לא מותקן אצלכם כאן. במקרה כזה — מביאים את הוראות בנאי לתוך השיחה הנוכחית כאן ב-Claude Code, ומבקשים מקלוד להפוך את בנאי לסקיל גלובלי. כך בנאי נשמר אצלכם בתוך Claude Code ויהיה זמין בכל פרויקט מעכשיו, לא רק בשיחה הזאת. הפרומפט:

```text
קלוד — למטה הוראות בנאי, הסוכן בונה-הסקילים שבניתי בשיעור 2. תהפוך את בנאי לסקיל גלובלי ב-Claude Code, שיהיה זמין לי בכל פרויקט. [כאן מדביקים את הוראות בנאי]
```

או, אותו פרומפט באנגלית:

```text
Claude — below are Banay's instructions, the skill-building agent I built in session 2. Turn Banay into a global skill in Claude Code so it's available to me in every project. [paste Banay's instructions here]
```

---

## Instructions for Banay

Banay — you are building this student's personal brand skill inside Claude Code, in this project folder. Read this whole section before you start, then explain what you understood and wait for the student's approval before you build anything.

What you are building: a **personal art director** skill. It holds all of the student's brand and design knowledge as reference files, and adapts to whatever the student asks for — asked for a prompt, it composes a complete on-brand media prompt; asked for an image, video, or speech, it invokes the media tools of the student's Gemini MCP engine directly. The student built that engine in class; it is registered in Claude Code as the MCP server `gemini-engine`.

### Phase 1 — Gather the brand from this project folder

Search the project folder and collect the brand, in this order:

1. **Logo** — image or SVG files (`*.svg`, `*.png`, `*.jpg`). Record the exact file paths.
2. **Design system** — `DESIGN.md` at the project root (the student built it in the screens preparation unit). Also any tokens, colors, or fonts files.
3. **Brand voice and characterization** — the BUILD YOUR BRAND material from session 3, if present in the folder.
4. **Design knowledge base** — the design research the student ran after session 4, if present.
5. **Liked examples** — any reference images or notes the student saved about styles they like.

From these, extract concrete values — numbers over adjectives: exact colors as hex (by role: primary, background, accent, text), font family names, spacing and corner style, tone words for the brand voice, the logo file path, and whether the student's content is Hebrew and right-to-left.

**Duplicate the student's exact values into the skill; never summarize, re-word, or invent a brand.** The student's folder is messy — extract the real values from it, but do not fill a gap with a plausible-sounding invention (that is Phase 2's job: ask). This one line is the whole point of the gather phase: a brand that gets re-expressed in your own words is no longer the student's brand.

There are only two legal ways to move a gathered value into the skill, and no third:

1. **Point at the source file and inject verbatim** — when a value already lives in a file the skill can read at runtime (the logo path, `DESIGN.md`), point the skill at that source and inject the exact value; do not transcribe it into new prose.
2. **Copy into `references/`, byte-faithful, with a diff check** — when a value must be copied into the skill's own reference files, copy it as-found and confirm every value survived the copy unchanged.

Never a summarizing copy — reading the brand and re-describing it in your own words. A summarizing copy silently drops constraints, and a dropped constraint is a value the skill will never know it lost.

### Phase 2 — When something is missing, ask; never invent

If a key value is not in the files — an exact hex color, a font name, the logo file — ask the student for it, **one short question at a time**. Do not invent or guess a brand value, ever. Do not ask about anything you already found in the files.

### Phase 3 — The skill itself

Build the skill as a skill folder in this project, the way you build Claude Code skills: a thin `SKILL.md` with a name, a clear description of when to trigger (any request for media, a visual, an image, a video, speech, or an on-brand prompt), and a `references/` folder holding everything you gathered in Phase 1 — the hex colors, fonts, logo path, tone, style notes, and the RTL default. Those gathered references are the skill's single reference-of-truth: the skill reads them at runtime and everything it composes measures against them; the brand lives there as-found, never paraphrased into new prose in the `SKILL.md` body. The references are the point: the skill already knows the design, so the student never has to re-explain it.

The skill's behavior adapts to the request:

- **Asked for a prompt** ("write me a prompt for a post image about X") — compose a complete, ready-to-run on-brand prompt: exact hex colors, font names, style descriptors, the logo when the medium calls for it, and an RTL note when the content is Hebrew. Return the prompt.
- **Asked for media** ("make me an image for a post about X") — compose that same on-brand prompt internally, then invoke the matching `gemini-engine` tool directly: `generate_image` for images, `generate_video` for video, `generate_speech` for speech, `generate_music` for music. Return the result to the student.
- If the `gemini-engine` tools are not available in the session, do not fail — return the ready prompt instead, and tell the student the engine is not connected.

When composing any prompt, the gathered hex and font values go in as **literal strings** — `#1A1A1A`, `Rubik` — never re-described. The no-replace rule is narrow: never **replace** a value with a word ("warm charcoal" in place of the hex, "a friendly font" in place of the family name). A short descriptor **may accompany** a value — a hex followed by a color word — but the literal value always goes in. The ban is on substitution, not on description.

Tool names above follow the engine's contract; if the connected server exposes different tool names, use the actual names you discover on `gemini-engine` — do not invent tool names.

**Right tool for precision — never spend `generate_image` on a mark, type, or exact geometry.** A generated image only approximates, at cost, and can never be trusted for an exact mark/logo, readable typography, or a strict geometric composition — code builds those exactly and for free. Generation earns its cost **only on organic imagery code cannot make** — scenes, characters, backgrounds. So when the student asks for a logo, a title card, or anything that must be color-exact or letter-exact, the skill's answer is code, not a paid render.

<!-- sync note (maintainers): tool names + server name + $0.067 image cost + JPEG return type reconciled against _kits/mcp-engine/engine-contract.md (verified 2026-07-21). -->

### Phase 4 — Test contract: one on-brand image

After the skill is built, run one defined sample as proof of life: through the skill, generate **one** image — a cover image for a post about the student's own project — using `generate_image`. The engine returns a saved `.jpg`; it never returns a transparent background. Before running, tell the student this is a paid call (about $0.067 for one image) and wait for their go-ahead. Then check the result together with the student against a standard a generated image can actually meet: the style matches the references, and the colors are recognizably the brand's — the right family of colors, close, not exact. Do not hold the render to exact hex: a generated JPEG shifts a flat fill a few units per channel on compression alone, so exact-hex output belongs to code-built assets (logo, cards, typography), never to a generated one. One good image = the skill is alive.

---

## איך יודעים שהצליח

אחרי שבנאי סיים, מבקשים מהסקיל את התמונה הראשונה:

```text
דרך סקיל המותג — תייצר לי תמונת פתיחה לפוסט על הפרויקט שלי
```

או, אותו פרומפט באנגלית:

```text
Through my brand skill — generate a cover image for a post about my project
```

אם הסקיל חי, קלוד יזהה את הבקשה, ישלוף את הצבעים והסגנון מהסקיל בלי לשאול אתכם שוב, ויחזיר תמונה שנראית שלכם. שימו לב שזו קריאה בתשלום — תמונה אחת עולה בערך 7 סנט מהקרדיט שטענתם בהכנה.

רוצים בדיקה חינמית קודם? בקשו רק פרומפט: "דרך סקיל המותג — תנסח לי פרומפט לתמונת פוסט". אם הפרומפט שחוזר כולל את צבעי ה-hex שלכם ואת הגופנים שלכם — הסקיל מכיר אתכם.

---

## אם נתקעתם

| מה קרה | מה עושים |
|---|---|
| לא זוכרים איפה בנאי | ההוראות שלו שמורות בפרויקט "בניית מטא-סוכן" משיעור 2, בהוראות של הפרויקט. מעתיקים אותן משם — והכי טוב: הופכים את בנאי לסקיל גלובלי עם הפרומפט שבסעיף "איך משתמשים במסמך" למעלה, וכך הוא זמין לכם בכל פרויקט מעכשיו |
| בנאי שואל על צבע או גופן שאין לכם | עונים שאלה-שאלה. אין לכם DESIGN.md בכלל? חוזרים להכנת המסכים של השיעור הזה — שם בונים אותו בפרומפט מוכן |
| הסקיל לא קופץ כשמבקשים תמונה | מנסחים את הבקשה עם השם המפורש: "דרך סקיל המותג". קלוד יפנה אל הסקיל |
| הפקת התמונה נכשלת, או שכלי gemini-engine לא מופיעים | המנוע לא מחובר. חוזרים למסמך-הבנייה של המנוע מהכיתה, בודקים עם claude mcp list שהשרת gemini-engine רשום, וסוגרים ופותחים את קלוד קוד |
| התמונה יצאה בצבעים קרובים אבל לא מדויקים | זה נורמלי וצפוי. ייצור לעולם לא מחזיר את צבע-המותג המדויק — סטייה קטנה בגוון היא חלק מהשיטה, לא תקלה. אם הסגנון או התחושה יצאו לא נכון, מבקשים מקלוד להראות מה כתוב בקובצי ה-references, מוודאים שערכי ה-hex והגופנים נכונים, ומייצרים שוב. לנכסים שחייבים צבע מדויק — לוגו, כרטיסים, טיפוגרפיה — הכלי הנכון הוא קוד, לא ייצור |
| בנאי בונה משהו אחר ממה שביקשתם | עוצרים אותו ומחזירים אותו למסמך: "תבנה לפי מסמך ההוראות, שלב-שלב, ותסביר מה הבנת לפני שאתה ממשיך" |
