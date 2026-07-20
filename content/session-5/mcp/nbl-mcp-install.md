---
type: install-doc
unit: mcp
session: 5
title: מסמך התקנה — NotebookLM MCP
target: Claude Code
---

# מסמך התקנה — NotebookLM MCP

## מה המסמך הזה

זה לא קובץ שלוחצים עליו. זה מסמך שנותנים לקלוד, וקלוד עושה את העבודה.
פותחים את Claude Code בתיקייה כלשהי במחשב, מדביקים לקלוד את הקישור למסמך הזה (או את התוכן שלו), ומבקשים ממנו: "תתקין לי לפי המסמך הזה". קלוד קורא את ההנחיות שלמטה, מריץ את מה שצריך, ומלווה אתכם בשלב ההתחברות עם חשבון Google.

החיבור נכנס ל-Claude Code — אותו מקום שבו תרוצו בכיתה ובהכנות הבאות. לכן ההתקנה כולה נעשית מתוך Claude Code, ולא ידנית.

---

## Instructions for Claude

Claude — read this section and carry it out step by step. After each step, briefly tell the user what happened, and if an action is needed from the user (for example, signing in through the browser) — stop and ask for it.

Goal: install and run the NotebookLM MCP server inside Claude Code, so that you have access to the user's notebooks.

The tool in question is the Python package `notebooklm-mcp-cli`. It installs two commands: `nlm` (a command-line tool for management and authentication) and `notebooklm-mcp` (the MCP server itself). Authentication with Google is done through `nlm login`, which opens a Chrome window where the user signs in with their own Google account — no API key and no credit card.

Before you start — briefly explain to the user what you understood and what you are about to do, and wait for approval to continue.

Proceed as follows:

1. Check prerequisites. Make sure Python (version 3.10 or higher) is installed. Check whether `uv` or `pipx` is available on the machine for installing global tools. If neither is present, install `uv` (the recommended way) and continue.

2. Install the package globally. The recommended way:

   ```
   uv tool install notebooklm-mcp-cli
   ```

   If `uv` is not available, use `pipx install notebooklm-mcp-cli`. After the installation, make sure the commands `nlm` and `notebooklm-mcp` are available on the PATH.

3. Register the MCP server with Claude Code:

   ```
   nlm setup add claude-code
   ```

   This adds the `notebooklm-mcp` server to Claude Code's MCP configuration.

4. Authenticate the user with Google. Run:

   ```
   nlm login
   ```

   A Chrome window will open. Stop here and tell the user explicitly, in Hebrew: "ייפתח לך חלון דפדפן — התחבר עם חשבון Google שאתה משתמש בו ל-NotebookLM, ואשר את ההרשאות." Wait for the user to finish before you continue.

5. Confirm that the authentication took hold:

   ```
   nlm login --check
   ```

   Then run a general diagnostic:

   ```
   nlm doctor
   ```

   If anything is marked as unhealthy in `doctor`, fix it according to what it indicates and repeat the step.

6. For the new MCP server to be picked up, you may need to refresh Claude Code's MCP connections (reloading the servers or restarting the session). If the server does not appear in the tools available to you after registration — ask the user to reopen Claude Code.

What not to invent: if a particular command fails in a way you do not understand, or the user is on a different operating system than these instructions assume — do not guess. Stop, explain to the user what you tried and what happened, and ask them to reach out to the course group with a screenshot.

---

## איך יודעים שהצליח

אחרי שקלוד סיים, בקשו ממנו לרשום את המחברות שלכם:

```text
רשום לי אילו מחברות יש לי ב-NotebookLM
```

או, אותו פרומפט באנגלית:

```text
List the notebooks I have in NotebookLM
```

אם החיבור חי, קלוד יזהה לבד שיש לו כלי חדש, יפנה אליו, ויחזיר רשימה אמיתית של המחברות מהחשבון שלכם. זהו — החיבור עובד.

אין לכם עדיין אף מחברת? זה תקין. בקשו מקלוד ליצור מחברת חדשה — גם זו בדיקה טובה באותה מידה.

---

## אם נתקעתם

| מה קרה | מה עושים |
|---|---|
| קלוד מדווח שהפקודה `nlm` או `notebooklm-mcp` לא נמצאה | ההתקנה לא הושלמה או שהנתיב לא התרענן. בקשו מקלוד לבדוק שוב את ההתקנה, ואם צריך — לפתוח מחדש את הטרמינל ולנסות שוב |
| חלון ההתחברות ל-Google לא נפתח או נתקע | בקשו מקלוד להריץ שוב `nlm login`; ודאו שאתם מחוברים לחשבון Google הנכון בדפדפן |
| מחפשים איפה להקליד מפתח API | אין מפתח — NotebookLM מתחבר עם חשבון Google בלבד. זה היופי שלו |
| קלוד לא רואה את הכלי אחרי ההתקנה | השרת נרשם אבל לא נטען. פתחו מחדש את Claude Code, וקלוד יזהה את החיבור בהפעלה |
| קלוד עונה בלי להשתמש בכלי | נסחו את הבקשה עם השם המפורש "ב-NotebookLM", וקלוד יפנה אל הכלי |
