---
type: practice
unit: vscode
session: 4
phase: הכנה
num: "4.2"
parent: content/session-4/vscode/index.html
parentLabel: VS Code ו-Claude Code
title: בבית — VS Code ו-Claude Code
studio: [Design, Operate]
video: TBD
---

# בבית — `VS Code` ו-`Claude Code`

## מה עושים כאן

זו ההכנה השנייה לשיעור, והיא ממשיכה בדיוק מאיפה שעצרנו. בהכנה הקודמת פתחתם `Terminal`, בניתם מכונת-זמן ודחפתם לענן. עכשיו נכנסים לחדר-הבקרה — `VS Code` — ומכניסים אליו את `קלוד`, שעובד על הקבצים שלכם.

שני סרטונים קצרים. הראשון מכיר את `VS Code` לבד. השני מתקין את התוסף של `Claude Code`, ואז `קלוד` בונה לכם עמוד שלם מפרומפט אחד — ואתם מעלים אותו חי לאינטרנט בעצמכם, בפעם הראשונה.

> **נתקעתם? שאלו את `קלוד`.** אם משהו לא ברור, או שלא הבנתם מה שלב מסוים מבקש, פשוט שאלו את `קלוד`. צלמו מסך של מה שאתם רואים, הדביקו לו, ובקשו שיסביר: "מה אני רואה כאן ואיך אני ממשיך?". זה הכי מהיר, ו-`קלוד` יעבור איתכם צעד-צעד.

### מה שאתם צריכים קודם

- חשבון `GitHub`, עם `Git` מותקן ומחובר, מההכנה הקודמת. זה מה שיאפשר להעלות את העמוד לאוויר.
- חשבון `Claude` פעיל (‏`Pro` או `Max`) — זה מה שמריץ את `Claude Code`.

---

## 🎬 סרטון 1 · `VS Code` — חדר הבקרה

<!-- video: TBD -->

הסרטון מכיר את `VS Code`, את שלושת החלקים שרואים בו, ומתקין אותו. צפו בו, ואז עשו את התרגיל.

### תרגיל 1 — מקימים את חדר-הבקרה

מה עושים:

1. נכנסים לדף ההורדה של `VS Code` ומתקינים. ב-`Windows` בחרו `User Installer` — הוא לא דורש הרשאות מנהל.
2. פותחים את `VS Code`, ובוחרים `File` ← `Open Folder` על תיקייה חדשה וריקה. זו תהיה סביבת-העבודה שלכם.
3. אם קופץ חלון `Workspace Trust`, בוחרים `Yes, I trust the authors`. בלי האישור הזה, `קלוד` לא יוכל להריץ כלים בהמשך.

מה השגתם: `VS Code` פתוח עם תיקיית-עבודה ריקה ומהימנה, ואתם מזהים את שלושת החלקים — `Editor` במרכז, `Terminal` בתחתית (`Ctrl` `+` backtick), ו-`Git` בסרגל הצד.

בדיקה עצמית:
- `VS Code` נפתח והתיקייה הריקה פתוחה בתוכו.
- אישרתם את `Workspace Trust`.
- אתם יודעים להצביע על ה-`Editor`, ה-`Terminal` וה-`Git` בחלון.

---

## 🎬 סרטון 2 · התוסף של `Claude Code` — `קלוד` בונה, ואתם מפרסמים

<!-- video: TBD -->

הסרטון מתקין את התוסף של `Claude Code` בתוך `VS Code`, ואז נותן ל-`קלוד` פרומפט אחד שבונה עמוד — שאותו אתם מעלים לאוויר. צפו בו, ואז עשו את התרגיל.

### תרגיל 2 — `קלוד` בונה עמוד, ואתם מעלים אותו לאוויר

חשוב: לאורך כל התרגיל אנחנו עובדים עם **התוסף של `Claude Code` בתוך `VS Code` — הפאנל**, לא עם ה-`Terminal`.

#### צעד א — מתקינים את `קלוד` (הכול דרך הממשק, בלי `Terminal`)

1. פותחים את `Extensions` (‏`Ctrl` `+` `Shift` `+` `X`), מחפשים `Claude Code`, ולוחצים `Install`. זה התוסף הרשמי של `Anthropic`, והוא מביא איתו את כל מה שצריך — אין צורך בשום דבר ב-`Terminal`.
2. מתקינים את `benefits-toolkit` — גם הוא מה-`Marketplace`. מחפשים `benefits-toolkit` ב-`Extensions` ולוחצים `Install`, או פותחים את הכתובת `https://marketplace.visualstudio.com/items?itemName=benakiva.benefits-toolkit`. הוא נותן עברית מימין-לשמאל בצ'אט, היסטוריית-שיחות, וצליל כש-`קלוד` מסיים או צריך אתכם.
3. טוענים מחדש את החלון (`Reload Window`), פותחים קובץ כלשהו, ולוחצים על אייקון ה-`Spark` בפינה הימנית-עליונה — הפאנל של `Claude Code` נפתח בצד. בפעם הראשונה לוחצים `Sign in`, מאשרים בדפדפן עם חשבון ה-`Claude`, וזהו.

מה השגתם: הפאנל של `Claude Code` פתוח ב-`VS Code`, `benefits-toolkit` פעיל, והעברית בצ'אט נקראת מימין-לשמאל.

#### צעד ב — מריצים את הפרומפט המוכן ב-`Plan Mode`

1. בפאנל, לוחצים על מחוון-המצב בתחתית תיבת-הפרומפט, ובוחרים `Plan Mode`. במצב הזה `קלוד` חושב קודם ומראה לכם תוכנית לפני שהוא נוגע בכלום.
2. מעתיקים את הפרומפט המוכן שלמטה **כמו שהוא** (הוא באנגלית, אל תשנו אותו), מדביקים בתיבה, ושולחים.
3. `קלוד` ישאל אתכם קודם באיזו שפה לבנות את העמוד — ענו. ואז תראו אותו מחפש ברשת, מסביר מה מצא, כותב תוכנית שנפתחת כמסמך (קראו אותה ואשרו), בונה את העמוד, ופותח אותו מולכם.

הפרומפט להעתקה (אנגלית, כמו שהוא):

```
You are helping me publish a web page to GitHub Pages. Work in Plan Mode: think first, show me a short plan, and wait for my approval before you build anything. Follow these steps in order.

STEP 0 — LANGUAGE. Before anything else, ask me one question: should the guide be written in Hebrew or in English? Wait for my answer.
- If Hebrew: set the page to right-to-left (<html lang="he" dir="rtl">) and write the explanatory sentences in natural Hebrew. IMPORTANT: keep every technical term and every GitHub interface label in English — do NOT translate these: GitHub, GitHub Pages, repository, branch, main, commit, push, Settings, Pages, Source, Deploy from a branch, index.html, README, HTTPS, Git, terminal. Translate only the plain explanatory prose around them.
- If English: left-to-right, everything in English.

STEP 1 — RESEARCH (do a real web search; I want to watch it happen). Search the web for the current official way to publish a static page to GitHub Pages by pushing it with Git: creating a repository, pushing an index.html with git, then enabling Pages from the repository's Settings > Pages (choosing the branch, saving, and where the live URL appears). Then tell me, in 3 to 5 short bullet points, what you found and which official source it came from.

STEP 2 — PLAN. Based on what you found, show me a short plan of the page: its sections, in order. Wait for my approval before building.

STEP 3 — BUILD. After I approve, build ONE self-contained index.html (all CSS and JS inline, no build step, no frameworks). The page is a step-by-step guide that teaches a complete non-developer how to publish this very index.html to GitHub Pages using git push.

CONTENT — the deploy path, in this exact order (this is the whole point):
- Hero: a bold title, a one-line subtitle, and a short note that this page will teach you how to publish itself.
- Step 1: Create a new empty repository on GitHub (Public, no README).
- Step 2: In the terminal, push this folder up with Git — show these as copy-ready commands: git init / git add . / git commit -m "my first page" / git remote add origin <URL> / git branch -M main / git push -u origin main.
- Step 3: On GitHub, open the repository's Settings, then Pages; set Source to "Deploy from a branch"; choose the main branch and the / (root) folder; Save.
- Step 4: Wait a minute, refresh, and open the live URL shown at the top of the Pages settings.
- A short "Common problems" section: the page is not live for a minute or two (wait and refresh); the wrong branch was selected (choose main); nothing shows because index.html is not at the repository root.

DESIGN — premium, futuristic GitHub dark theme (must not look generic):
- Dark theme in the spirit of GitHub's own dark interface, elevated to feel modern and premium.
- Exact colors: page background #0d1117; card/surface #161b22 (or translucent rgba(22,27,34,0.7) with backdrop blur); elevated/hover surface #1c2128; hairline borders #30363d (1px); primary accent green #3fb950 (used sparingly — step numbers, key actions, subtle glow); secondary accent blue #58a6ff (links); primary text #e6edf3; muted text #7d8590.
- Background detail: a very subtle radial gradient glow near the top (faint green/blue) and, optionally, a faint low-opacity dot grid. Keep it calm.
- Typography: load "Rubik" from Google Fonts (fallbacks Assistant, system-ui, sans-serif) for all prose and headings; load "JetBrains Mono" from Google Fonts and use it ONLY for commands, code, and inline technical terms. h1 ~40px/700; section titles ~26px/600; body 17px, line-height 1.7; centered content, max-width ~780px.
- Cards: each step is a card — 14px radius, 1px #30363d border, translucent surface with backdrop-filter blur(12px), a soft inset top highlight (inset 0 1px 0 rgba(255,255,255,0.05)), padding 28px+. On hover: gentle lift translateY(-3px) and a soft green glow (box-shadow: 0 0 0 1px rgba(63,185,80,0.5), 0 10px 30px rgba(63,185,80,0.12)); cursor pointer; 200ms transitions.
- Step numbers: circular badges with a green-to-blue gradient, white numeral, faint outer glow.
- Icons: Tabler Icons from CDN for each section header and each common-problem item. No emojis anywhere.
- Command blocks: style as a small "terminal card" — background #010409, JetBrains Mono, a top bar with three small dots, a green ">" prompt before commands, and a copy button (Tabler copy icon) that copies the block.
- Spacing: airy, 56px+ between sections. Premium restraint: one accent color, hairline borders, generous whitespace, no clip-art.

MOTION — subtle only: fade-and-slide-up each section as it enters the viewport (IntersectionObserver, staggered, 250ms ease-out); smooth hover states (transform and opacity only); respect prefers-reduced-motion: reduce; nothing flashing, no glitch, no autoplay loops.

RESPONSIVE: great on phone and laptop; body text at least 16px on mobile; no horizontal scroll.

STEP 4 — OPEN. After building, open index.html in my default browser so I can see it (run the correct command for my operating system).

Keep everything in a single index.html, and build the whole page in the language I chose in Step 0.
```

תוצר-ביניים: עמוד `HTML` אחד, מעוצב ויפה בסגנון `GitHub` כהה, שמסביר צעד-אחר-צעד איך מעלים עמוד ל-`GitHub Pages` — נפתח מולכם בדפדפן.

#### צעד ג — מעלים את העמוד לאוויר בעצמכם (ה-deploy הראשון)

זה החלק היפה: העמוד שמסביר איך מעלים הוא העמוד שאתם מעלים. לכו אחרי ההוראות שכתובות **בעמוד ש-`קלוד` בנה לכם עכשיו**. הרעיון: אתם עושים `git push` — וככה העמוד עולה — ואז מסדרים ב-`Settings` שיופיע ב-`Pages`:

1. יוצרים `repository` חדש ב-`GitHub` ודוחפים אליו את `index.html` עם `git push` (בדיוק המיומנות מההכנה הקודמת).
2. מפעילים `GitHub Pages`: ב-`repository`, נכנסים ל-`Settings` ← `Pages` ← מגדירים `Source` ל-`Deploy from a branch` ← בוחרים את ה-`branch` בשם `main` ← `Save`.
3. מחכים דקה, מרעננים, ופותחים את הכתובת החיה שמופיעה למעלה.

מה השגתם: העמוד שבניתם חי באינטרנט, עם כתובת ציבורית משלו — ה-deploy הראשון שלכם, מודרך על ידי עמוד ש-`קלוד` בנה לכם.

בדיקה עצמית:
- הפאנל של `Claude Code` פתוח, והעברית בצ'אט תקינה.
- `קלוד` שאל אתכם באיזו שפה, חיפש ברשת, הראה תוכנית, ובנה עמוד שנפתח בדפדפן.
- יש לכם כתובת חיה ב-`GitHub Pages`, ופתיחה שלה מציגה את העמוד.

הערות-חיכוך ידועות (אם משהו נתקע — ואפשר תמיד לצלם מסך ל-`קלוד` ולשאול):
- אייקון ה-`Spark` לא מופיע? פתחו קודם קובץ כלשהו — הוא מופיע רק כשקובץ פתוח.
- ה-`Sign in` נתקע? מ-`Command Palette` הריצו `Developer: Reload Window`.
- לא מוצאים את `Plan Mode`? הוא במחוון-המצב בתחתית תיבת-הפרומפט.
- העמוד לא נפתח בדפדפן לבד? לחיצה-ימנית על `index.html` בסייר ← `Open in Default Browser`.
- הכתובת של `Pages` לא עובדת מיד? המתינו דקה-שתיים ורעננו — הפרסום לוקח רגע.

---

## מה הלאה

זהו. הכרתם את חדר-הבקרה, התקנתם את `קלוד`, ובפרומפט אחד בניתם ופרסמתם עמוד חי — הפעם הראשונה שעשיתם `deploy`. זו הטעימה הראשונה של `Claude Code`. בכיתה נמשיך מכאן ונבנה דברים אמיתיים.

ואם משהו נתקע — קודם כול שאלו את `קלוד`, ואם עדיין תקוע, שלחו צילום מסך בקבוצה, ונפתור יחד עוד לפני השיעור.
