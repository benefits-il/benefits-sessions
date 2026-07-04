---
type: learning-chapter
unit: product-page
session: 4
phase: בכיתה
num: "4.6"
parent: content/session-4/product-page/index.html
parentLabel: עמוד המוצר
title: עמוד המוצר — הסרטון מהבית הופך לעמוד שמגיב לגלילה
studio: [Design, Operate]
---

# 🎬 הסרטון מקבל עמוד משלו

> פרק למידה · יחידת עמוד המוצר. נכתב מחומרי הכיתה של התחנה: עמוד הכיתה והפרומפט המלא.

## מה תדעו לעשות בסוף הפרק

לקחת תיקיית מותג וסרטון מוצר, ולהפוך אותם לעמוד נחיתה שבו הגלילה מנגנת את הסרטון — קדימה ואחורה — בעזרת פרומפט מוכן אחד בקלוד קוד. בדרך תבינו שני דברים שמחזיקים את כל התחנה: למה הכול חייב לשבת בתיקייה אחת מסודרת, ולמה אפקט הגלילה בנוי מפריימים שמצוירים על קנבס. ותצאו עם הרגל עבודה אחד חשוב: קלוד לא נוגע בקבצים לפני שהוא הציג תוכנית וקיבל מכם אישור.

**מה כדאי שיהיה פתוח:** VS Code עם הפאנל של קלוד קוד, תיקיית המוצר שלכם, והסרטון שיצרתם ביחידת ההכנה. אם אין לכם סרטון, ערכת TUESDAY עם סרטון מוכן נמצאת להורדה בעמוד הכיתה.

**על מה זה נשען:** על יחידות ההכנה של השיעור — סביבת העבודה של VS Code עם קלוד קוד, והסרטון מיחידת סרטון המוצר. הבונוס בסוף נשען גם על יחידת ההכנה של הטרמינל ושל git, זו שבה פרסמתם עמוד לאינטרנט.

**מפת הפרק:** מתחילים בעגינה — הצעד הקטן שמסדר את הכול לפני שמתחילים. ממשיכים לרעיון שמאחורי האפקט: פריימים על קנבס. אחר כך מריצים את הפרומפט המלא ועוברים את שער התוכנית של Plan Mode. וסוגרים באזור הנחיתה: איך ממשיכים בבית, ומה הבונוס למי שרוצה עוד.

---

## העגינה — הכול נהיה קבצים בתיקייה אחת

קלוד קוד עובד בתוך תיקייה. הוא רואה את מה שיש בה, ורק את מה שיש בה. והעמוד שאנחנו בונים נשען בדיוק על שני דברים שצריכים לשבת שם: חומרי המותג (מה המוצר, הצבעים, המשפטים) והסרטון שיצרתם בבית. לכן התחנה מתחילה בצעד שנקרא לו עגינה — מסדרים את התיקייה לפני שמבקשים ממנה משהו:

1. פותחים את תיקיית המוצר דרך **File ← Open Folder**. מהרגע הזה קלוד עובד בתוך התיקייה הזאת.
2. מעתיקים את הסרטון מהבית לתוך התיקייה.
3. משנים את שם הסרטון ל-hero.mp4.

למה שינוי השם חשוב? כי הפרומפט מחפש קודם כול קובץ בשם הזה. חצי דקה של סידור חוסכת את התקלה הנפוצה ביותר בתחנה — סרטון שלא נמצא. ואם אין לכם סרטון בכלל, לא נתקעים: מורידים את ערכת TUESDAY עם סרטון מוכן מעמוד הכיתה, ועובדים איתה.

**בדיקה עצמית:** מסתכלים בעץ הקבצים של VS Code. רואים זה לצד זה את קובצי המותג ואת hero.mp4? העגינה הושלמה. אם הסרטון לא מופיע בעץ — הוא לא בתיקייה, וקלוד לא ימצא אותו.

---

## פריימים על קנבס — הרעיון שמאחורי האפקט

מה בכלל רוצים להשיג: עמוד בסגנון של אפל, שבו הגולש גולל והסרטון של המוצר מתנגן פריים אחרי פריים, כאילו הגלילה היא שמנגנת אותו. הפרומפט בונה את זה משלושה חלקים, וכולם כתובים בו במפורש:

- הכלי ffmpeg מפרק את הסרטון לרצף של תמונות ממוספרות — בערך 120 עד 200 פריימים — ושומר גם את הפריים הראשון כתמונת פתיחה.
- העמוד מציג קנבס נעוץ: אזור ציור שנשאר קבוע על המסך בזמן שגוללים לאורך מקטע גבוה.
- הסקריפט ממפה את התקדמות הגלילה למספר פריים: תחילת המקטע היא הפריים הראשון, סוף המקטע הוא הפריים האחרון, וכל נקודה באמצע מקבלת את הפריים שלה.

זה כל הרעיון: כשכל רגע בסרטון הוא תמונה עם מספר, הגלילה שולטת בזמן. גוללים למטה — הסרטון מתקדם. גוללים למעלה — הוא חוזר אחורה. עוצרים — הוא נעצר בדיוק באותו פריים.

הפרומפט מוסיף לזה כמה החלטות איכות שכתובות בתוכו: כל פריים נטען ומפוענח פעם אחת בלבד, כדי שגם גלילה מהירה לא תיתקע; בטלפון נטענים פחות פריימים כדי לשמור על קלילות; ומי שהגדיר במערכת שלו העדפה להפחתת תנועה יקבל את תמונת הפתיחה, בלי אפקט.

**במילים שלכם:** עצרו רגע ונסו להסביר במשפט אחד למה מפרקים את הסרטון לתמונות במקום להשתמש בו כמו שהוא. תשובת מודל: כי הגלילה צריכה שליטה מדויקת בשני הכיוונים, וכשכל רגע בסרטון הוא תמונה ממוספרת, אפשר להצמיד כל מיקום גלילה לפריים אחד מסוים — קדימה ואחורה.

---

## שער Plan Mode — תוכנית לפני קוד

את הפרומפט מדביקים בקלוד קוד במצב Plan Mode, בתוך תיקיית המוצר. מה שקורה אחר כך בנוי כשרשרת של שלבים, והשער נמצא באמצע:

- קלוד שואל קודם שאלה אחת — באיזו שפה לכתוב את העמוד, עברית או אנגלית — ומחכה לתשובה.
- הוא קורא את קובצי המותג ומאתר את הסרטון, ומחויב להשתמש רק בעובדות שמצא בקבצים. אסור לו להמציא הבטחות, מחירים או המלצות; מה שחסר מקבל סימון ברור של ממלא מקום.
- הוא בודק ש-ffmpeg מותקן, מתקין אותו אם צריך, ומחלץ את הפריימים.
- ואז הוא עוצר: מציג תוכנית קצרה — אילו מקטעים יהיו בעמוד, אילו צבעים וגופנים נלקחו מחומרי המותג, ואיך רצף הפריימים יניע את החלק העליון — ומחכה לאישור שלכם לפני שהוא כותב שורת קוד אחת.
- גם הבטיחות כתובה בפרומפט: אסור לו למחוק או לדרוס קבצים קיימים. הוא כותב רק את הקבצים החדשים.

**עכשיו אתם:** העתיקו את הפרומפט, הדביקו בקלוד קוד במצב Plan Mode בתוך תיקיית המוצר, ענו על שאלת השפה, קראו את התוכנית — ואם היא משקפת את המותג שלכם, אשרו.

```
You are a senior web developer and motion designer working in Claude Code, inside my product
folder. Build me a scroll-driven product landing page, Apple style: as the visitor scrolls,
the product video plays frame by frame on a pinned canvas.

STEP 0 — One question first: ask me in which language the page should be written — Hebrew
(RTL, dir="rtl" lang="he") or English — then wait for my answer.

STEP 1 — Explore the folder: read the brand/product files (brand sheet, one-pager, README if
present) and find the product video — hero.mp4, or any .mp4 in the folder. Use ONLY facts
found in these files. Do not invent product claims, prices, or testimonials; if something is
missing, use a clearly marked placeholder like [TAGLINE].

STEP 2 — Frames: check that ffmpeg is available (run: ffmpeg -version). If it is missing,
install it with: winget install --id Gyan.FFmpeg -e --accept-source-agreements, and make sure
it is on PATH for this session. Then extract the video into an image sequence:
  ffmpeg -i hero.mp4 -vf "fps=30,scale=1600:-1" -c:v libwebp -q:v 80 -f image2 assets/frames/frame_%04d.webp
(-c:v libwebp with -f image2 is REQUIRED — without it ffmpeg writes one animated file instead
of a numbered sequence). Target 120-200 frames; adjust fps to the video length. Also save the
first frame as assets/poster.webp.

STEP 3 — Plan Mode: present a short plan — sections, palette and fonts taken from the brand
files, and how the frame sequence will drive the hero. Explain what you understood and WAIT
FOR MY APPROVAL before writing any code.

STEP 4 — Build exactly three files (index.html, style.css, script.js) plus the assets folder.
No build step. GSAP + ScrollTrigger + Lenis via their official CDN script tags are allowed.
  - Hero: a tall scroll section with a pinned canvas. Preload all frames; decode each frame
    ONCE into an ImageBitmap and draw only decoded bitmaps (never set img.src on scroll, never
    re-decode). Draw the nearest ready frame so fast scrolling never freezes. Cover-fit the
    canvas with a devicePixelRatio cap of 1.5.
  - Map scroll progress within the hero section to the frame index; scrub 0.6, anticipatePin 1.
  - Text overlays from the brand taglines fade in and out over the canvas at scroll points.
  - After the hero: what-it-is (from the one-pager), 3 selling points as cards, closing CTA.
    No generic pricing table.
  - Design: strictly the brand colors and type character from the brand sheet. Minimum body
    font 18px, mobile-first responsive, no emojis.
  - Mobile: load every 2nd frame under 768px and always include the exact last frame.
  - prefers-reduced-motion: show the poster frame, no scrubbing.
  - Accessibility: semantic tags, alt text, visible focus states.

STEP 5 — Safety: do not delete or overwrite any of my existing files. Write only the new
files and the assets/frames output.

STEP 6 — When done, open index.html in my default browser (Windows PowerShell:
Start-Process index.html) and give me one short paragraph: what you built and what I can
tweak next.
```

מה מקבלים בסוף: שלושה קבצים — קובץ index.html למבנה, קובץ style.css למראה וקובץ script.js להתנהגות — לצד תיקיית הפריימים. קלוד פותח את העמוד בדפדפן ומסכם בפסקה קצרה מה נבנה ומה אפשר לשפר.

**בדיקה עצמית — ככה נראית הצלחה, וככה מטפלים בתקלות:**

- הצלחה: העמוד נפתח, גוללים, והסרטון מתנגן קדימה ואחורה עם הגלילה.
- הסרטון לא נמצא ← בודקים את השם ואת המיקום: hero.mp4, בתוך תיקיית המוצר.
- עמוד לבן ← פותחים את קונסולת הדפדפן ומדביקים לקלוד את השורה האדומה הראשונה.
- חילוץ הפריימים נכשל ← מבקשים מקלוד להריץ שוב את בדיקת ffmpeg שמופיעה בפרומפט.
- התוצאה יצאה גנרית ← מפנים את קלוד חזרה לקובץ המותג ומבקשים לתקן לפי מה שכתוב בו.

ומי שרוצה עוד, הליטוש הוא פרומפט המשך אחד: בוחרים שיפור אחד ומבקשים במשפט — כותרת נוספת שמופיעה בגלילה, אפקט עומק לרקע, או שיפור לכפתור.

---

## אזור הנחיתה — ממשיכים מאותה נקודה

כאן נמצא יתרון שקט של העבודה בתיקייה: אף אחד לא נשאר מאחור. הכול קבצים — הפריימים שחולצו, התוכנית שאושרה, הקבצים שנכתבו. מי שלא סיים בכיתה פותח בבית את אותה תיקייה, באותו VS Code, וממשיך בדיוק מאותה נקודה.

והבונוס למי שסיים: לדחוף את העמוד לריפוזיטורי חדש ולהעלות אותו לאינטרנט, כמו שעשיתם ביחידת ההכנה. עמוד המוצר מפסיק להיות קובץ במחשב, ומתחיל להיות כתובת שאפשר לשלוח.

---

## מחברים הכול

אז מה היה לנו. התחלנו בעגינה: תיקייה אחת עם חומרי המותג והסרטון, והשם hero.mp4 שהפרומפט מחפש. הבנו את הרעיון שמאחורי האפקט: הסרטון מפורק לפריימים ממוספרים, קנבס נעוץ מצייר אותם, והתקדמות הגלילה ממופה למספר הפריים — ולכן הגלילה מנגנת את הסרטון בשני הכיוונים. הרצנו פרומפט מוכן אחד במצב Plan Mode, וראינו את השער בפעולה: שאלה על שפה, קריאה של חומרי המותג, תוכנית — ורק אחרי האישור שלכם, קוד. ובסוף נשארנו עם תיקייה שממשיכה איתנו הביתה, מאותה נקודה בדיוק.

---

## דף-עזר מהיר

| שלב | מה עושים |
|---|---|
| עגינה | פותחים את תיקיית המוצר דרך **File ← Open Folder**, מעתיקים את הסרטון פנימה ומשנים את שמו ל-hero.mp4. |
| הרצה | מדביקים את הפרומפט המוכן בקלוד קוד, במצב Plan Mode, בתוך תיקיית המוצר. |
| שער התוכנית | קלוד שואל על שפה, קורא את חומרי המותג, מציג תוכנית — ורק אחרי האישור שלכם כותב קוד. |
| בדיקה | פותחים את index.html בדפדפן וגוללים: הסרטון מתנגן קדימה ואחורה. |
| המשך | ממשיכים בבית מאותה נקודה; בונוס — ריפוזיטורי חדש ופרסום לאינטרנט. |

**הכלל:** העבודה שלכם היא לא לכתוב קוד. היא להכין תיקייה נכונה, ולאשר תוכנית טובה.

**לאן ממשיכים:** העמוד עובד. התחנה הבאה בשיעור עוסקת באיך דברים נראים — מערכת עיצוב.
