# 📓 NotebookLM, the tool that answers only from your own material

## What you will know how to do by the end of this chapter

To identify when NotebookLM is the right tool and when it is not, to feed it your own sources of any kind (document, link, PDF, video, recording, Drive, or pasted text) and ask questions that are answered only from these sources with a citation to the source, and to produce a single output from the Studio (mind map, infographic, table, or guide). And above all, to understand that this is almost never the final product, but rather raw material and inspiration.

**Reading time:** About 15 minutes, mostly in front of the screen.
**What you should have open:** A Google account (the free one is absolutely fine), and one real source from your work.
**What this is based on:** On the memory layers. You remember the six layers, and you remember that we left the sixth layer, RAG, for "later". This is the continuation.

**Chapter map:** First we will talk about the pain point this tool comes to solve. Then we will see how to feed a source and get an answer that relies only on your material, and why this is the sixth layer. Then we will enter the Studio and the various outputs. Finally, you will take this to something real of your own.

---

## The Pain Point

Let us start with the place without which everything else sounds like just another toy, so let us pause on it for a moment.

You have a pile of your own material. Documents, old presentations, a few links, a YouTube video, maybe a recording of a conversation, perhaps an entire folder in Drive. And you want to ask questions and get answers that rely only on this material. Not on what the AI knows about the world, not on what it will find for you on the open internet, but exactly on what you brought.

Now think about what happens when you take this to a regular chat like Claude. A chat is built to answer from its general knowledge, or to go and search outside. That is its entire purpose. And when the truth must come from your material and only from it, this is exactly the moment when a regular chat is the wrong tool. (Not bad, just not for this.)

NotebookLM was built for exactly this moment. Its entire point is that you choose the source it will answer from, and then it answers only from it, with a citation to the exact source. In addition, it knows how to take that same material and generate quick and diverse outputs from it. This is the pain point, and these are the two sides of the answer.

---

## Anchor

Here is the difference in one sentence, so it sticks. A regular chat knows everything and sometimes hallucinates, and answers from its general knowledge or from an external search. NotebookLM only knows what you have fed into it, and answers only from within it, with a small marker showing which source each sentence was drawn from.

And there is one simple way to see where this tool sits in relation to everything we have already learned. Think of a ladder. At the bottom is a regular chat, which answers you from the big wide world. Above it is regular internet search. Above that is Deep Research, which we have already nicknamed "the third thing" at home, because it is neither a chat nor a regular search, but something that goes out to search deeply. And now, above all of these, comes NotebookLM, and this is a completely new breed. Why new? Because it is not just a chat, and not just search, and not even just Deep Research. It is all of these things together, and in addition, it generates outputs from your material that none of the previous ones provided. Each step relies on the one below it and adds one layer, and that is why this clicks better than a dry definition.

And there is one more thing that is important to make clear right now, because it changes how you approach the entire tool. NotebookLM is a sketch artist, not a printer. You take inspiration and raw material from it, it will almost never be the final output. Hold both of these things together: a powerful tool that answers from your material, but a sketch, not a final print. (We will return to this, it is the most important rule in the chapter.)

---

## Cycle 1: Feed a source, get an answer from your material

### The Idea

NotebookLM is a free tool by Google. There is also a paid version, but the differences are not huge, and it is very good even for free. You open a new notebook, and the first thing it asks you to do is feed it sources, because without sources it has nothing to answer from.

And what can you feed it? Almost anything. You can upload files (PDF, presentation, document, even a recording), paste a link to a website or a YouTube video, connect your Drive, upload images, or simply paste text. And if you do not have ready-made sources yet, it also has its own quick web search and Deep Research, which bring you sources from the web, and you choose which ones to bring in.

Once you approve a source, it is not just saved. The tool organizes it in a way that allows retrieval (the process is called vectorize), and from here you chat with it, ask questions, and it answers only from the sources and shows you which source each answer came from.

### This is the sixth layer, RAG

Remember when we mapped out the six memory layers, the sixth and most distant layer was RAG, and I said we would get to it separately later? We have arrived. NotebookLM is exactly that layer.

Let us clarify what RAG is, because that is what explains why the tool behaves this way. RAG is semantic retrieval: the information sits in vector form, and when you ask, the model searches for a field with a meaning close to the question and retrieves based on that. And that is exactly what NotebookLM does when it vectorizes your source.

And there is a difference here worth keeping in mind. In Notion, in the knowledge base you built, you have full manual control, you see and edit every block. In NotebookLM you do not edit how the information sits inside, at least not at this stage. In return, you get something that Notion does not have: the ability to throw in almost any type of data and extract answers and outputs from it. That is the trade-off, less manual control, more breadth and variety.

### This is what it looks like

You open a new notebook, and as a source, you do a quick web search on a topic, say "best practices for building AI agents that run on different platforms". The tool opens a window, shows the sources it found, and you add one of them to the notebook. Here you see the vectorize happening in real time.

After approving the source, the notebook automatically identifies the topic and suggests questions. You go into the settings, change the output language to Hebrew, and ask a focused question, say "what are the rules for writing an agent that will run well in Claude?". And the answer comes back with small markers, like an old-fashioned encyclopedia, and each of them points to the source from which the sentence was drawn. Clicking on a marker opens the source segment itself. This is the heart: not an answer out of thin air, but an answer with an address.

### Now you

Go to notebooklm.google.com, create a new notebook, and upload one real source from your work, a document or a link. Then, in the notebook settings, change the output language to Hebrew, and ask one question about the material. See that it answers with a citation to your source, and try clicking on one of the markers to see where it came from.

### Self-check

How will you know it is working properly? When the answer points to your source with a clickable marker, rather than answering in thin air. If it answers without a source, you probably did not feed in a source, or the question is too general.

**Common mistake:** Uploading ten sources all at once. Start with one, see that the notebook has captured it and answers from it, and only then add more.

> **In your own words:** Why is a regular chat the wrong tool when the truth must come from your material, and NotebookLM is the right one?
> *(Sample answer: Because a chat answers from its general knowledge or from an external search, and NotebookLM answers only from the sources I chose and fed into it, with a citation to them.)*

---

## Cycle 2: The Studio, and diverse outputs from your material

### The Idea

It does not stop at questions and answers. NotebookLM also knows how to generate outputs from your sources, different types of outputs. This is what is called multimodal: all kinds of inputs go in, and all kinds of outputs come out. In the Studio, there are buttons that generate a table, a mind map, an infographic, a report, a presentation, a study guide, a quiz, and flashcards from your material. And for any output that has a small arrow next to it, you can go into the settings and adjust what comes out, for example, in a table you can choose the language and formulate exactly what goes into it.

### This is what it looks like

Let us go over a few outputs from the source, because they show both the power and the limit, and both of these are equally important.

The **table**. You ask for "an organized table of all the details that should be included in the instructions of an AI agent", and you get a table with organized categories. It is fast and orderly, and at the same time it is not perfect: sometimes the same category appears twice, and sometimes something that does not exactly belong gets in there. Both statements are true together.

The **mind map**. It takes the topic and breaks it down into chapters and sub-chapters, and clicking on a topic inside it pops up a question to the chat and makes it answer it. This is an excellent tool when you want to organize material and see it visually. If you pushed an entire deep research paper in there, you can see what is in it without reading ten pages.

The **infographic**. It comes out really nice, and at the same time gets messed up in certain places, and again, both statements are true. It gives you an idea for thematic division, and an idea for a visual, but sometimes suddenly puts strange, unrelated things there. You take the idea, the division, and the visual direction. The output itself, you do not.

### Why it is a sketch artist, not a printer

Now we reach the most important rule in the chapter, and we already touched on it in the anchor. NotebookLM is not a printer. You do not take the output as-is and send it off, because there are typos, because sometimes the language is not 100% accurate, and because the visuals look pretty much the same. But for a certain way of thinking, for seeing the order and the points, it helps a lot.

Here is a real example that shows exactly what it looks like when you work correctly with this tool. Suppose you need to design a logo. Instead of reading ten articles, you gather about ten YouTube videos that look interesting about logos and icons, and put them all in as sources. Now you ask for a podcast, listen to it on your commute, and also ask for a mind map that breaks the topic down into chapters. The tool returns diagrams of the thought process, and this organizes things in your head: what the stages are, what is important, where to focus. Notice what happened here. None of these outputs is the final logo, or even close to it. Someone who has already designed logos in the past still learned something from this, because it gave them structure and understanding, not a finished product. That is exactly what this tool is good for.

You take inspiration and raw material from it, how to organize, what the points are, what is missing, and build your own. It is not forbidden to use it, on the contrary. But the moment you want an output of a certain quality, you look at the sketch and understand why it is only a starting point. This is exactly what distinguishes someone who submits a sketch as-is, from someone who takes from it and builds a real thing.

### One important note for Hebrew

In the Studio, there are also Audio (podcast) and Video outputs. In Hebrew, their quality is weak, the right-to-left reading and the language confuse them. So in Hebrew, stick to text and visual outputs: table, mind map, infographic, guide, report. That is where the tool is strong, and that is where you will get the best out of it.

### Now you

From the source you uploaded in Cycle 1, open the Studio and request one output, a mind map or an infographic. Read it, see that it relies on your material, and pay attention to both the beautiful sketch and the things that are messed up in it. This experience, seeing with your own eyes what is good and what needs fixing, is the main thing.

### Self-check

The output has done its job when it relies on your source and gives you a starting point, not when it is perfect. If you know how to point out what to take from it (the order, the points, a visual idea) and what not to take (the errors, the strange things, the generic visual), you have understood exactly how to work with this tool.

> **In your own words:** What does it mean that NotebookLM is a sketch artist, not a printer?
> *(Sample answer: You do not take the output as-is for a final product, because there are errors, the language is not always precise, and the visual is generic; you take inspiration, ideas, and raw material from it, and build your own.)*

---

## Putting It All Together

So what did we have? NotebookLM is the tool that answers only from your own material, because you choose the source it will answer from. You feed it sources of any kind (files, links, YouTube, recordings, Drive, text), the tool vectorizes them, and answers with a citation to the exact source. This is the sixth layer, RAG, semantic retrieval with less manual control than Notion but much more breadth and variety. It also generates multimodal outputs from the material: a table, a mind map, an infographic, a guide, and more. And above all, it is a sketch artist, raw material and inspiration, almost never the final product.

Three questions to consolidate:
1. Why is a regular chat the wrong tool when the answer must come only from your material?
2. Which layer of the six memory layers is NotebookLM, and what is its difference from Notion?
3. Why in Hebrew do we stick to text and visual outputs and not Audio or Video?

*(Answers: 1: Because a chat answers from its general knowledge or from an external search, not from my sources. 2: The sixth layer, RAG, semantic retrieval without control over how the information sits, unlike Notion where I see and edit every block by hand. 3: Because the quality of right-to-left reading and the language of audio and video is weak in Hebrew.)*

**Write down for yourself in Notion:** Which single real source from your work you will feed into NotebookLM, and which output you will request from it.

---

## Take it to your world

This is the moment to do this on something real of your own, not on a practice topic.

**Step 1: Source.** Take one real source from your work. A document, presentation, video, link, or a recording of a conversation. Open a new notebook at notebooklm.google.com, feed it in, and wait for the notebook to finish processing it.

**Step 2: Anchored question.** Change the output language to Hebrew, and ask one focused question about the material. Make sure the answer comes back with a marker pointing to your source.

**Step 3: One output.** Open the Studio and request one output, an infographic or a mind map. In Hebrew, do not touch Audio and Video.

**Step 4: Editor's eye.** Look at the output and ask yourself two questions: what to take from it (the order? the points? a visual idea?), and what not to take (where is it messed up, generic, or imprecise?). This is not an exercise that ends with a pretty file, it is an exercise in seeing the limit of the tool.

---

## Quick Reference Sheet

**The flow:** notebooklm.google.com → new notebook → feed sources (files / link / YouTube / recording / Drive / text, or the tool's quick search and Deep Research) → change output language to Hebrew → ask in the center (answers with source citation) → Studio → choose output (table / mind map / infographic / guide).

**What it is in a sentence:** The tool that answers only from your own material. The sixth layer, RAG.

**Golden rules:** Hebrew = text and visual outputs only, not Audio or Video. NotebookLM = a sketch artist, not a printer. Start with one source, not ten.

**Where we go next:** We will learn how to connect NotebookLM to your Claude agents in the chapter on MCP, not here. Here, we got to know the tool itself.
