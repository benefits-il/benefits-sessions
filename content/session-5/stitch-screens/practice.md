---
type: practice
unit: stitch-screens
session: 5
phase: הכנה
num: "5.4"
parent: content/session-5/stitch-screens/index.html
parentLabel: מסכים לפלטפורמה שלכם
title: בבית — מסכים לפלטפורמה שלכם
studio: [Design]
video: TBD
downloads: [{"label":"מסמך ההתקנה של Stitch MCP","href":"stitch-mcp-install.md"}]
---

# בבית — מסכים לפלטפורמה שלכם

## מה עושים כאן

עד עכשיו בניתם את כל החלקים של הפרויקט שלכם — קול-מותג, מערכת-עיצוב, ובסיס-ידע. חסר רק דבר אחד: איך זה **נראה**. בהכנה הזאת ניקח את המותג שלכם ונהפוך אותו למסכים אמיתיים של הפלטפורמה — בעזרת כלי מדהים בשם **Google Stitch**.

ואיך נעבוד איתו? בדיוק כמו שאתם כבר עובדים עם הכול: **דרך Claude Code.** ל-Stitch יש MCP רשמי — אותו סוג חיבור שלמדתם בהכנה על MCP — אז מחברים אותו לקלוד קוד פעם אחת, ואז פשוט אומרים לקלוד אילו מסכים אתם רוצים. קלוד מפעיל את Stitch, מייצר את המסכים, ומוריד אותם ישר לתיקיית-הפרויקט שלכם. בלי להקליק באתר, בלי להעתיק-להדביק.

אלה סקיצות-המסכים שתביאו איתכם לכיתה — הרכיב האחרון בחבילה שתזין את הפרויקט הסופי.

> **נתקעתם? שאלו את קלוד.** אם משהו לא ברור, צלמו מסך, הדביקו לקלוד, ובקשו שיסביר: "מה אני רואה כאן ואיך אני ממשיך?".

### מה שאתם צריכים קודם

- ‏Claude Code מותקן (משיעור 4) ופתוח בתיקיית-הפרויקט שלכם.
- חשבון Google פעיל — ‏Stitch חינמי ונפתח איתו.
- **חומר-המקור של המותג שלכם** — וכאן יש שתי אפשרויות, שתיהן טובות:
  - עשיתם את design-pipeline (ההכנה של שיעור 4)? יש לכם בסיס-ידע עיצובי עשיר. מצוין — נשתמש בו.
  - לא עשיתם? משתמשים בכל מה שכבר יש לכם — כולל מערכת-העיצוב הפשוטה שבניתם בשיעור 4 ‏(BUILD YOUR BRAND). גם זה מספיק בהחלט.

---

## 🎬 הסרטון של היחידה

<!-- video: TBD -->
> הסרטון בהכנה ויעלה כאן בקרוב.

הסרטון מראה את כל המסלול חי: מחברים את Stitch לקלוד קוד, ומשם — מהמותג שלכם, בפרומפט אחד, למסכים שנוחתים בתיקייה.

---

## צעד 1 — מתקינים Node (דבר טכני קטן, חד-פעמי)

לפני שמחברים כלים לקלוד קוד, צריך רכיב אחד בסיסי שנקרא Node — זו התשתית שמאפשרת לחיבורים כאלה לרוץ על המחשב. מתקינים אותו פעם אחת, וזהו.

1. נכנסים ל-nodejs.org ומורידים את המתקין שמסומן LTS (הגרסה היציבה).
2. מריצים את המתקין ומאשרים את ברירות-המחדל (Next עד Finish).
3. רוצים לוודא שהצליח? אפשר פשוט לבקש מקלוד: "בדוק אם Node מותקן אצלי". הוא יריץ את הבדיקה ויגיד.

מה השגתם: הסביבה מוכנה לחבר כלים לקלוד קוד. (את Node תצטרכו גם בהמשך ובכיתה — אז זה כבר מסודר.)

---

## צעד 2 — מחברים את Stitch לקלוד קוד

זה בדיוק אותו דפוס שעשיתם עם NotebookLM בהכנה על MCP, רק עם כלי אחר — ועם הרגל-אבטחה אחד חדש.

1. נכנסים ל-stitch.withgoogle.com ומתחברים עם חשבון Google.
2. יוצרים מפתח: בתפריט הפרופיל ← ‏Stitch settings ← ‏API key ← ‏Create key.
3. שומרים את המפתח ב-Bitwarden — בדיוק ההרגל מהיחידה הראשונה: רשומה חדשה, המפתח בשדה מוסתר.
4. נותנים לקלוד את [מסמך ההתקנה של Stitch MCP](stitch-mcp-install.md) ומבקשים ממנו: "תתקין לי לפי המסמך הזה". קלוד בודק שהכול מוכן ומדריך אתכם, ואת פקודת-החיבור עם המפתח מהכספת אתם מריצים בעצמכם, בטרמינל. זה ההרגל החדש, והוא כלל הזהב של המסמך: את המפתח מדביקים רק בטרמינל, אף פעם לא בצ'אט.

מה השגתם: קלוד קוד מחובר ל-Stitch. מעכשיו קלוד יכול לייצר ולמשוך מסכים בשבילכם.

בדיקה עצמית:
- ‏Node מותקן.
- מפתח Stitch שמור בכספת.
- ה-MCP של Stitch מופיע מחובר בקלוד קוד.

---

## צעד 3 — מסדרים את המותג לקובץ אחד (DESIGN.md)

‏Stitch עובד הכי טוב כשנותנים לו את מערכת-העיצוב כקובץ מסודר בשם DESIGN.md — קובץ קטן שמרכז את הצבעים, הגופנים והסגנון. נבקש מקלוד לבנות אותו מהחומר שכבר יש לכם בתיקייה.

מדביקים בקלוד קוד את הפרומפט המוכן. קלוד יקרא את כל מה שיש לכם — ה-KB מ-design-pipeline או ה-DS משיעור 4 — ישאל רק מה שחסר, ויכתוב DESIGN.md נקי.

הפרומפט להעתקה:

```
I am about to design UI screens for my platform with the Stitch MCP, and I want to prepare a clean design-system file first. Work inside this project folder, and explain what you understood before you write anything.

STEP 1 — GATHER MY DESIGN CONTEXT. Search this folder and read everything that describes how my product should look and feel: a design system, a brand or knowledge base, any brief or notes. Pull out the concrete details — exact colors (as hex), fonts, spacing, corner style, tone, and any component rules.

STEP 2 — ASK ONLY WHAT IS MISSING. If a key detail is not in my files (for example an exact hex color or a font name), ask me for it — one short question at a time. Do not ask about things you already found.

STEP 3 — WRITE DESIGN.md. Create a single file named DESIGN.md at the project root, in clean markdown: color roles with hex values (Primary, Background, Accent, Text), typography (font families and sizes), a spacing base unit, corner radii, and a one-line note on the overall feel. Prefer numbers over adjectives ("8px" beats "rounded"). Add a short RTL note: the product's content is Hebrew and should be right-to-left.

STEP 4 — FINISH. Show me the DESIGN.md and confirm it is saved at the project root.

Explain what you understood and wait for my approval before you write the file.
```

מה השגתם: קובץ DESIGN.md בתיקיית-הפרויקט — מקור-האמת של המותג שלכם, שקלוד ו-Stitch יקראו.

---

## צעד 4 — מייצרים את המסכים (בפרומפט אחד לקלוד)

עכשיו הקסם. מדביקים בקלוד קוד את התבנית המוכנה, ממלאים את הסוגריים לפי הפרויקט שלכם, ושולחים. קלוד מפעיל את Stitch דרך ה-MCP, מייצר את המסכים על-בסיס ה-DESIGN.md, מושך אותם, ושומר בתיקייה.

התבנית להעתקה (ממלאים את הסוגריים):

```
Use the Stitch MCP to design screens for my platform. Work in this project folder.

First, read the DESIGN.md in this folder and treat it as the source of truth for colors, fonts, and style.

Then generate these screens through Stitch, all with Hebrew content, all in the same style and color palette:
1. [מסך ראשון — למשל: מסך כניסה]
2. [מסך שני — למשל: רשימת הפריטים]
3. [מסך שלישי — למשל: מסך פריט בודד]

Context: this is [סוג הפלטפורמה] for [מי המשתמשים]; its purpose is [במשפט אחד]. Platform: [Web / Mobile].

Because the content is Hebrew, favor center alignment and avoid left-aligned labels that look wrong in RTL.

When the screens are ready: pull the screen images so I can see them, and save the generated code and the extracted design context into a "screens" folder in this project.
```

מה השגתם: מסכים על-המותג של הפלטפורמה שלכם — שנוצרו דרך קלוד, ויושבים כבר בתיקיית-הפרויקט.

בדיקה עצמית:
- יש תיקיית screens בפרויקט, עם הקוד והתמונות של המסכים.
- המסכים בסגנון המותג שלכם.

---

## צעד 5 — רואים ומלטשים

- **רואים:** מבקשים מקלוד להראות את תמונות המסכים, או פותחים אותן מתיקיית screens.
- **משנים:** אומרים לקלוד מה לתקן — **שינוי אחד בכל פעם.** כמה שינויים ביחד גורמים ל-Stitch לבנות מחדש ולשבור את הפריסה.
- **חוסכים:** ל-Stitch יש מכסה יומית שמתאפסת בחצות (שעון UTC). תיקונים קטנים וממוקדים חוסכים ממנה — לא מייצרים הכול מחדש בכל פעם.

---

## צעד 6 — רוצים לראות אותם מחוברים? (הצצה חיה)

התוצר האמיתי שלכם — המסכים, הקוד ומערכת-העיצוב — כבר בתיקייה, דרך קלוד. אבל אם בא לכם לראות את המסכים מחוברים כזרימה שאפשר ללחוץ בה, ל-Stitch יש תצוגה חזותית: נכנסים לפרויקט באתר, מחברים מסך למסך בלחיצה על אייקון החיבור, ולוחצים **Play** כדי לעבור ביניהם כמו באפליקציה.

זו הצצה נחמדה, לא חלק-חובה — חומר-העבודה שתביאו לכיתה כבר אצלכם בתיקייה.

---

## איפה עברית פוגשת את Stitch

‏Stitch כותב עברית, אבל מנוע-הפריסה שלו נוטה לשמאל-לימין. לכן אלה **סקיצות-כיוון** — הן מראות איך הפלטפורמה תיראה, לא המוצר המוגמר. את ה-RTL המלא בונים בשלב הקוד, בכיתה, עם BMAD. אם מסך יוצא הפוך, מבקשים מקלוד יישור-מרכז, או פשוט מקבלים אותו כסקיצה.

---

## מה בעצם קרה כאן

שימו לב לתמונה הגדולה: לא הקלקתם באתר של Stitch. דיברתם עם קלוד, וקלוד — דרך MCP — הפעיל כלי אחר לגמרי, משך ממנו מסכים, קוד ומערכת-עיצוב, והוריד הכול לתיקייה שלכם. זה בדיוק העולם שאליו הקורס חותר: כלי אחד מדבר עם כלי אחר דרך קלוד, והתוצר נוחת אצלכם מוכן. הסקיצה של היום היא הבסיס לקוד של מחר.

---

## התנסו — על הפרויקט שלכם או על Tuesday

הכי טוב לתרגל על הפלטפורמה **שלכם** — זו שתבנו ב-capstone. אבל אם אתם עדיין לא בטוחים מה בדיוק אתם בונים, אפשר להתאמן על החברה שאתם כבר מכירים מהקורס — Tuesday: מייצרים לה כמה מסכים ומתנסים בכל התהליך. העיקר — שתעברו את המסלול בידיים לפני הכיתה.

---

## אם נתקעתם

| מה קרה | מה עושים |
|---|---|
| יצירת מפתח Stitch נחסמה | ‏Stitch לפעמים חוסם יצירת-מפתח כהגנה אוטומטית — ממתינים ומנסים שוב, או משתמשים בחשבון Google אחר |
| ה-MCP של Stitch לא מתחבר בקלוד | מוודאים שהסביבה הטכנית מהיחידה על ההתקנות מוכנה, ושהמפתח הודבק בלי רווחים; סוגרים ופותחים את קלוד |
| המסך יצא בפריסה הפוכה (שמאל במקום ימין) | ‏Stitch נוטה ל-LTR בעברית. אלה סקיצות-כיוון — מבקשים מקלוד יישור-מרכז, או מקבלים; ה-RTL המלא נבנה בשלב הקוד בכיתה |
| נגמרו הקרדיטים היומיים | המכסה מתאפסת בחצות (שעון UTC). עד אז — מבקשים שינויים קטנים וממוקדים במקום ייצור-מחדש |
| הסגנון "קופץ" בין מסכים | מוודאים שה-DESIGN.md מסודר, ומבקשים "אותו סגנון וצבעים" בכל מסך חדש |

---

## מה הלאה

יש לכם מסכים — והם כבר בתיקיית-הפרויקט, יחד עם כל השאר: קול-מותג, בסיס-ידע, מערכת-עיצוב. חבילת-הפרויקט שלמה. בהכנה הבאה מסדרים את הסביבה הטכנית לרמה של הכיתה, ובכיתה מחברים את הכול ובונים את הפלטפורמה האמיתית עם BMAD.
