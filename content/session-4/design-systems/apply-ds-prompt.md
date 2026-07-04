מדביקים בקלוד קוד בתוך תיקיית העמוד מהבית, יחד עם קובץ מערכת העיצוב שנוצר בפרומפט הראשון.

---

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
