# Practice — Shared Language

## ✏️ Download the tool that makes life easier for the AI

You saw in the video that the simplest way to save tokens is to make things easier for the AI. So before we dig into why, let's just grab a ready-made tool that does exactly that. (Yes, even before the explanation. We trust you.)

## What the tool does

It takes any messy input, a Word file, a PDF, a presentation, an image, or just plain text, and hands it back as clean, tidy MD. Exactly the "make life easier for the AI" we talked about.

## The task

1. Open the Skill at this link: [markitdown by Eleanor Berger](https://gist.github.com/intellectronica/7c76818d79851fa8c33a6f7b0420bccb).
2. Download the Skill file (`.skill`) from the link and upload it to Claude, just like you installed Skills in the first session.
3. That's it. From now on you have a tool that tidies the material for the AI before it even starts working.

## Self-check

- The Skill is installed and shows up in your list of Skills in Claude.

## Tip

This Skill came from our free library, [benefits-il.dev/benefits-library](https://benefits-il.dev/benefits-library). There's a whole shelf of tools like this there, take a look whenever you feel like it.

[[video:RoFhObRaCgQ]]

## ✏️ The tool: clean, export, and send

You already met this tool in class, so we won't introduce it from scratch. We'll just practice. [md-he](https://benefits-il.dev/md-he) is open in a tab, no install and no account.

## The task — four actions, a minute each

1. **Clean and paste.** Take any Hebrew output from Claude, copy it, and in the tool click "clean and paste". Suddenly it's tidy and readable, right-aligned too.
2. **Export to Word.** Take that same text, export it to Word, and watch the headings turn into real headings.
3. **Copy to WhatsApp.** Take a short list, choose copy to WhatsApp, and send it to yourself. The bolds come out right.
4. **Mermaid.** Paste the following text into the tool and watch it turn into a diagram:

```
flowchart TD
  A[Output from Claude] --> B[Clean and paste in the tool]
  B --> C[Export to Word or WhatsApp]
```

## Self-check

- Pasted normally and the formatting broke? Make sure you clicked "clean and paste" and not a regular paste.
- WhatsApp doesn't show headings and tables, only bold, italic, and lists. That's expected.

[[video:-KDAafr5xZE]]

## ✏️ Explore → Convert → Identify

You met the family in the video. Now you'll meet it hands-on. Three steps, and one promise: you won't write a single line.

## Step 1 — Explore: same content, four costumes

Open Claude and paste the prompt (it already includes a sample item, just send it):

```
Take the following item and present it in four formats, one after another: Markdown, YAML, JSON, and XML.
Under each format, write one line only: when it's most useful and where you run into it.
No long explanation, just the example and the line.

Here's the item:
Name: Dana Levi
Role: Product Manager
City: Haifa
```

The exact same content, four completely different forms.

## Step 2 — Convert: let the Skill do the work

Remember the Skill you installed earlier? Give it some real work: take a messy file or text of your own from this week, and toss it into the Skill. It'll hand it back as clean MD, without changing a word. (Don't have anything on hand? Use this passage.)

```
Meeting May 26. Ronit, Dani, and Michal attended. Decisions: scope will be limited to three modules, the method is two-week sprints. Open point: an external vendor for the integration.
```

## Step 3 — Identify: three questions

For each passage, which format do you see? Pick one answer, and the answers are at the end.

**Question 1:**

```
{ "name": "Dana Levi", "role": "Product Manager", "city": "Haifa" }
```

a. Markdown · b. YAML · c. JSON · d. XML

**Question 2 — look at the block between the lines (---) at the top:**

```
---
title: Weekly Report
tags: [summary, meeting]
---
## Key Points
- First point
```

Which format is the top block? a. JSON · b. MD · c. XML · d. YAML

**Question 3 — a format hiding inside a format:**

```
{ "title": "Summary", "body": "## Decisions\n- Scope: three modules" }
```

What's the outer format, the one wrapping everything? a. JSON · b. YAML · c. XML · d. MD

## The answers (only after you've answered)

- **Question 1: c, JSON.** Curly braces, quotes around every key, commas.
- **Question 2: d, YAML.** Spaces at the start of the line and colons, no braces. This block is called frontmatter, and what follows it is MD. Two formats in one file.
- **Question 3: a, JSON wraps everything.** Inside the body field, MD is hiding. That's how formats nest one inside another, which is why it's worth spotting who wraps whom.

(Did you notice? You didn't write a single line of any format. Claude and the Skill did the work, you just identified.)

## Bonus — XML in a prompt (the exception worth knowing)

Want to try the one member of the family you'll actually use yourself? Paste this into Claude:

```
Take the following prompt and wrap each of its components in a suitable XML tag (instruction, context, example),
to give Claude sharp boundaries between the parts. At the end, explain in one line why this helps.

Here's the prompt:
Instruction: Summarize the customer feedback into five bullet points.
Context: The summary is for senior management and needs to be concise.
Example: Each bullet up to two lines, action-focused.
```
