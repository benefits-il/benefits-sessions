---
type: prompt-doc
unit: class-bmad
session: 5
title: פרומפט-האב — מהידע שלכם לעמוד-המעקב
target: Claude Code
---

# פרומפט-האב — מהידע שלכם לעמוד-המעקב

## מה המסמך הזה

זה פרומפט אחד שמדביקים בקלוד קוד, בתוך תיקיית-הפרויקט שלכם, והוא עושה שני דברים בזה אחר זה.

**קודם הוא אוסף לכם את הידע.** כל מה שבניתם עד עכשיו מפוזר: קול-המותג במקום אחד, האיפיון במקום שני, מאגר-הידע, מערכת-העיצוב, הסקיצות. קלוד שולח סוכנים שסורקים את המקומות שתגידו לו, מחזיר לכם רשימה של מה שמצא, בוחר מה רלוונטי — ומרכז את הכול לתיקיית-ידע אחת בתוך הפרויקט.

**ואז הוא עוצר ומחכה לכם.** שום דבר לא ממשיך בלי שתאשרו.

**אחרי האישור הוא בונה לכם עמוד מעקב.** קובץ HTML אחד שיושב אצלכם בפרויקט, מעוצב בסגנון של הקורס, ובו כל מסע BMAD: כל שלב, מה הפקודה שלו, מה נדרש מכם, מה בודקים בתוצר לפני שמאשרים — ופרומפט מוכן להעתקה לכל שלב. זה העמוד שממשיך ללוות אתכם אחרי שהשיעור נגמר.

לפני שמדביקים: פותחים בקלוד קוד את תיקיית-הפרויקט שלכם — זו שבה תעבדו עם BMAD.

---

## הפרומפט — להעתקה

מעתיקים את כל הבלוק, מדביקים בקלוד קוד, ושולחים.

```text
You are working inside the user's own project folder in Claude Code. The user is a student in an AI course; they are not a developer and they are working in Hebrew. Speak to them in Hebrew throughout, in short plain sentences, and never mix Hebrew and English inside the same sentence.

This task has two stages with a hard approval gate between them. Stage A collects the user's scattered knowledge into the project. Stage B builds them a single HTML tracking page for their BMAD journey. Do not start Stage B before the user has explicitly approved Stage A.

Make no assumptions about what the user is building, what their folders are called, or what kind of project this is. Everything specific comes from them.

===============================================================
STAGE A — COLLECT THE KNOWLEDGE
===============================================================

The user's intent, in their own words:

"I have a lot of knowledge related to the app I want to build, and it is scattered across several places. I would like to send agents that will go and look for relevant information about the app everywhere (without skipping anything) and then return an index list of the locations of those files, and then you will choose what is relevant for us, and prepare a knowledge folder here with us, where all the information will live. Explain what you understood and wait for approval to continue."

Carry that out as follows.

1. ASK WHERE THE KNOWLEDGE LIVES.
   Ask one clear question and stop for the answer. Say, verbatim in Hebrew:
   "איפה הידע שלכם יושב? תנו לי נתיב אחד או כמה — תיקיות במחשב שבהן יש חומרים שקשורים לפרויקט. אני אסרוק אותן ואחזיר לכם רשימה."
   Accept one path or several. Accept the current project folder as one of them if the user says so.

2. SCAN EXHAUSTIVELY.
   Dispatch parallel subagents, one per top-level path the user gave, to walk that path and every subfolder underneath it, to full depth. Exhaustive, not a sample — skipping is a failure of this stage. Read enough of each file to describe it in one line; do not read files in full.
   Include documents, notes, markdown, text, PDFs, spreadsheets, presentations, images of screens or sketches, design tokens, and code that documents structure. Skip machine noise: node_modules, .git internals, build output, dist, caches, virtualenvs, binaries and installers, and anything over ~20 MB. If a path is unreadable or does not exist, say so plainly instead of silently dropping it.

3. RETURN AN INDEX — NOT CONTENT. THIS IS A VISIBLE DELIVERABLE.
   Print the index in the chat, as a table, before you copy anything anywhere. The user has to see it. A summary sentence such as "I found 10 files" does not satisfy this step and is a failure of the stage.
   One row per file: its location, and one line describing what it holds. Group by source path. Never paste file contents into the chat, and never summarize a file at length. If the scan found more than about 80 files, show them grouped and say how many there are in total; do not truncate silently.

4. CHOOSE WHAT IS RELEVANT — ALSO IN THE CHAT.
   Go through the index and mark what actually serves building this project — brand voice, requirements and characterization, knowledge base, design system, screen sketches, decisions, research. Give a short reason per item, one line each. Say what you are leaving out and why. This is visible too: the user reads your choices in the chat, not only in a file.

5. BUILD THE KNOWLEDGE FOLDER.
   Create docs/knowledge/ inside the project and copy the chosen files into it. Copy, never move, and never delete anything at the source. Preserve original filenames; if two files collide, prefix the second with its source folder name. Inside docs/knowledge/ write INDEX.md in Hebrew: a table of what is in the folder, one line per file, and where each file came from.
   Use exactly docs/knowledge/ — not docs/ itself. Another tool writes to docs/ later and the two must not collide.

6. STOP AT THE GATE.
   Explain in Hebrew what you understood, what you scanned, what you chose, and what is now in docs/knowledge/. Then say, verbatim in Hebrew:
   "זה מה שאספתי. אם זה נראה לכם נכון — כתבו לי 'אישרתי' ואני ממשיך לבנות את עמוד המעקב. אם משהו חסר או מיותר — תגידו לי ואני אתקן."
   Do not continue to Stage B until the user answers with an explicit approval. A question, a comment, or silence is not approval. If they ask for a fix, fix it and return to this gate.

===============================================================
STAGE B — BUILD THE TRACKING PAGE
===============================================================

Only after explicit approval.

1. PRECHECK.
   Check whether the folder _bmad/ exists in the project. If it does not, BMAD is not installed here and bmad-help does not exist yet. Tell the user in Hebrew that the installation is missing, ask them to run npx bmad-method install in a terminal inside this folder, and wait until they confirm it finished. Do not continue without _bmad/.

2. TALK TO THE BMAD MASTER.
   Invoke bmad-help. Let it scan the project and hold its conversation with the user about what they are building and where they currently stand. Do not answer for the user and do not rush it.
   When it finishes, you should know two things: what the project is, and which stage of the BMAD sequence the user is at right now. Derive the stage from what actually exists in the project: no BMAD artifacts at all means they are at the very beginning, before the product brief — that is not ambiguous, so do not ask about it. Ask the user one short question in Hebrew only if artifacts exist and it is genuinely unclear which one is current.

3. BUILD THE PAGE.
   Write one single self-contained HTML file to docs/bmad-tracker.html. No build step, no dependencies, no external files besides Google Fonts. The page is in Hebrew, right-to-left. Open it for the user when it is ready and tell them, in Hebrew, that this page is theirs and it stays with them.

WHAT THE PAGE CONTAINS

Header: the project name as the user described it, and one line saying this page tracks the whole BMAD journey.

A stage strip along the whole journey, marking where the user stands right now, based on what bmad-help reported. Stages that are already behind them are marked done; the current one is highlighted; the rest are ahead.

Then one card per stage, in order. Every card holds:
  - the stage name in Hebrew and the command name as a code tag
  - which agent runs it and what it produces
  - what is required from the user at that stage, in plain language
  - what to check in the artifact before approving it — this is the Go/No-Go moment
  - a ready-to-copy prompt with a copy button that copies the full text
  - a checkbox that marks the stage done and persists in localStorage, so the page remembers state between visits

The stages, in this exact order. These command names are verified against the official BMAD v6 documentation — use them exactly as written and invent nothing:

  1. bmad-help — BMad Master — a recommendation for the next step. The navigation point: stuck at any moment, come back here.
  2. bmad-product-brief — מרי — product-brief.md. She asks what you are building, for whom, and what the outcome is.
  3. bmad-prd — ג'ון — prd.md and decision-log.md. The requirements document.
  4. bmad-ux — סאלי — DESIGN.md and EXPERIENCE.md. Only if the project has an interface.
  5. bmad-create-architecture — ווינסטון — the architecture: how it will be built. Optionally followed by bmad-generate-project-context.
  6. bmad-create-epics-and-stories — the project cut into work items. In v6 this comes after the architecture, on purpose.
  7. bmad-check-implementation-readiness — ווינסטון — a readiness report. The quality gate before any code.
  8. bmad-sprint-planning — אמיליה — sprint-status.yaml. Opens the work plan.
  9. bmad-create-story then bmad-dev-story then bmad-code-review — אמיליה — code and tests. A loop, once per story.
  10. Karman — the crossing into an autonomous run. Details below. Its name in Hebrew on the page is spelled כרמן, always — never קרמן.

Each ready-to-copy prompt is the command on its own line, followed by a short English context line pointing the agent at the knowledge folder. For example, the one on the bmad-product-brief card:

  bmad-product-brief

  Context: my project knowledge is collected in docs/knowledge/ — read INDEX.md and the files it lists before you start asking, and use them to pre-fill whatever you can. Ask me only about what is genuinely missing.

Adapt that context line per stage so it points at what that stage actually needs — the PRD card points at the product brief and the knowledge folder, the architecture card points at the PRD, and so on.

The full BMAD map, complete, on the page: help, brief, prd, ux, architecture, epics, readiness, sprint, stories. One clear visual with the command under each station, so the user can see the whole road at once.
Command names are long — bmad-check-implementation-readiness is thirty-four characters. The map must survive that: let every station size itself to its own content, let the command text wrap onto as many lines as it needs inside its own tag, and never let a tag overflow its station or overlap its neighbour. Stations flow right to left and wrap onto further rows when the width runs out; arrows between them point left, because the page is Hebrew. Before you finish, check the map at a 1280px width and again at a narrow phone width, and fix it if anything is clipped.

A short "how to work with this" note in Hebrew, holding three rules:
  - a clean chat for every command
  - type the command name directly, with no slash before it; if right-to-left flips the character, just type the name as it is
  - between commands, open the document that was created, read it, and approve or fix — an inaccurate document means inaccurate code

A troubleshooting note in Hebrew: stuck at any point, run bmad-help — it scans the project and says what the next step is. Guides on the internet that use /pm or /architect are from v4 and v5; here the bmad- commands are typed directly.

THE KARMAN STAGE — LAST CARD ON THE PAGE

Frame it as the crossing from planning into an autonomous run: the moment the machine keeps going on its own. It is not a stage that gets finished in class — it is what continues afterwards. Write it in that spirit, in Hebrew, without hype.

The card must state the two conditions that have to be true before calling it, and put them in this order:
  - the project has to be a git repository with at least one commit. The page instructs: run git init, then a first commit, and only then call Karman. Without that first commit it fails.
  - _bmad/ has to exist and BMAD has to have been run on the project — which is why this card sits at the end and not at the beginning.

Then the installation, as two commands the user runs in Claude Code:

  /plugin marketplace add benefits-il/orbit-autopilot
  /plugin install orbit-autopilot@orbit-autopilot

Mention the interface alternative as well: Customize, then Plugins.

And then the call itself, as a ready-to-copy prompt whose first line is /karman — with the slash, because that is how the plugin skill is invoked. Say what it does — it works out everything the build will need from a human, walks the user through obtaining it, verifies each item landed, and writes its own console to docs/karman-console.html.

THE DESIGN — BUILD IT EXACTLY LIKE THIS

The page is styled in the Benefits course look. Everything needed is written here; do not look for a design file and do not import one.

Colors, as CSS custom properties on :root:
  --ink: #0F172A          hard borders and headings
  --paper: #FFFFFF        cards and surfaces
  --canvas: #FFFBEB       page background
  --anchor: #047857       primary action green
  --green-soft: #D1FAE5   soft mint fill, pills, done states
  --green-mint: #6EE7B7   mint accent
  --depth: #064E3B        the block-shadow under primary buttons
  --gray-900: #1E293B     body text
  --gray-600: #475569     muted text

Fonts, loaded from Google Fonts:
  headings — Rubik, weights 400 to 900
  body — Varela Round
  code and command tags — JetBrains Mono

The visual language is Memphis: a hard 2.5px solid ink border on every card, a solid offset shadow with no blur at all (5px 5px 0 0 var(--ink)), slightly squared corners (radius 14px, pills 999px), and one accent per section rather than seven. Primary buttons carry a block shadow: 0 6px 0 0 var(--depth), dropping to 0 2px on press.

Right-to-left: dir="rtl" and lang="he" on the html element. Command names, file paths and code stay left-to-right inside their own inline elements — wrap them so they do not flip.

Single file. Inline CSS and JavaScript. No frameworks, no CDN scripts beyond the Google Fonts stylesheet, no images that live outside the file. It has to open correctly by double-clicking it.

RULES THAT HOLD ACROSS BOTH STAGES

Do not invent a command name. Every BMAD command on the page appears in the list above; if you are unsure about anything else, leave it out and say so.
No emojis, anywhere — not in the chat and not on the page. Arrows inside Hebrew text point left.
If API keys or passwords come up at any point, they go into a terminal only — never into the chat.
Do not push anything to git and do not create commits, except the first commit the Karman card instructs the user to make themselves.
Work only inside this project folder. Reading from the paths the user named is fine; writing outside the project is not.
```

---

## איך יודעים שהצליח

שלוש בדיקות, לפי הסדר:

**אחרי שלב א** — קלוד החזיר לכם רשימה של קבצים עם שורת-תיאור לכל אחד, ולא הדפיס לכם תוכן. בתיקיית-הפרויקט נוצרה `docs/knowledge/`, ובתוכה הקבצים שנבחרו וקובץ `INDEX.md`.

**בשער** — קלוד עצר וביקש אישור. אם הוא המשיך לבד לבנות את העמוד בלי שאמרתם "אישרתי" — עצרו אותו וחזרו לשלב א.

**אחרי שלב ב** — נוצר הקובץ `docs/bmad-tracker.html`. פותחים אותו בדפדפן: הוא נפתח בעברית, מימין לשמאל, ורואים בו את כל שלבי BMAD. לוחצים על כפתור ההעתקה באחד השלבים ומדביקים במקום כלשהו — צריך לקבל את הפרומפט המלא.

---

## אם נתקעתם

| מה קרה | מה עושים |
|---|---|
| קלוד ממשיך לשלב ב בלי לעצור | עוצרים אותו, וכותבים: "חזור לשלב א, אני עוד לא אישרתי". הפרומפט בנוי עם שער — אם הוא דילג עליו, מחזירים אותו |
| הסריקה החזירה מעט מדי קבצים | כנראה נתתם נתיב צר מדי. אומרים לקלוד: "תסרוק גם את הנתיב הזה", ונותנים נתיב נוסף |
| קלוד מדפיס תוכן של קבצים במקום רשימה | כותבים לו: "אני רוצה אינדקס בלבד — מיקום הקובץ ושורת תיאור, בלי תוכן" |
| קלוד קפץ ישר להעתקה ולא הראה רשימה | כותבים לו: "תראה לי קודם את האינדקס בצ'אט — טבלה של כל הקבצים שמצאת" |
| קלוד אומר שאין `_bmad/` | ‏BMAD לא מותקן בתיקייה הזו. פותחים טרמינל בתוך התיקייה, מריצים `npx bmad-method install`, ואז אומרים לקלוד להמשיך |
| ‏`npx bmad-method install` נכשל | בודקים `node -v` — צריך 20.12 ומעלה |
| הפקודה `bmad-help` לא נענית | צ'אט נקי, וכותבים את שם הפקודה ישירות בלי slash לפניו |
| העמוד נוצר אבל נראה שבור | מבקשים מקלוד: "בנה מחדש את `docs/bmad-tracker.html` — קובץ HTML יחיד, בלי תלויות חיצוניות" |
| הגופנים לא נטענים | צריך חיבור לאינטרנט בפתיחה הראשונה. בלי חיבור העמוד עדיין עובד, רק עם גופן ברירת-מחדל |
| כפתור ההעתקה לא עובד | חלק מהדפדפנים חוסמים העתקה בקובץ מקומי. מסמנים את הטקסט ומעתיקים ידנית |
