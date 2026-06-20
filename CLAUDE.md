# benefits-sessions — סוכן תחזוקה

זה הריפו של **אתר המסירה של קורס Benefits**. אתר HTML סטטי שמרנדר תוכן Markdown לעמודים מעוצבים בשפת Benefits, מתארח ב-`benefits-il.dev/benefits-sessions`. כשבן אומר "תוסיף יחידה / תוסיף מפגש / תעדכן תוכן" — אתה עורך את הקבצים, מראה לבן, ורק באישורו דוחף.

## איך האתר עובד (שתי שכבות)

- **מנוע** `viewer.html` — מרנדר כל MD דרך `viewer.html?doc=<נתיב>`. תומך בכל Markdown (טבלאות, Mermaid, קוד מודגש + כפתור העתקה, RTL/LTR), וקורא frontmatter כדי לבנות כותרת, סלוט סרטון, הורדות וניווט. **אל תיגע בו אלא אם מוסיפים יכולת מנוע חדשה.**
- **קליפה סטטית** — `index.html`, `sessions.html`, `session-<N>.html`, ו-`content/.../index.html` (hub). HTML ביד, נשען על `delivery.css`.

החוזה המלא לכתיבת תוכן: `CONTENT-CONTRACT.md`. קרא אותו לפני כל הוספה.

## להוסיף יחידה חדשה (workflow)

1. צור `content/session-<N>/<unit-slug>/`.
2. כתוב `practice.md` ו-`learning-chapter.md` עם frontmatter תקין (ראה CONTENT-CONTRACT) — `type`, `title`, `session`, `unit`, `parent`, `parentLabel`, `studio`, ולתרגול גם `video: TBD`.
3. העתק קבצי הורדה (תמלול / מאגר / PDF) לאותה תיקייה; ודא שה-`href` ב-`downloads` יחסי ומצביע אליהם.
4. צור `index.html` (hub) בהעתקת hub קיים — עדכן כותרת, chip STUDIO, ושני קישורי `../../../viewer.html?doc=…`.
5. הוסף `unit-card` לעמוד המפגש ברצועה הנכונה.
6. screenshot-verify מקומית (`npx serve`) לפני שמראים לבן.

## להוסיף מפגש חדש

1. צור `session-<N>.html` בהעתקת `session-2.html` — שלוש רצועות (הכנה · בכיתה · בבית), עדכן כותרת ותוכן.
2. ב-`sessions.html`, החלף את כרטיס ה-stub של אותו מפגש בקישור פעיל.
3. הוסף את היחידות שלו תחת `content/session-<N>/`.

## כללי בית

- עברית-first, חיצים שמאלה ←, בלי אימוג'ים (אלא בתוכן Story קיים), בלי ערבוב עברית-אנגלית באמצע משפט.
- `tokens` ו-`delivery.css` נשארים גנריים — ריפו תאום (מנחה-בלבד) אמור לרשת אותם נקי. אל תכניס ל-`delivery.css` שום דבר ספציפי לשיעור.
- אל תשלח שום דבר החוצה ואל תדחוף ל-git בלי אישור בן.
- screenshot-verify לפני "מוכן".

## אירוח

push ל-`benefits-il/benefits-sessions` (main) ← GitHub Pages מתעדכן תוך כדקה ב-`benefits-il.dev/benefits-sessions/`. דורש `.nojekyll` ו-`CNAME` (benefits-il.dev) בשורש — כבר קיימים.
