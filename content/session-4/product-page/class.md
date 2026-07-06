---
type: class
unit: product-page
session: 4
phase: בכיתה
num: "4.6"
parent: content/session-4/product-page/index.html
parentLabel: עמוד המוצר
title: בכיתה — עמוד המוצר
studio: [Design, Operate]
downloads: [{"label":"ערכת TUESDAY — תיקיית מותג עם סרטון","href":"tuesday-brand-folder.zip"}]
links: [{"label":"סרטוני TUESDAY לגיבוי","href":"https://benefits-il.dev/tuesday/videos/"}]
---

# בכיתה — עמוד המוצר

בבית יצרתם סרטון למוצר. עכשיו המוצר מקבל עמוד משלו. אני מדגים על TUESDAY, ואתם עובדים על מה שבחרתם — המותג שלכם, TUESDAY מהתיקייה של הבית, או מוצר מהאינטרנט. בסוף התחנה יהיה לכם עמוד נחיתה שהסרטון שלכם חי בראשו, עם אפקט הגלילה שראיתם אצלי.

## מה מכינים לפני שמתחילים

- VS Code פתוח עם הפאנל של קלוד קוד, כמו ביחידת ההכנה.
- תיקיית המוצר מהבית פתוחה דרך **File ← Open Folder**.
- מעתיקים את הסרטון לתוך תיקיית המוצר ומשנים את שמו ל-hero.mp4 — חצי דקה, וזה חוסך את רוב התקלות.
- אין סרטון? מורידים מעמוד זה את ערכת TUESDAY עם סרטון מוכן, או עובדים עם השכן.
- אין מה להכין מראש: קלוד מתקין את ffmpeg לבד אם צריך, כחלק מהפרומפט.

---

## הפרומפט

מדביקים בקלוד קוד, במצב Plan Mode, בתוך תיקיית המוצר. קלוד ישאל באיזו שפה לכתוב את העמוד, יציג תוכנית, ויחכה לאישור לפני שהוא נוגע בקבצים. אחרי שמאשרים את התוכנית, מחליפים חזרה ל-Bypass permissions (Shift יחד עם Tab) כדי שהבנייה תרוץ ברצף עד הסוף בלי לעצור על כל אישור.

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

---

## מה הולך לקרות

קלוד שואל על שפה ← קורא את חומרי המותג ומוצא את הסרטון ← מחלץ פריימים (דקה-שתיים) ← מציג תוכנית ← מאשרים ומחליפים חזרה ל-Bypass permissions ← הקבצים נוצרים ← הפרומפט פותח את index.html בדפדפן וגוללים. הסרטון מתנגן עם הגלילה, קדימה ואחורה. את התוצר פותחים על המסך שלכם, מהמחשב שלכם, ולא צופים בו דרך שיתוף-מסך של המנחה.

## ליטוש (רשות, פרומפט המשך אחד)

בוחרים שיפור אחד ומבקשים במשפט — כותרת נוספת שמופיעה בגלילה, אפקט עומק לרקע, או שיפור לכפתור.

## נקודת המשך

מי שלא סיים ממשיך בבית מאותה נקודה — הכול קבצים בתיקייה. בונוס לבית: לדחוף את העמוד לריפוזיטורי חדש ולהעלות אותו לאינטרנט, כמו שעשיתם ביחידת ההכנה.

---

## רשימת בדיקה לסוף התחנה

- [ ] **הסרטון** יושב בתיקיית המוצר בשם hero.mp4.
- [ ] **תיקיית הפריימים** נוצרה — בתוך assets/frames יש רצף קבצים ממוספרים.
- [ ] **שלושת הקבצים** קיימים בתיקייה: קובץ index.html, קובץ style.css וקובץ script.js.
- [ ] **העמוד נפתח בדפדפן**, והסרטון מתנגן עם הגלילה קדימה ואחורה.
- [ ] **מי שלא סיים** — התיקייה שמורה כמו שהיא, וממשיכים בבית מאותה נקודה.
