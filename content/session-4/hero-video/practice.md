---
type: practice
unit: hero-video
session: 4
phase: הכנה
num: "4.3"
parent: content/session-4/hero-video/index.html
parentLabel: סרטון ה-hero והתקנת ORBIT
title: בבית — סרטון ה-hero והתקנת ORBIT
studio: [Design, Operate]
video: none
downloads: [{"label":"תיקיית המותג Tuesday","href":"tuesday-brand-folder.zip"}]
---

# בבית — סרטון ה-`hero` והתקנת `ORBIT`

## מה אתם מכינים

זו ההכנה האחרונה לשיעור, ובה שתי משימות. הראשונה: סרטון אחד בולט — תמונת נושא נועזת שקמה לתחייה עם אפקט קיצוני, שבכיתה הופך לחלק העליון של דף נחיתה מבוסס-גלילה. השנייה: התקנת `ORBIT` בתוך `Claude Code`, כדי שבתחנת מאגר-הידע בכיתה הכול יהיה מוכן. שתיהן קצרות, ושתיהן חשובות לשיעור.

החלק הטוב: אתם לא כותבים או משנים שום פרומפטים. אתם בוחרים על מה זה יהיה, מדביקים פרומפטים מוכנים, ונותנים לכלים לעשות את העבודה. הכוח נמצא בפרומפטים, לא בכם.

### מה אתם צריכים קודם

- **`Claude Code`** מותקן ב-`VS Code` (מהיחידה הקודמת) — אתם תריצו איתו פרומפט על תיקייה.
- חשבון **`Google`** עבור `Google Flow` (חינמי). `Flow` הוא כלי סרטוני ה-`AI` של `Google`.

---

# חלק א — סרטון ה-`hero`

---

## שלב 1 — בחרו על מה זה יהיה

בחרו אחד:

- **המותג שלכם** — התיקייה שבניתם ביחידת ה-`Cowork`. כל מה שקשור למותג שלכם כבר נמצא שם.
- **`Tuesday`** (ברירת המחדל הקלה) — הורידו את **תיקיית המותג `Tuesday`** המוכנה בראש הדף הזה. בתוכה: פרטי המותג של `Tuesday` והלוגו שלו, מוכנים לשימוש.
- **מוצר מהאינטרנט** — בחרו כל חברה או מוצר שאתם אוהבים ושמרו תמונה אחת ברורה שלו (הלוגו שלו או צילום מוצר).

אם אין לכם מותג משלכם מוכן, פשוט השתמשו ב-`Tuesday`. לשם כך זה שם.

---

## שלב 2 — הכינו את תמונת הנושא

ראשית, פתחו את התיקייה שלכם ב-`Claude Code` — תיקיית מותג ה-`Cowork` שלכם, או תיקיית ה-`Tuesday` שהורדתם. הדביקו את הפרומפט הזה. קלוד קורא את המותג וכותב לכם פרומפט מוכן לתמונה:

```
Read every file in this folder to understand the brand — what it is, who it's for, its colors, its logo or mark, its taglines, and its voice.

Then write me ONE ready-to-paste image-generation prompt (for Gemini or GPT Image) that produces a single, exaggerated, cinematic HERO COVER IMAGE for this brand's website — the kind of over-the-top visual that stops the scroll.

The image prompt you write must specify:
- A wide 16:9 landscape composition, high resolution.
- The brand's product or service (or its logo/mark) as a bold, dramatised, larger-than-life hero.
- The brand's exact colors as the dominant palette, matching the brand's mood and personality.
- Premium, dramatic lighting, rich depth, and one striking "wow" moment — not a flat product shot.
- Clean negative space on one side so a headline can sit over it later.
- Absolutely NO text, letters, words, or watermarks baked into the image.
- A note that a reference image (the brand's logo or product) will be attached — tell the model to keep that mark faithful.

Output ONLY the finished image prompt, ready to copy. Nothing else.
```

עכשיו קחו את פרומפט התמונה ש-קלוד נתן לכם, ו:

1. פתחו את **`Gemini`** או **`ChatGPT`** (`GPT Image`).
2. הדביקו את פרומפט התמונה, ו**צרפו את הלוגו** (בתיקיית `Tuesday` זה `logo.png`; עבור המותג שלכם, צרפו את הלוגו או תמונת המוצר שלכם).
3. חוללו. אתם תקבלו תמונת נושא אחת רחבה ומוגזמת.
4. **הורידו את התמונה.**

> משתמשים במוצר מהאינטרנט במקום בתיקייה? פשוט הדביקו את אותו פרומפט תמונה ישירות לתוך `Gemini` או `ChatGPT`, צרפו את תמונת המוצר ששמרתם, והוסיפו שורה אחת: "`the attached image is the product — make it the hero.`"

---

## שלב 3 — הפיחו בה חיים ב-`Google Flow`

1. פתחו את **[`Google Flow`](https://labs.google/fx/tools/flow)** והתחילו סרטון חדש.
2. **העלו את תמונת הנושא שלכם** כרפרנס (אפשרות ה-`image-to-video`).
3. הדביקו את הפרומפט הזה **בדיוק כפי שהוא — אל תשנו אף מילה**:

```
Animate the attached image into a short, striking hero video for a website's scroll experience. Use the attached image exactly as the starting frame — do not add, remove, or change the subject.

Pick the ONE effect below that best and most logically fits what's in the image, and execute it in an extreme, cinematic, precisely-noticeable way:

1. Explosion — the subject bursts outward in a dramatic blast, then settles back.
2. Shatter — the image breaks into many flying pieces, then reassembles.
3. Exaggerated rotation — the subject spins in a bold, over-the-top 360 with motion.
4. Particle disintegration — the subject dissolves into particles and reforms.
5. Liquid-chrome morph — the surfaces flow and ripple like molten metal, then resolve.
6. Dramatic zoom and light burst — a fast push-in with a burst of light and lens flare.

Constraints: 16:9, about 8 seconds, smooth and loop-friendly, cinematic and premium, maximum visual impact for a scrolling website. No text, no subtitles, no watermarks. Choose only one effect — the one that suits the image best.
```

4. חוללו. `Flow` בוחר את האפקט שמתאים לתמונה שלכם ומכין את הסרטון. **הורידו אותו.**

> **הסירו את סימן המים.** סרטונים מ-`Google Flow` החינמי מגיעים עם סימן מים קטן. הסירו אותו בקליק אחד עם הכלי החינמי הזה — [online-video-cutter.com/remove-logo](https://online-video-cutter.com/remove-logo): העלו את הסרטון שלכם, הורידו את הגרסה הנקייה, וזו הגרסה שאתם מביאים לכיתה.

---

## שלב 4 — שמרו את זה לכיתה

שמרו את הסרטון (ו, אם השתמשתם במותג משלכם, שמרו את הבסיס — שם, מה זה עושה, צבעים). זה מה שאנחנו בונים סביבו את דף נחיתת הגלילה בכיתה.

---

## אם משהו נתקע בסרטון

- **התמונה יצאה שטוחה או משעממת?** הריצו את פרומפט תמונת הנושא שוב — קלוד יכתוב אחד קצת שונה בכל פעם. או חוללו את התמונה פעם שנייה ב-`Gemini` / `ChatGPT`; אתם תקבלו וריאציות.
- **האפקט לא היה דרמטי מספיק?** חוללו את סרטון ה-`Flow` שוב — הוא עשוי לבחור אפקט אחר. קיצוניות היא המטרה.
- **אין לוגו למותג שלכם?** דלגו על תמונת הרפרנס; פרומפט תמונת הנושא עדיין עובד מטקסט המותג בלבד.
- **משהו אחר?** צלמו מסך לקבוצה ואנחנו נסדר את זה לפני הכיתה.

---

# חלק ב — התקנת `ORBIT` ב-`Claude Code`

`ORBIT` הוא אוסף הסקילים שבנינו בשיעור הקודם. בכיתה נשתמש בו בתוך `Claude Code` כדי לבנות מאגר ידע לעסק — ולכן הוא צריך להיות מותקן שם מראש. ההתקנה לוקחת דקה, וקלוד עושה את רובה בעצמו.

## הדרך הקלה — נותנים לקלוד להתקין

פותחים את `Claude Code` בכל תיקייה, ומדביקים את הפרומפט הזה כמו שהוא:

```
Install the ORBIT plugin in Claude Code so it is available globally, in every project (user-level install).
The plugin lives here: https://github.com/benefits-il/orbit-plugin

Do this:
1. Add the marketplace: run  /plugin marketplace add benefits-il/orbit-plugin
2. Install the plugin from it: run  /plugin install orbit@orbit-plugin
3. If the marketplace path fails, download the zip from
   https://github.com/benefits-il/orbit-plugin/releases/latest/download/orbit-plugin.zip
   and install it as a personal plugin from file.
When you are done, list which ORBIT skills are now installed so I can confirm it worked.
```

קלוד יריץ את הצעדים ויסיים ברשימת הסקילים המותקנים. אם רואים ברשימה שמות כמו `boomerang`, `kb-builder` ו-`design-pipeline` — מוכנים.

## הדרך הידנית (גיבוי, אם הפרומפט לא הסתדר)

### דרך 1 — דרך ה-`marketplace`

1. נכנסים ל-**Customize**, ללשונית **Plugins**.
2. באזור **Personal plugins** לוחצים על הפלוס, ובוחרים **Add marketplace**.
3. בשדה הכתובת מדביקים את הספרייה הזאת:

```
benefits-il/orbit-plugin
```

4. לוחצים **Browse plugins**, ומתוך הספרייה מתקינים את הפלאגין של `ORBIT`.

### דרך 2 — מורידים קובץ ומתקינים ממנו

אם ה-`marketplace` לא נפתח או נתקע, אפשר להוריד את הפלאגין כקובץ ולהתקין אותו ישירות:

1. מורידים את קובץ הפלאגין: [הורדת `ORBIT` plugin](https://github.com/benefits-il/orbit-plugin/releases/latest/download/orbit-plugin.zip).
2. ב-**Customize ← Plugins**, באזור **Personal plugins**, לוחצים על הפלוס ובוחרים להוסיף פלאגין מקובץ.
3. בוחרים את ה-zip שהורדתם, וההתקנה רצה.

**אם אזור Personal plugins ריק, או שאין בכלל כפתור Add marketplace:** האזור הזה מופיע רק אחרי שכבר מותקן אצלכם plugin אחד כלשהו. הפתרון פשוט: מתקינים קודם plugin אחר כלשהו, וברגע שיש אחד מותקן — האזור נפתח וכפתור Add marketplace זמין. זה באג ידוע ב-`Claude`, לא תקלה אצלכם.

## בדיקה — לוודא שזה עבד

בכל תיקייה ב-`Claude Code`, מדביקים את משפט הבדיקה:

```
בדוק אילו סקילים של ORBIT מותקנים אצלך והצג רשימה קצרה.
```

רואים ברשימה את סקילי `ORBIT` — וזהו, אתם מוכנים לכיתה.
