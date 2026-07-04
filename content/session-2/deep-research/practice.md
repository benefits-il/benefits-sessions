---
type: practice
unit: deep-research
session: 2
phase: הכנה
num: "2.5"
globalIndex: 8
parent: content/session-2/deep-research/index.html
parentLabel: Deep Research
title: תרגול — Deep Research
studio: [Scout]
video: C8fuafuVgeY
downloads: [{"label":"research-architect (הסקיל)","href":"https://github.com/benefits-il/orbit-plugin/releases/latest/download/research-architect.zip"}]
en: practice.en.md
links: [{"label":"Claude","href":"https://claude.ai"},{"label":"ChatGPT","href":"https://chatgpt.com"},{"label":"Gemini","href":"https://gemini.google.com/app"},{"label":"Perplexity","href":"https://perplexity.ai"},{"label":"DeepSeek","href":"https://chat.deepseek.com"},{"label":"Grok","href":"https://grok.com"},{"label":"Arena","href":"https://arena.ai"}]
---

# תרגול — Deep Research

## לפני שמתחילים

בסרטון ראיתם מה זה Deep Research, ולמה הוא לא צ'אט ולא גוגל אלא משהו שלישי: סוכן שיוצא לאינטרנט, חוקר באמת, וחוזר עם דוח מצוטט. עכשיו תתנסו בו בעצמכם. שלושה תרגילים: מתקינים את הסקיל שכותב לכם את תוכנית המחקר, מריצים מחקר אמיתי בכמה כלים במקביל ושומרים אותו, ומסדרים לעצמכם את נוף הכלים.

באים לכיתה אחרי שכבר התנסיתם, אז במפגש נוכל לרוץ ישר על מה שאספתם.

מה שכדאי שיהיה פתוח: חשבון Claude, וגישה לעוד כלי מחקר אחד לפחות.

---

## איפה נמצא Deep Research, ומי באמת עושה אותו

בכל כלי הפיצ'ר הזה מתחבא קצת במקום אחר, אבל בדרך כלל הוא יושב בחלון הצ'אט, בתוך התפריט שנפתח מכפתור הפלוס (+). ברוב הכלים הוא נקרא Deep Research, ובקלוד דווקא Research. כשתפתחו כלי חדש, חפשו אותו שם.

כדאי גם להבחין בין שני סוגי כלים. יש כלים שרק מחפשים באינטרנט ומביאים מקורות במהירות, כמו DeepSeek, Grok ו-Arena. ויש כלים שעושים Deep Research אמיתי, כלומר בונים תוכנית, יוצאים לחיפוש לעומק, ומסנתזים דוח מצוטט, כמו Claude, ChatGPT, Gemini ו-Perplexity. נשתמש בשני הסוגים: החיפוש המהיר טוב לבדיקה זריזה, וה-Deep Research למחקר של ממש.

---

## תרגיל 1 — מתקינים את research-architect

אתם כבר יודעים להתקין סקיל. עכשיו מתקינים את **research-architect**, סקיל עם תפקיד אחד בלבד: לקחת נושא ולהחזיר תוכנית מחקר מסודרת, כדי שלא תצטרכו לכתוב אחת כזאת ביד אף פעם.

1. הורידו את הסקיל מעמוד ORBIT, באופציה "הורד רק את הסקיל": https://github.com/benefits-il/orbit-plugin/releases/latest/download/research-architect.zip
2. התקינו אותו ב-Claude: Settings ← Skills ← Upload skill ← בחרו את קובץ ה-ZIP.
3. בחנו אותו: תנו לו נושא לדוגמה, למשל "השוק של X", וודאו שהוא מחזיר תוכנית עם חמשת השדות:
   - **Goal** — מה תעשו עם הדוח בסוף.
   - **Main question** — השאלה הראשית.
   - **Sub-questions** — שלוש עד חמש שאלות משנה.
   - **Scope** — איפה לחפש, ומה מחוץ לטווח.
   - **Output format** — פורמט הפלט.

אם קיבלתם תוכנית עם כל חמשת השדות, הסקיל עובד. זאת אותה תוכנית שהייתם צריכים לכתוב ביד לפני כל הרצה.

---

## תרגיל 2 — Deep Research על עולם ה-Deep Research

עכשיו מריצים מחקר אמיתי, והנושא הוא Deep Research עצמו: אילו כלים קיימים ומה מייחד כל אחד. את התוצאה תשמרו לקובץ, ניקח אותו איתנו לכיתה.

**צעד 1 — תוכנית.** פתחו את research-architect והדביקו את הפרומפט הזה. הוא יבקש מהסקיל לבנות תוכנית מחקר על עולם ה-Deep Research:

```
אני רוצה לייצר תוכנית מחקר בעזרת research-architect כדי לחקור את עולם ה-Deep Research:
אילו כלים קיימים שעושים מחקר עמוק, מה כל אחד, ומה הייחוד שלו. תן דגש על Perplexity,
Grok, Qwen, Arena, Gemini ו-Claude. תבנה תוכנית מחקר מסודרת עם מטרה, שאלה ראשית,
תתי-שאלות, היקף ופורמט פלט. תסביר מה הבנת וחכה לאישור כדי להמשיך.
```

הסקיל ישאל אתכם רק את שפת הפלט, ואז יחזיר תוכנית מסודרת. אשרו וקחו אותה.

**צעד 2 — הרצה בכמה כלים.** קחו את התוכנית שיצאה, והריצו אותה כ-Deep Research גם בקלוד וגם בג'מיני. מתחילים את שתי ההרצות, ולא מחכים לאחת לפני שמתחילים את השנייה. כל כלי רץ לבד כמה דקות, ובינתיים אתם פנויים.

**צעד 3 — קוראים ושומרים.** כשההרצות חוזרות, קראו את שני הדוחות, ושמרו את התוצאות לקובץ MD אחד על המחשב. זה מאגר המידע הראשון שלכם, שנאסף משני מקורות שונים. שמרו אותו במקום שתמצאו, כי ניקח אותו לכיתה ונעבוד עליו שם.

---

## תרגיל 3 — נוף הכלים

עכשיו נסדר את כל מה שאספתם. ובמקום שאנחנו נספר לכם מה כל כלי עושה, ניתן למחקר שלכם לעשות את זה.

פתחו שיחה חדשה, הדביקו לתוכה את שני דוחות המחקר ששמרתם בתרגיל 2 (של ג'מיני ושל קלוד), ואחריהם את הפרומפט הזה:

```
מצורפים שני דוחות מחקר על עולם ה-Deep Research. עבור עליהם, וחלץ מהם את כל הכלים
שמופיעים. הצג לי טבלה ברורה עם עמודה לכל אחד מאלה: שם הכלי, האם הוא עושה Deep
Research אמיתי או רק חיפוש באינטרנט, מה ייחודי בו, והאם הוא דורש הרשמה. בסוף הטבלה,
סמן אילו כלים הכי שווה לי לפתוח ולהתחיל לעבוד איתם. הסבר מה הבנת וחכה לאישור כדי להמשיך.
```

קיבלתם טבלה שמסכמת את כל נוף הכלים, מהמחקר שאתם הרצתם, לא מרשימה מוכנה שנתנו לכם.

ועכשיו פתחו לפחות חמישה מהכלים, ושמרו אותם בתיקיית מועדפים בשם "Deep Research" בדפדפן, כדי שיהיו לכם ביד במקום אחד. כמה כלים נגישים בלי הרשמה או בהרשמה מהירה:

- **עושים Deep Research אמיתי:** [Claude](https://claude.ai) · [ChatGPT](https://chatgpt.com) · [Gemini](https://gemini.google.com/app) · [Perplexity](https://perplexity.ai).
- **חיפוש מהיר באינטרנט:** [DeepSeek](https://chat.deepseek.com) · [Grok](https://grok.com) · [Arena](https://arena.ai).

---

## עוד כלים לחקור, אם בא לכם

רוצים להציץ רחוק יותר? יש עוד שכבה שלמה של כלים שיודעים לחפש ולחקור, חלקם שמות שכנראה לא פגשתם. שום דבר מהם לא נדרש כדי לסיים את התרגיל ← זאת פשוט המפה המלאה, אם בא לכם לשוטט בה. אלה הכלים שאני עצמי מסתובב ביניהם:

[Jina](https://search.jina.ai/) · [Consensus](https://consensus.app/) · [Elicit](https://elicit.com/) · [Undermind](https://app.undermind.ai/) · [Semantic Scholar](https://www.semanticscholar.org/) · [SciSpace](https://scispace.com/) · [Scite](https://scite.ai/) · [You.com](https://you.com/home) · [Exa](https://exa.ai/) · [Perplexity](https://www.perplexity.ai/) · [DeepSeek](https://chat.deepseek.com/) · [Grok](https://grok.com/) · [Mistral](https://chat.mistral.ai/chat) · [Qwen](https://chat.qwen.ai/) · [MiniMax](https://agent.minimax.io/) · [Claude](https://claude.ai/new) · [Gemini](https://gemini.google.com/app) · [Arena](https://arena.ai/) · [NotebookLM](https://notebooklm.google.com/) · [ChatGPT](https://chatgpt.com/)

---

## חומרים ולינקים

- **research-architect** — [הורד רק את הסקיל](https://github.com/benefits-il/orbit-plugin/releases/latest/download/research-architect.zip).
- **הכלים:** [Claude](https://claude.ai) · [ChatGPT](https://chatgpt.com) · [Gemini](https://gemini.google.com/app) · [Perplexity](https://perplexity.ai) · [DeepSeek](https://chat.deepseek.com) · [Grok](https://grok.com) · [Arena](https://arena.ai).
