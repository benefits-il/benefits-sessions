---
type: class
unit: design-systems
session: 4
phase: בכיתה
num: "4.7"
parent: content/session-4/design-systems/index.html
parentLabel: מערכת עיצוב
title: בכיתה — מערכת עיצוב
studio: [Design]
downloads: [{"label":"מונחי חיפוש להשראה","href":"design-search-terms.md"},{"label":"פרומפט — מתמונה למערכת עיצוב","href":"image-to-ds-prompt.md"},{"label":"פרומפט — הלבשת המערכת על העמוד","href":"apply-ds-prompt.md"}]
links: [{"label":"המצגת מהכיתה","href":"https://benefits-il.dev/benefits-sessions-host/decks/session-4/design-systems/slides.html"},{"label":"מערכת העיצוב של TUESDAY","href":"https://benefits-il.dev/tuesday/design-system.html"},{"label":"העמוד לפני ואחרי — הדמו","href":"https://benefits-il.dev/tuesday/home-page-demo.html"}]
---

# בכיתה — מערכת עיצוב

## מה עשינו יחד

התחלנו מרעיון הזיהוי: מותג מזוהה בשני דברים — איך הוא מדבר ואיך הוא נראה. את הצד הראשון, קול המותג (brand voice), פגשתם בשיעור הקודם ובשיעורי הבית. היום השלמנו את הצד השני: מערכת העיצוב (design system) — הצבעים, הצורות והטיפוגרפיה שגורמים לכל תוצר שלכם להיראות שייך לאותו מקום. חברות עבדו שנים כדי לבנות את הזיהוי הזה; אתם בניתם אותו היום.

ראינו למה זה דחוף: רוב העמודים שנבנים עם AI נראים אותו דבר. אותם גופנים, אותם מעברי צבע, אותם כרטיסים. יש אפילו בדיחה שאומרת: כדי לדעת אם עמוד נבנה עם AI, בודקים כמה סגול וכחול יש בו. «ההבדל הוא לא הבקשה. ההבדל הוא ששנייה קיבלה את החוקים.»

עצרנו לשני משפטי תיאוריה, לא יותר: UX קובע איך זה עובד — איפה הכפתור נמצא ומה קורה אחרי הלחיצה. UI קובע איך זה מרגיש — הצבע של הכפתור, עיגול הפינות והצל.

ואז הגדרנו את הדבר עצמו. מערכת עיצוב היא ההחלטות שלכם, כתובות פעם אחת: לצבע יש תפקיד ולא רק שם, יש מקור אמת אחד שמעדכנים במקום אחד וכל העמודים מתעדכנים בעקבותיו, ולרכיבים יש מצבים — לכפתור יש מראה רגיל, מראה במעבר עכבר ומראה כשהוא כבוי.

מכאן המהלך של התחנה, בשלושה צעדים: תמונה ← מערכת ← הלבשה. מוצאים עיצוב שאוהבים, פרומפט ראשון הופך את התמונה לעמוד מערכת עיצוב שלם ואינטראקטיבי, ופרומפט שני מלביש את המערכת על העמוד שהעליתם בבית.

מה שצריך פתוח כדי לחזור על המהלך: VS Code עם הפאנל של קלוד קוד, ותיקיית העמוד מהבית — העמוד שהעליתם לאינטרנט ביחידת ההכנה. אם העמוד עוד לא באוויר, חזרו רגע ליחידת ההכנה והשלימו אותו קודם.

---

## 1 · חיפוש השראה — חמש דקות למצוא עיצוב שאוהבים

לא צריך לדעת לעצב כדי לבחור. חיפוש תמונות קצר, בתשע קטגוריות: כהה למפתחים · מינימליסטי · ברוטליסטי · מגזיני ויוקרתי · צבעוני ושובב · בנטו · זכוכית · רטרו · שטוח וגיאומטרי. הרשימה המלאה, עם מחרוזות החיפוש באנגלית לכל קטגוריה, נמצאת בהורדה «מונחי חיפוש להשראה» למעלה.

ההנחיה האחת: מצלמים את המקטע שאהבתם — הפתיח, הכרטיסים או הכפתורים — לא את כל העמוד. צילום מסך אחד טוב מספיק, ואפשר לעבוד בזוגות.

---

## 2 · פרומפט ראשון — מתמונה למערכת עיצוב

הפרומפט הזה הוא הרצה כבדה, השנייה בשיעור אחרי עמוד המוצר, ולכן הוא רץ על Opus כמו שם. כמו בעמוד המוצר, לא יושבים מול המסך בזמן שהוא בונה.

מצרפים את צילום המסך להודעה בקלוד קוד ומדביקים את הפרומפט המלא: הוא מזהה את סגנון העיצוב, מחלץ ממנו צבעים, טיפוגרפיה וצורות, ובונה עמוד מערכת עיצוב שלם ואינטראקטיבי. בצעד הראשון הוא שואל באיזו שפה לכתוב את העמוד — עונים עברית.

```
# Build a Complete, Style-Matched Design System from a Reference Image

You are a senior design engineer and design-systems specialist working in **Claude Code**. Attached to this message is a **reference image**. Your job is to produce a single, self-contained, interactive **Design System reference page** — a living component library in the spirit of Storybook — whose entire visual language is **derived from, and faithfully matched to, the attached image**.

Work in the exact order below. Do not skip steps, and **do not write any code before your plan is approved.**

---

## Step 0 — Ask one question first
Before anything else, ask me **one** question and wait for my answer:

> In which language should the Design System be written — **English (LTR)**, **Hebrew (RTL, `dir="rtl" lang="he"`)**, or **bilingual** (English component/token names + descriptions in a language I choose)?

Apply my answer to all page text and the layout direction. If bilingual, keep component names, token names, and code snippets in English and write the human-facing descriptions in the chosen language.

---

## Step 1 — Analyze the reference image (style detection)
Study the image and **classify its visual style** against known design languages. Name the closest match (or an explicit blend), and justify it in 3–6 short bullets citing concrete evidence from the image. Consider at least:

- **Glassmorphism** — translucent frosted panels, background blur, thin light borders, layered depth.
- **Neumorphism** — soft monochrome surfaces, dual (light + dark) extruded/inset shadows, very low contrast.
- **Brutalism / Neubrutalism** — raw high contrast, hard 2–4px borders, zero/low radius, solid offset drop shadows, oversized bold type.
- **Claymorphism** — puffy rounded 3D shapes, large radius, soft inner + outer shadows, pastel palette.
- **Minimalism / Swiss** — generous whitespace, monochrome + one accent, hairline borders, type-led hierarchy.
- **Flat / Material** — solid fills, subtle elevation shadows, bold accent, geometric.
- **Skeuomorphism** — realistic textures, gradients, bevels, physical metaphors.
- **Bento** — modular rounded card grid with varied tile sizes.
- **Editorial / Luxury** — serif display type, dramatic imagery, refined restraint, high contrast.
- **Dark / Developer** — near-black surfaces, a single neon accent, monospace accents, subtle glows.
- **Retro / Y2K** and **Playful / Colorful** — vibrant multi-color, organic shapes, pill-shaped components.

Then **extract exact design tokens** from the image:

- **Palette** (give hex values): background, surface(s), primary text/ink, muted text, borders, ONE (or a few) accent color(s), and semantic colors (success / warning / danger / info) tuned to fit the palette.
- **Typography**: serif vs sans vs mono, weight range, letter-spacing character. Pick matching **Google Fonts** (a display/heading face, a body face, and a monospace for code). If the chosen language is Hebrew or bilingual, pick fonts with strong Hebrew support (e.g., Rubik, Assistant, Heebo).
- **Shape language**: the border-radius scale, border thickness, and — most importantly — the **shadow/elevation model that defines this style** (glass blur, neumorphic dual-shadow, brutalist hard offset, flat soft elevation, or none).
- **Motion character**: e.g., smooth fades (glass/minimal), snappy/near-instant (brutalist), springy/bouncy (playful), restrained (editorial).
- **Density**: generous vs compact spacing.

Report your classification and extracted tokens back to me before planning.

---

## Step 2 — Plan (enter Plan Mode)
Enter **Plan Mode** and write a concise plan covering:

- The detected style and the concrete token values you will use, expressed as CSS custom properties (light + dark).
- The page shell and the full, ordered list of sections/components (the mandatory inventory below).
- How the detected style will be applied **consistently to every component** (buttons, cards, inputs, overlays — all coherent with the image).
- The single-file, no-build technical approach.

Then **call `ExitPlanMode` to request my approval. Do not write any code until I approve.**

---

## Step 3 — Build (only after approval)
Create ONE self-contained `design-system.html`.

### Architecture & shell
- Single file. All CSS in one inline `<style>`, all JS in one inline `<script>`. **No build step, no frameworks or libraries.** The only external resources are **Google Fonts** and **Tabler Icons** (webfont via CDN); provide a graceful system-font fallback if the CDN is offline.
- A **token layer** using CSS custom properties for the entire palette, spacing, radius, shadow, and type scale — every component inherits from it.
- **Light + dark themes** driven by a `[data-theme]` attribute, switched by a **toggle** in a sticky top bar, persisted in `localStorage`. Both themes must express the detected style.
- **Storybook-like layout**: a sticky top bar (logo + version tag + theme toggle); a **sidebar** containing a live **search filter**, grouped navigation, and **scrollspy** that highlights the active section on scroll; and a main "canvas" area where each component sits in a bordered specimen panel with a caption. On mobile the sidebar collapses into an off-canvas drawer with a hamburger toggle and a scrim.
- A hero section, a footer, a **back-to-top** button (appears on scroll), a toast region, and overlay roots.

### Mandatory component inventory
Group these in the sidebar exactly as listed. **Every item must be present**, and every one must be styled in the detected aesthetic (not a generic default).

- **Foundations**: Colors (click a swatch to copy its hex, with a toast), Typography (type scale + weight ramp + monospace sample), Spacing scale, Radius scale, Elevation/Shadow, Icons (a Tabler gallery — click an icon to copy its name).
- **Actions**: Buttons (variants primary / secondary / ghost / outline / danger × sizes sm / md / lg × states default / hover / active / disabled / loading, plus icon buttons and full-width), Button Group & Segmented control, Dropdown Menu (with separators and shortcut hints, closes on outside click), FAB & Speed Dial, Keyboard Keys (`kbd`).
- **Form Controls**: Inputs (text / textarea / select with default / focus / error / disabled), Input Add-ons (prefix / suffix / attached button), Search (with clear button), Password (show/hide toggle), Number Stepper, OTP / PIN (auto-advance between cells), Selection (checkbox / radio / switch), Autocomplete / Combobox (live filtering), Tags Input (add on Enter, remove on click), File Upload (click + drag & drop), Rating (interactive stars), Color Picker (native + brand presets), Date & Time (date / time / month), Slider (range with a live value readout).
- **Data Display**: Cards (basic / media / stat), List Group, Description List, Stats grid, Table (hover rows + status badges), Timeline, Tree View (expand/collapse), Calendar (real current month with prev/next navigation and day selection), Carousel (arrows + dots), Code Block (with copy), Avatar (sizes / status dot / group), Badges & Chips (removable), Empty State.
- **Navigation**: Navbar, Sidebar Nav, Tabs (working), Steps / Stepper (clickable), Breadcrumbs, Pagination (working), Command Palette (opens with **Ctrl/Cmd + K**, live filter, jumps to the chosen section), Bottom Navigation.
- **Feedback & Overlay**: Alerts (info / success / warning / danger, dismissible), Banner, Toast (triggerable), Modal (blurred overlay; close via button, overlay click, or ESC), Confirm Dialog, Drawer, Popover (closes on outside click), Tooltip (on hover), Progress (bar + spinner + skeleton), Circular Progress (ring), Loading Bar (top of page), Result / Status (success + error).
- **Layout**: Divider (plain / with text / vertical), Accordion (working), Blockquote.
- **Interactive**: a **Component Playground** — live controls (e.g., variant / size / state / label / icon toggles) that update a live preview and generate a copyable HTML snippet.

### Behavior & interactivity
Everything must actually work: theme toggle + persistence; sidebar search filter; scrollspy; reveal-on-scroll; tabs; accordion; modal / drawer / command-palette / confirm open + close (ESC and overlay click); dropdown and popover close on outside click; OTP auto-advance; autocomplete filtering; tags add/remove; file drag & drop; rating; color picker; number stepper; carousel; calendar; pagination; steps; toasts; and **copy-to-clipboard** (hex tokens, icon names, code snippets) using `navigator.clipboard` with an `execCommand` fallback so it also works from `file://`.

### Motion
Tasteful and subtle: fade/slide-in as sections enter the viewport (IntersectionObserver), smooth hover/press micro-interactions, a smooth theme transition, and gentle overlay enter/exit. **The motion character must match the detected style.** Nothing flashing or distracting. Fully honor `prefers-reduced-motion`.

### Quality bar
- Responsive — looks great on phone and laptop.
- Accessible — semantic HTML, visible focus states, keyboard operability, and `aria-*` on interactive/overlay elements.
- **No emojis anywhere** — use Tabler icons only.
- Clean, readable, consistently named code.
- The final page must be visibly, unmistakably in the **style of the reference image** — palette, typography, shapes, shadows, and motion all coherent.

---

## Step 4 — Open it
After building, open `design-system.html` in my default browser using the correct command for my OS — Windows PowerShell: `Start-Process design-system.html`; macOS: `open design-system.html`; Linux: `xdg-open design-system.html`.
```

סומכים על הצבעים ועל האווירה שהפרומפט מחלץ; גופנים וריווחים לפעמים דורשים סבב תיקון קצר, וזה חלק מהתהליך.

---

## 3 · פרומפט שני — הלבשת המערכת על העמוד מהבית

מדביקים בקלוד קוד בתוך תיקיית העמוד מהבית, יחד עם קובץ design-system.html שנוצר בפרומפט הראשון. הפרומפט רץ במצב Plan Mode: קלוד מסביר אילו החלטות עיצוב הוא חילץ ומה ישתנה בעמוד, ומחכה לאישור שלכם לפני שהוא נוגע בקבצים. לפני השינוי הוא שומר עותק של הגרסה הנוכחית בשם index.before-ds.html — שום דבר לא הולך לאיבוד.

```
You are a senior design engineer working in Claude Code. In this folder is a web page I built
(index.html — my GitHub Pages page). I am also giving you a design-system reference page
(design-system.html) that defines my visual language: colors, typography, spacing, radius,
shadows, and component styles.

MISSION: restyle my page to live fully inside this design system. Content stays; look changes.

STEP 1 — Read the design system page and extract its tokens: palette (exact hex), font stack,
spacing scale, radius, shadow/elevation model, and motion character.

STEP 2 — Plan Mode: explain what you understood — which tokens you extracted and what will
change on my page — and WAIT FOR MY APPROVAL before touching anything.

STEP 3 — Apply, strictly:
  - Every color used is a token from the system; every font from its stack; spacing on its
    scale. No inventions, no defaults — never fall back to generic AI design (no Inter/Roboto,
    no purple gradients, no cookie-cutter cards).
  - RESTYLE ONLY: do not rewrite, add, or remove content, sections, or functionality.
  - Keep the page valid, responsive, and accessible (focus states, contrast); honor
    prefers-reduced-motion.

STEP 4 — Safety: before changing index.html, save a copy of the current version as
index.before-ds.html in the same folder. Never delete any file.

STEP 5 — Open the restyled page in my default browser, and give me a short before/after list:
each visual decision and the token behind it.
```

התוכן נשאר בדיוק אותו תוכן; רק המראה מתחלף. מי שרוצה להלביש את עמוד המוצר מהתחנה הקודמת במקום העמוד מהבית — אפשרי, אבל המסלול שלימדנו הוא העמוד מהבית.

---

## 4 · ההדגמה — הסיפור של TUESDAY

ככה זה נראה כשזה עובד: מהלוגו של TUESDAY נולדה [מערכת עיצוב שלמה](https://benefits-il.dev/tuesday/design-system.html) — כהה עם צהוב — והעמוד הגנרי מהבית [לבש אותה](https://benefits-il.dev/tuesday/home-page-demo.html): אותו תוכן בדיוק, לפני ואחרי. אם ריצה נתקעה אצלכם בכיתה, הדמו הזה מראה לאן התהליך מגיע.

מי שלא הספיק לסיים — ממשיך בבית מאותה נקודה בדיוק. הכול קבצים בתיקייה: הצילום, עמוד המערכת והעמוד מהבית מחכים איפה שהשארתם אותם, ושני הפרומפטים שמורים להורדה בעמוד הזה.

---

## מה נשאר אצלכם ביד

- [ ] **צילום מסך** של עיצוב שאהבתם — ההשראה שממנה הכול התחיל.
- [ ] **עמוד מערכת עיצוב** אינטראקטיבי שנולד מהצילום, עם הצבעים, הגופנים והרכיבים שלכם.
- [ ] **העמוד מהבית לובש את המערכת** — אותו תוכן, מראה חדש ואחיד.
- [ ] **קובץ גיבוי** של הגרסה הקודמת (index.before-ds.html), למקרה שרוצים לחזור.

## המושגים של התחנה

| מושג | המשמעות |
|---|---|
| **UX** | איך זה עובד: איפה הכפתור נמצא ומה קורה אחרי הלחיצה. |
| **UI** | איך זה מרגיש: הצבע של הכפתור, עיגול הפינות והצל. |
| **מערכת עיצוב** | ההחלטות שלכם, כתובות פעם אחת: לצבע תפקיד, מקור אמת אחד, רכיבים עם מצבים. |
| **המהלך** | תמונה ← מערכת ← הלבשה: מצילום מסך אחד לעמוד שנראה שלכם. |

זה מה שנשאר אחרי שהמסכים נכבים: החלטות שנכתבות פעם אחת, שפה אחת לכל תוצר, ועמוד שנראה שלכם. «הפסקתי לריב עם ה-AI על איך זה נראה.»
