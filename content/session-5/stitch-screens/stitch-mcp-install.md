---
type: install-doc
unit: stitch-screens
session: 5
title: מסמך התקנה — Stitch MCP
target: Claude Code
---

# מסמך התקנה — Stitch MCP

## מה המסמך הזה

זה לא קובץ שלוחצים עליו. זה מסמך שנותנים לקלוד, וקלוד עושה את העבודה.
פותחים את Claude Code בתיקיית-הפרויקט שלכם, מדביקים לקלוד את הקישור למסמך הזה (או את התוכן שלו), ומבקשים ממנו: "תתקין לי לפי המסמך הזה". קלוד קורא את ההנחיות שלמטה, בודק שהכול מוכן, ומלווה אתכם ברגע היחיד שדורש אתכם — הרצת פקודת-החיבור עם המפתח, בטרמינל שלכם.

שימו לב להבדל מ-NotebookLM: שם ההתחברות הייתה עם חשבון Google בלבד, בלי שום סוד. כאן Stitch עובד עם מפתח API — והמפתח הוא סוד, בדיוק כמו סיסמה. לכן חוק אחד מלווה את כל ההתקנה: **את המפתח מדביקים רק בטרמינל, אף פעם לא בצ'אט.** מה שמודבק בצ'אט נשלח ונשמר בשיחה; מה שמודבק בטרמינל נשאר במחשב שלכם. את המפתח כבר יצרתם ושמרתם ב-Bitwarden בצעד הקודם של היחידה — כל מה שנשאר הוא לשלוף אותו מהכספת ברגע הנכון.

החיבור נכנס ל-Claude Code — אותו מקום שבו תרוצו בכיתה ובהכנות הבאות. לכן ההתקנה כולה נעשית מתוך Claude Code, ולא ידנית.

---

## Instructions for Claude

Claude — read this section and carry it out step by step. After each step, briefly tell the user what happened, and if an action is needed from the user (for example, running the connection command in the terminal) — stop and ask for it.

Goal: install and run the Google Stitch MCP server inside Claude Code, so that you have access to the user's Stitch projects and screens, and can pull images, code, and a design system from them.

The tool in question is the official npm package `@_davideast/stitch-mcp`. It runs through npx (and therefore requires Node, which was already installed in an earlier step of the unit) and brings up a local proxy that talks to Stitch. Authentication is done with a Stitch API key, injected as an environment variable named `STITCH_API_KEY`. The key is the user's secret: it is stored in their Bitwarden, and the user pastes it directly into their own terminal — not into the chat. You do not generate the key, you do not ask for it, and you do not write it down anywhere.

Binding rule: never ask the user to paste the key into the conversation. If the user pasted it into the chat by mistake — do not repeat it in text, tell them to rotate it (create a new key in Stitch settings and delete the old one), and continue with the new one.

Before you start — briefly explain to the user what you understood and what you are about to do, and wait for approval to continue.

Proceed as follows:

1. Check prerequisites. Make sure Node is installed and the `npx` command is available. If Node is missing — stop and tell the user it must be installed first (this was done in the first step of the unit, nodejs.org, LTS version). Without Node you cannot continue.

2. Show the user the connection command and guide them to run it themselves. Tell them explicitly, in Hebrew: "פתח חלון טרמינל — לא את השיחה איתי. שלוף את מפתח ה-API של Stitch מ-Bitwarden — הרשומה ששמרת בצעד הקודם — והחלף בפקודה את `<the-key-from-the-vault>` במפתח. מוחקים את `<the-key-from-the-vault>` כולו, כולל הסוגריים המשולשים `<` `>`, ובמקומו נשאר רק המפתח — שום `<` או `>` לא נשאר בפקודה הסופית. ואז הרץ אותה." The command:

   ```
   claude mcp add stitch -s user -e STITCH_API_KEY=<the-key-from-the-vault> -- npx -y @_davideast/stitch-mcp proxy
   ```

   The `-s user` flag saves the connection globally, for all projects. Wait for the user to confirm that the command ran and finished without an error, and only then continue.

   There is also an alternative guided way — a wizard the user runs themselves in the same terminal, selecting Claude Code in it and entering the key (there too — in the terminal only):

   ```
   npx @_davideast/stitch-mcp init
   ```

   If the direct command fails in an unclear way, offer the user the guided wizard.

3. Confirm the server is registered. Run:

   ```
   claude mcp list
   ```

   and check that the server named stitch appears in the list and connects successfully. If it appears twice or is marked as Failed to connect — see the "אם נתקעתם" table below.

4. For the new MCP server to be picked up, you may need to refresh Claude Code's MCP connections, or restart the session. If the server does not appear in the tools available to you after registration — ask the user to close and reopen Claude Code.

What not to invent: if a particular command fails in a way you do not understand, if the key is rejected, or the user is on a different operating system than these instructions assume — do not guess and do not invent a command or endpoint. Stop, explain to the user what you tried and what happened, and ask them to reach out to the course group with a screenshot.

---

## איך יודעים שהצליח

אחרי שקלוד סיים, בקשו ממנו לרשום את הפרויקטים שלכם:

```text
רשום לי אילו פרויקטים יש לי ב-Stitch
```

או, אותו פרומפט באנגלית:

```text
List the projects I have in Stitch
```

אם החיבור חי, קלוד יזהה לבד שיש לו כלי חדש, יפנה אליו, ויחזיר רשימה אמיתית של הפרויקטים מהחשבון שלכם. זהו — החיבור עובד.

אין לכם עדיין אף פרויקט? זה תקין. המשיכו לצעד הבא ביחידה, שם תבקשו מקלוד לייצר את המסכים הראשונים דרך Stitch — גם זו בדיקה טובה באותה מידה.

---

## אם נתקעתם

| מה קרה | מה עושים |
|---|---|
| קלוד מדווח שהפקודה npx או Node לא נמצאה | הסביבה הטכנית לא מוכנה. ודאו שהתקנתם Node (nodejs.org, גרסת LTS) בצעד הראשון של היחידה, ואז נסו שוב |
| המפתח נדחה, או מופיעה שגיאה על "API keys are not supported / Expected OAuth2 access token" | ‏Stitch מבדיל בין שני נתיבי-אימות. אם נתיב המפתח לא עובד אצלכם כרגע, הריצו בטרמינל את האשף `npx @_davideast/stitch-mcp init` ובחרו בו התחברות עם חשבון Google Cloud. אם גם זה תקוע — צלמו מסך ופנו לקבוצת הקורס |
| יצירת המפתח עצמו נחסמה ב-Stitch | ‏Stitch לפעמים חוסם יצירת-מפתח כהגנה אוטומטית — ממתינים ומנסים שוב, או משתמשים בחשבון Google אחר. את המפתח יוצרים חזרה בצעד ה-Bitwarden של היחידה (בתפריט הפרופיל ← ‏Stitch settings ← ‏API key ← ‏Create key) |
| איפה המפתח שהפקודה צריכה | המפתח נשמר ב-Bitwarden בצעד הקודם של היחידה. פותחים את הכספת, שולפים את הרשומה של Stitch, ומדביקים לתוך הפקודה בטרמינל. לא יצרתם עדיין? חוזרים לצעד ה-Bitwarden ויוצרים אותו |
| הדבקתם בטעות את המפתח בצ'אט | מחליפים אותו: יוצרים מפתח חדש ב-Stitch ‏(בתפריט הפרופיל ← ‏Stitch settings ← ‏API key ← ‏Create key), מוחקים את הישן, מעדכנים את הרשומה ב-Bitwarden, ומריצים שוב את פקודת-החיבור עם החדש |
| השרת מופיע Failed to connect, או שמופיעה אזהרה על Conflicting scopes | כנראה נשארה רשומת-stitch ישנה או שבורה מניסיון קודם. מריצים `claude mcp list` ובודקים אם stitch מוגדר פעמיים; מוחקים את הרשומה השגויה עם `claude mcp remove stitch -s local` (או `-s user`, לפי מה שהאבחון מציע) ובודקים שוב |
| השרת לא מופיע אחרי הרישום | השרת נרשם אבל לא נטען. סגרו ופתחו מחדש את Claude Code, וקלוד יזהה את החיבור בהפעלה. אפשר גם לבדוק עם `claude mcp list` שהשרת אכן רשום |
| קלוד עונה בלי להשתמש בכלי | נסחו את הבקשה עם השם המפורש "ב-Stitch", וקלוד יפנה אל הכלי |
