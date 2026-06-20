# Practice — Chaining Agents

## Before you start

In the video you met this pair: one agent summarizes a meeting, and the agent after it pulls the tasks out of that summary. Now it is your turn to build it yourself, step by step. The first agent makes an intermediate product (the summary), and the second turns it into the final product (the task list).

Every prompt here is ready to copy, and next to it you will find exactly what to copy, where, and into which conversation. You are not writing anything from scratch, just copying.

What to have open: a Claude account. If you already built an agent in the agents unit, great. And if not, the first block here builds you one from scratch.

---

## Bonus — give your agent a styled name

Even before you start, a small something for the fun of it. I built you a sweet little tool that gives your agent a styled name: you type a name (Benefits, for example), pick an emoji you like, add some decorations, and copy the result straight into your agent's name. Completely optional. Just because it is nice for your agent to have a name of its own.

[Style an agent name](https://benefits-il.dev/agent-names/)

---

## Part A — Building the pair step by step

The pair we are building: **a meeting-summarizer agent → a task-extractor agent.** The first one takes a transcript and returns a summary, the second takes the summary and returns a task list. Notice exactly what passes between them: not the original meeting, but the summary the first one made. That is the glue of the chain.

### Step 1 — Build the first link (the meeting-summarizer agent)

Open a new conversation in Claude. We will call it the **build conversation**, and we will come back to it later.

First, paste the agent's ready SPOKE description:

```
I want to build an agent using the SPOKE method. Here is the description:

Self — an agent that summarizes the transcript or recording of a meeting.
Principles — does not track follow-ups, only summarizes. Does not invent things that were not said in the meeting.
Outputs — a clean, organized MD file, with clear headings for three sections: topics discussed, decisions made (who, what, and by when), and open points.
Knowledge — the transcript itself, who the participants are, and the purpose of the meeting.
Execution — reads the transcript, identifies implied decisions and tasks, and summarizes briefly.
```

Now you add the letter N. Notice where it goes: it enters **at the end of the description, after E**. It is the sixth letter, so it sits at the bottom, below everything else, not above. This is the letter that turns SPOKE into SPOKEN, and it declares that the agent is one link in a chain and who comes after it. Add this block at the end, below the five letters:

```
N — next in the chain:
My product is an intermediate product, not the end.
The next link is a task-extractor agent. It takes my summary as input,
and its output is the final task list.
```

And now paste the "expand" prompt, which turns the full description into a tidy system prompt:

```
Above I laid out a description of an agent using the SPOKEN method. Go over the description, organize it into
logical sections, fix what I said, and expand it into a precise system prompt that an AI model
will work with well as an agent. Be sure to include the letter N, who the next link is and what it takes
as input. Explain what you understood and wait for approval before continuing.
```

You now have a full system prompt for the meeting-summarizer agent. Set it up as an agent exactly as you did in the agents unit: a Project with a name and icon, and the system prompt inside the Instructions.

### Step 2 — Give the first link real work

Now we will give the agent real material to work on. Download the transcript file: [practice meeting transcript](meeting-transcript.en.md). This is a long, packed management meeting, with seven topics, decisions, owners, dates, and open points, exactly like a real meeting from work.

Open a new conversation with the agent you set up, and feed it the transcript. You can upload the file, or copy its contents into the conversation.

The agent returns an organized MD file: the topics discussed, the decisions made with their owners and dates, and the open points. Pause for a moment on what just happened. A messy transcript packed with information went in, and a clean, readable document you can work with came out. That is the real work of the first link, it took chaos and turned it into order. Keep the summary aside. It is the intermediate product, and the input for the next link.

### Step 3 — The second link builds itself (the task-extractor agent)

Go back to the **build conversation** from step 1, the one where you expanded the first agent. The agent already knows what its N is, so it knows exactly who to build. Paste:

```
Now build the next agent in the chain, matching the SPOKEN skeleton.
Describe it by the five components (Self, Principles, Outputs, Knowledge, Execution),
where its input is the summary I produced, and its output is the final task list.
It delivers its output in two files: a clean MD file of the tasks, and also a styled,
nicely designed PDF file in the Rubik font, with a due date for each task, and pleasant colors.
Explain what you understood and wait for approval before continuing.
```

You now have a full description for the second agent, the task-extractor, with its input being the summary the first one produces. Notice what you did here: you did not write it at all. You wrote N, and the chain built itself. Set this one up as a separate agent too.

### Step 4 — Run the chain

Take the summary from step 2, and paste it into the task-extractor agent. It returns two files: an organized task list in MD, and a styled PDF file with the tasks, the owners, and the due dates, in the Rubik font and pleasant colors.

Stop and see the whole route. You started from a long, messy meeting transcript, and after two links you are holding a clean summary document and a styled task document ready to hand over. Two links, each did its own job, and the first one's product fed the second. That is a chain that works, on real material and not on an example.

---

## Part B — Build a pair of your own from the menu

Now the exact same thing, on a different pair. We put together a menu of fifteen agent-pairs from different fields for you. Pick a pair that speaks to you (or one of your own), and build both links with the very same blocks from Part A: write N at the end of the first link's description, expand, and in the same conversation ask it to build the next one.

The full menu, fifteen pairs: [the agent-pairs menu](agent-pairs-menu.en.md).

Three example pairs, in case you feel like starting without leaving the page:

**Researcher → writer.** The first one gathers sources and returns a findings brief with citations. The second takes the brief and returns an edited, flowing article. What passes between them: the findings brief.

**Campaign strategist → copywriter.** The first one defines the audience and the message and returns a marketing brief. The second takes the brief and returns the actual copy. What passes between them: the brief.

**Content organizer → output builder.** The first one takes raw material and returns a slide structure: a title and key points for each slide. The second takes that structure and returns a styled deck or page. What passes between them: the slide structure.

For every pair, the N line of the first link is the same template, only with the description of the next agent:

```
N — next in the chain:
My product is an intermediate product, not the end.
The next link is [description of the next agent: what it does, what its final output is],
and it takes my product as input.
```

---

## Optional challenge

For anyone who already built a pair, two ways to keep going. **A third link:** ask the second agent to build the one after it, and you get a chain three links long. **Another pair:** pick a different pair from the menu and build that one too.

---

## Materials and links

- [practice meeting transcript](meeting-transcript.en.md) — the input for step 2, to download.
- [the agent-pairs menu](agent-pairs-menu.en.md) — fifteen pairs to choose from.
