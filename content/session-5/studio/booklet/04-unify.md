---
type: booklet-page
unit: studio
session: 5
chapter: 4
title: תחנה 3 · Unify — מהן יחידות התפקוד?
---

## תחנה 3 — Unify: מהן יחידות התפקוד?

פס הייצור של התוכן שלי לתלמידים — התהליך שהופך כל שיעור מוקלט לתוצרים שנשלחים לתלמידים — נראה ככה: אחרי כל שיעור, הורדה של ההקלטה והעלאה ליוטיוב — אוטומטי לחלוטין. תמלול — סקיל. ניתוח של מה שהיה בשיעור — סוכן, כי זה דורש הבנה. שליחת המייל לתלמידים — אוטומטי. ארבע יחידות, כל אחת מהן היא עולם סגור עם העובד הנכון. וביחד: תהליך שרץ אחרי כל שיעור שאני מעביר, ומופעל על ידי משפט אחד כמו "סיימתי להעביר את שיעור 3 של קבוצה 2".

איך מגיעים לחיתוך כזה? זו בדיוק העבודה של התחנה הזאת — וזה הלב של השיטה, וגם החלק הכי קשה בה.

אתם לוקחים את כל מה שנאסף — הרצונות, הממצאים, החלקים — וחותכים אותו ל**יחידות תפקוד**: כל יחידה עושה דבר אחד ברור שאפשר להסביר במשפט. ועיקרון הברזל של החיתוך: **חותכים לפי הקשר, לא לפי גודל.** יחידה נכונה היא לא "משימה קטנה" — היא עולם תוכן סגור שנכנס לחלון צ'אט אחד: כל התוכן, ההקשר והדוגמאות שהיא צריכה כדי לחיות בזכות עצמה. והמבחן: אם ה-AI בחלון א' צריך מידע שקיים רק בחלון ב' — החיתוך שגוי. אתם חוזרים אחורה וחותכים אחרת.

ואחרי שחתכתם, אתם שואלים על כל יחידה: מי העובד הנכון פה?

- **בן-אדם** — החלטות גורליות, שיקול דעת, אישור סופי. מה שאסור להאציל.
- **סוכן AI** — עבודה שדורשת שיחה, ניתוח, שינוי מיקוד.
- **סקיל או אוטומציה** — עבודה פקידותית עם ידע קבוע, בלי דיונים. אל תבזבזו סוכן חכם על מה שסקיל מכני עושה באפס טעויות.

**בפועל:** אני מבקש מ-AI שרץ על תיקיית הפרויקט לתאר ולהסביר לי מה הוא מבין לגבי התהליך שרציתי לבנות. אחר כך אני מבקש ממנו להציע קודם כל את החלוקה לחלקים — ואני מסביר לו שכל חלק צריך להחזיק קונטקסט נפרד — ובסוף אני מבקש את המיפוי: מה פה זה בן-אדם, מה דורש סוכן, ומה יכול להיות סקיל או אוטומציה.

היחידות חתוכות. אבל אם כל אחת תיבנה בנפרד בלי שפה משותפת — אתם תקבלו ערימה של חלקים זרים. על זה מדברת התחנה הבאה.

---

## הפרומפט של התחנה

```
אני עובד לפי שיטת STUDIO — שיטה לתכנון ובנייה של תהליכים ומערכות עם
AI, בשש תחנות. בתיקיית הפרויקט יש קובץ בשם oven.md ("התנור"), ובראשו
הסבר מלא על השיטה. קרא אותו ואת כל מה שבתיקייה — כולל מסמך התוכנית
בתיקיית Target — לפני שאתה עונה.

אנחנו בתחנה 3 — Unify. השאלה שלה: מהן יחידות התפקוד?
זה הלב של השיטה: חותכים את הפרויקט ליחידות שכל אחת עושה דבר אחד ברור.
עיקרון החיתוך: לפי הקשר, לא לפי גודל — יחידה נכונה היא עולם תוכן סגור
שנכנס לחלון צ'אט אחד, עם כל התוכן, ההקשר והדוגמאות שהיא צריכה כדי
לחיות לבד.

1. קודם כל, תאר לי במילים שלך מה אתה מבין מהתהליך שאני רוצה לבנות —
   מהחלום ועד התוצר הסופי. אם משהו לא ברור או סותר — שאל לפני
   שממשיכים. זו גם בדיקה שלי: אם התיאור שלך לא תואם את מה שהתכוונתי,
   סימן שחסר מידע בתיקייה.
2. הצע חלוקה ליחידות תפקוד. לכל יחידה: שם, משפט אחד שמסביר מה היא
   עושה, ומה עולם התוכן שהיא צריכה כדי לעבוד לבד.
3. בדוק את החיתוך שלך במבחן החלונות: אם יחידה אחת זקוקה למידע שנמצא
   רק אצל יחידה אחרת — החיתוך שגוי. תקן והצע חיתוך אחר.
4. מפה כל יחידה — מי העובד הנכון:
   - בן-אדם: החלטות הרות גורל, שיקול דעת, אישור סופי.
   - סוכן AI: עבודה שדורשת שיחה, ניתוח, שיקול דעת.
   - סקיל או אוטומציה: עבודה קבועה בלי דיונים.
   נמק כל שיבוץ במשפט. אל תבזבז סוכן חכם על עבודה שסקיל מכני עושה
   באפס טעויות.
5. אם יחידה יוצאת גדולה או עמומה מדי — סמן אותה: היא מועמדת
   למיני-סטודיו משלה (כמוסבר בתנור).

בסיום: עדכן את התנור — משבצת Unify: רשימת היחידות והמיפוי של כל אחת.

תסביר מה הבנת ותחכה לאישור כדי להמשיך.
```

או, אותו פרומפט באנגלית:

```
I am working with the STUDIO method — a method for planning and building
processes and systems with AI, in six stations. In the project folder there
is a file named oven.md ("the oven"), and at its top a full explanation of
the method. Read it and everything in the folder — including the plan
document in the Target folder — before you answer.

We are at station 3 — Unify. Its question: what are the functional units?
This is the heart of the method: we cut the project into units, each doing
one clear thing. The cutting principle: by context, not by size — a correct
unit is a closed world of content that fits into a single chat window, with
all the content, context, and examples it needs to live on its own.

1. First, describe to me in your own words what you understand of the process
   I want to build — from the dream to the final output. If something is
   unclear or contradictory — ask before continuing. This is also a check for
   me: if your description does not match what I intended, it is a sign that
   information is missing from the folder.
2. Propose a division into functional units. For each unit: a name, one
   sentence explaining what it does, and what world of content it needs in
   order to work on its own.
3. Test your cut with the windows test: if one unit needs information that
   exists only in another unit — the cut is wrong. Fix it and propose a
   different cut.
4. Map each unit — who is the right worker:
   - Human: fateful decisions, judgment, final approval.
   - AI agent: work that requires conversation, analysis, judgment.
   - Skill or automation: fixed work with no discussions.
   Justify each assignment in a sentence. Do not waste a smart agent on work
   that a mechanical skill does with zero errors.
5. If a unit comes out too large or too vague — mark it: it is a candidate
   for a mini-studio of its own (as explained in the oven).

When done: update the oven — the Unify slot: the list of units and the
mapping of each one.

Explain what you understood and wait for my approval before continuing.
```

---

הקודם ← [תחנה 2 · Target](03-target.md) · הבא ← [תחנה 4 · Design](05-design.md)
