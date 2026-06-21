# In class — Memory Layers

## ✏️ In class: we build Benefit, and give it its memory layers

This is the moment to set up Benefit, the agent that sits beside you and holds the memory. In class we do the core: we set it up, give it its first two skills, save and retrieve, feed it everything we've learned so far, and then pull it back out with our own eyes. The other two skills, and the rest, we complete at home.

## Step 1 — Set up Benefit

Open a new project in Claude called Benefit, and paste the ready-made agent into the project Instructions. Connect Notion with read and write permission, and upload all the knowledge files to Files, including the course-structure file. It's all on one page: [benefits-il.dev/benefit-agent](https://benefits-il.dev/benefit-agent).

## Step 2 — Install the first two skills: save and retrieve

From that same page, download two skills and install them in Claude through Settings → Skills → Upload, each one separately:
- **Save** — Benefit writes an insight or a new page into Notion for you.
- **Retrieve** — Benefit goes to the index, picks the relevant page, and loads only it (index → select → load).

The other two skills, STUDIO and MICRO, you'll install at home.

## Step 3 — Feed Benefit everything we've learned so far

Now we give Benefit everything we've learned, so it has the full picture. Eight learning chapters, from both sessions: from Session 1, foundations, skills, agents. And from the Session 2 prep, shared language, connectors, Notion, agent chaining, and deep research.

Open a new conversation with Benefit. Go to each learning-chapter page on the site, click the "copy to Notion" button, and paste the chapter into the conversation. At the top of the conversation, before the first chapter, paste this prompt:

```
I'm going to paste you learning chapters from the course, one at a time. For each chapter: identify which unit and which session it belongs to, find its right place in the notebook (Benefits → the session → the unit), and add the matching STUDIO tag. Before you write anything to Notion, first show me where the chapter goes and which tag you gave it, and wait for my approval. Let's start. First chapter:
```

Under the prompt, paste the first chapter. After Benefit shows you where it's filing and you've approved, type "next chapter:" and paste the next one, and so on until all eight chapters are in.

**Why this:** this is what turns Benefit from "knows today's lesson" into "knows the whole course." And filing by the structure is exactly what lets it later pull the right page for you, without searching blind.

## Step 4 — Pull earlier info back out of the course

Now we check that retrieve works. Open a new conversation with Benefit, and ask a content question about something you've already learned. Benefit goes to the index in Notion, picks the relevant page, loads only it, and answers — with a pointer to where it's stored. Paste:

```
Remind me what the MICRO method is, and where in my notebook you pulled it from. Explain briefly, and show me the page you relied on.
```

**Why this:** this is how you see, with your own eyes, that the memory doesn't just go in, it comes back out on demand. That's the whole difference between a pile of documents and an agent that remembers.

## A few things worth remembering

- The manual approach is always available: you can open Notion and fix a name or a date yourself. It's better to let Benefit do the filing, but when you need to, you can.
- If a write action doesn't go through, make sure the Notion connection is linked with write permission, and approve the write tool when it asks.
- If you get stuck at any step, try again, and we'll sort it out together in the session.
