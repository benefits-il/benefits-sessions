# Prep — Cowork

## The unit video

<!-- video set: xoH6zsQaL1U (youtu.be/xoH6zsQaL1U, unlisted) — the engine builds the embed from video: in the frontmatter when this moves to the site -->

## Before we start

Up to now you've worked with Claude in the browser. Cowork is the moment everything you already know — the agents, the skills, the connectors — steps out of the browser and works directly on the real files sitting on your computer. That's the whole story. Before we see it run, a few unhurried minutes of setup.

What needs to be ready:

- **Claude Desktop** installed and up to date, on Mac or Windows. Cowork lives in the app, not in the browser — claude.ai in Chrome is not Cowork.
- **A Pro plan or higher.** Without it the Cowork tab simply won't appear.
- **The demo pack**, downloaded from [benefits-il.dev/cowork-demo](https://benefits-il.dev/cowork-demo), unzipped and saved in a separate folder.
- One setting in Settings you'll need to switch on — we'll get to it in a moment.

And a word on safety: Cowork touches real files. On your first run, work on **the demo folder only**, or on a backed-up copy. It asks permission to read, edit, and delete only inside the folder you choose, so hand it exactly the yard it's allowed to play in — not your whole Documents.

## What's in the pack

The demo pack is fictional practice files, arranged in seven numbered sub-folders:

- **0-mess-drawer** — a mixed pile to sort.
- **1-receipts** — receipts and invoices.
- **2-form** — a form to fill in plus a details file.
- **3-docs-to-summarize** — a few documents on one topic.
- **4-transcript** — a meeting transcript.
- **5-spreadsheet** — a raw data sheet.
- **6-to-translate** — a document to translate.

## Setup — install and aim Cowork

Three steps, and you're done:

1. Install or update Claude Desktop from claude.com/download, and open the **Cowork** tab. Make sure you're in Cowork and not in a regular chat — only in Cowork do the outputs get saved as files. If something "runs" but no file appears, you were in a chat.
2. In **Settings**, under **Capabilities**, switch on **Code execution and file creation** — the toggle that powers the skills which produce Excel, PowerPoint, Word, and PDF.
3. Set **the demo folder** as the working folder, and make sure it really got selected — Cowork shows the name of the active folder. This is where it reads and writes, and only here.

That's it. Now for the fun part.

---

## Station 1 — a task that runs by itself

The idea: you write once what to do, and Cowork runs it on its own on a schedule and leaves you a result every time. Try it on the demo folder. Paste:

```
Every morning at eight, go through the 0-mess-drawer sub-folder and write me a short brief of what changed since yesterday, into a file called morning-brief.md. Don't delete any file.
```

Note one important thing: the task runs **only when the computer is awake and Claude Desktop is open** — this is not a cloud that runs around the clock. If the computer is asleep or the app is closed at eight in the morning, the task simply waits and runs when you open it.

## Station 2 — give Cowork a goal, and watch it plan

Here you don't give steps, you give **one desired result**, and Cowork decides on its own how to get there. But before it touches anything it stops, shows you a plan, and you approve. It's worth seeing this safety gate work. Paste:

```
Organize the 0-mess-drawer sub-folder by topic, and show me a plan before you touch anything.
```

Read the plan it shows you, and only then approve. That's the habit that keeps you safe: see first, then let it act.

## Station 3 — turn your files into a professional deliverable

This is the heart of it. The moment you switched on the setting from setup, Cowork has built-in skills that know how to read a pile of files and hand back a professional deliverable — a spreadsheet, a presentation, a document, a filled-in form. Below is a pool of a few runs. **You pick what speaks to you** and run as many as you like. I'd start with the first one — it's the most satisfying the first time.

Each run lists which files it needs (they're all waiting, marked in the demo pack) and a ready prompt to copy. Every prompt ends with an instruction not to delete anything and to produce the deliverable in a new file, so the original stays whole.

### ★ Receipts and invoices → an Excel spreadsheet (recommended to start)

A messy pile of receipts and invoices turns, in a couple of minutes, into a sorted table with a summary row and a breakdown by category.
Files in the folder: PDF files of invoices, and photos of receipts (JPG or PNG).

```
Go through all the receipts and invoices in the 1-receipts sub-folder, extract from each one the supplier, date, amount, and category, and build a sorted Excel spreadsheet with a summary row and a breakdown by category. Don't delete any file, create the spreadsheet as a new file.
```

### Filling in a PDF form

A tedious form fills itself in seconds, from a details file you provide.
Files in the folder: a blank PDF form, and a details file (text, Word, or Excel).

```
Fill in the form in the 2-form sub-folder using the details in the data file, and save it as a new PDF file. Don't delete any file.
```

### A pile of documents → one executive summary

Several separate documents on one topic turn into a single page of "the big picture and the decisions."
Files in the folder: three to five PDF or Word files on a shared topic.

```
Read all the documents in the 3-docs-to-summarize sub-folder and produce one document: an executive summary, key points from each document, and a comparison table if relevant. Don't delete any file, create the summary as a new file.
```

### A meeting transcript → a summary and a task table

Dozens of pages of transcript turn into a single page of "what was decided and who does what."
Files in the folder: a transcript file (text or Word), for example an export from Zoom or Teams.

```
Read the transcript in the 4-transcript sub-folder and produce a document with four parts: a three-line summary, the decisions that were made, a task table with an owner and a due date, and next steps. Don't delete any file, create the document as a new file.
```

### A messy spreadsheet → charts and insights

Raw numbers turn into charts, and into one insight sentence that's hard to see with the eye.
Files in the folder: an Excel or CSV sheet (sales, budget, inventory, any tracker).

```
Analyze the spreadsheet in the 5-spreadsheet sub-folder, build two or three fitting charts in a new Excel file, and write at the top three key insights in English. Don't delete any file.
```

### A document → a translation that keeps the formatting

A document comes out as a clean English version that keeps the same structure.
Files in the folder: a Word or PDF document.

```
Translate the document in the 6-to-translate sub-folder into English in a new file, and keep the same heading and bullet structure. Don't delete any file.
```

---

## Bonus station — letting Cowork open a browser (optional, advanced)

This is a capability in its early runs — sometimes it works, sometimes it fails, and it's completely fine to skip it. If you feel like trying, paste:

```
Open the browser, find the opening hours of [a place near you], and write them to a file.
```

If it works, you'll see Cowork open a browser and navigate on its own. If not, don't get stuck — it's still experimental.

---

## Checklist before class

Run through the list, and when everything's ticked you're ready:

- You installed and updated **Claude Desktop**, and opened the Cowork tab.
- You switched on the **Code execution and file creation** setting.
- You downloaded the **demo pack** from [benefits-il.dev/cowork-demo](https://benefits-il.dev/cowork-demo) and set it as the working folder.
- You tried **Station 1** (a scheduled task) and **Station 2** (a goal with a plan to approve).
- You picked **at least one run from Station 3**, and the most fun is to start with the receipts.

That's it, you're in. In class we won't install a thing, we'll just work.
