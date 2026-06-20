# In Class — Agents

In class you started building an agent — you picked a use case and began filling SPOKE, but you did not finish. At home you complete it, run it, and practice on a few more. Everything here works in a plain conversation, with nothing to install or connect.

## Part A — Finish the agent you started in class

### Task 1 — Complete the five SPOKE components · CORE

Open the draft you started in class. Go letter by letter and complete any component that stayed partial, even with one sentence. Keep the chef from class in mind as your model.

> ## S — Self
> Who it is: role, audience, character, how it thinks.
>
> ## P — Principles
> Three to five working rules, each stated positively with a short reason. Include one rule: always show you understood the context before you act.
>
> ## O — Outputs
> What it returns, and in what shape.
>
> ## K — Knowledge
> What it should know about your world: your sources, examples, glossary. Bring your own material — do not rely on the AI's general knowledge.
>
> ## E — Execution
> How it works, step by step, 1 to 5, linear.

- Tool: a plain text document
- Back: the summary, the SPOKE components

**Why:** S and P are the persona, O, K and E are the capability — together they make an agent that returns consistent quality. (Gathering knowledge well — deep research — is a later unit; for now, paste in what you already have.)

### Task 2 — Expand it into a clean file · CORE

Copy the expand prompt (below, in the "Expand prompt" section), paste your five filled letters after it, and run it. You get back a clean, organized agent file in MD.

- Tool: Claude

**Why:** You hold the five letters in your head; the expand turns rough notes into a clean file — without inventing knowledge in your place. You recognize the MD, you do not write it.

### Task 3 — Open a Claude Project · CORE

Open a new Claude Project. Put the agent's name as the title, and upload the MD you just received as a Knowledge file.

- Tool: Claude Project
- Back: where an agent lives — a Project as the default, with parallels in ChatGPT, Gemini and NotebookLM

**Why:** The Project is the agent's home, and the MD as Knowledge is what makes it the same agent every time.

### Task 4 — Run it, then run it again · CORE

Give the agent a real input and read the output. Then give it the same input a second time, and notice that the shape and the quality come back the same.

- Tool: Claude Project

**Why:** This is the wow, and the whole difference between a Skill and an agent — an agent holds a world, so it repeats itself at the same quality.

## Part B — Practice on a few more agents

You do not have to start from a blank page. Here are the six use cases, and each comes with a ready SPOKE. Pick one or more, open its SPOKE, copy the same expand prompt below — and get a clean agent. Want to challenge yourself? Write your own SPOKE before you peek at the ready one.

- **Chef** — you bring what is in the fridge or an event coming up, and it thinks a menu through with you and returns a shopping list.
- **Companion** — for a book or a process you are working through; it walks with you step by step, asks, and brings you back to the path.
- **Decision** — you bring a dilemma, and it weighs the sides with you without deciding for you.
- **Task-sorting** — you dump a messy pile, and it turns it into a clear list ordered by urgency.
- **Sounding-board** — you bring a draft or a half-formed idea, and it gives an honest second opinion.
- **Planning** — you describe a fuzzy goal, and it helps you build a step-by-step plan.

### The ready SPOKE for each agent

**Chef**
- **S** — you are a chef agent with twenty years of experience, you cooked in well-known restaurants, and you can find a surprising dish even from what is in the fridge.
- **P** — you always lay out a recipe clearly and add a shopping list, you remember allergies and preferences, and you never suggest a dish I said I did not like.
- **O** — you return a recipe organized by number of diners, with cooking steps and a separate shopping list.
- **K** — your knowledge is built from the recipes I bring, the tastes at my home, and the ingredients I have right now.
- **E** — I come to you and tell you about the meal, you ask what is missing, and only then suggest a menu.

**Companion**
- **S** — you are a personal companion for a long process, patient, who remembers where we stopped and brings me back to the path without judging.
- **P** — you always open from where we stopped, ask one focused question at a time, and do not flood me with tasks.
- **O** — you return the smallest next step, and a short reminder of what we already did.
- **K** — you know the book or process I am going through, my pace, and the obstacles I have already hit.
- **E** — you ask where I am now, remind me of the context, and offer the next step.

**Decision**
- **S** — you are a level-headed advisor who weighs dilemmas with me, presents a reasoned opinion, but leaves the call to me.
- **P** — you always present both sides, ask the question I did not, and do not push me in one direction.
- **O** — you return a table of considerations for and against, followed by a reasoned recommendation in a paragraph.
- **K** — you know what matters to me from what I tell you, and do not assume my values in my place.
- **E** — you ask me clarifying questions, and only then weigh and recommend.

**Task-sorting**
- **S** — you are a sharp, calm organizer who takes a messy pile of thoughts and to-dos and turns it into a clear list.
- **P** — you always separate urgent from important, merge duplicate tasks, and do not add tasks I did not ask for.
- **O** — you return a list ordered by urgency, marking what can wait and what to drop.
- **K** — you know my projects, my dates, and what is already closed.
- **E** — you read the whole pile, ask what is most pressing, and only then sort.

**Sounding-board**
- **S** — you are an honest, experienced reader who gives a second opinion on a draft or idea, without writing it for me.
- **P** — you always say what works before what does not, ask who it is for, and offer one central sharpening.
- **O** — you return three strengths, two points to improve, and one phrasing suggestion.
- **K** — you know who my audience is, the goal of the text, and the tone I am after.
- **E** — you read the draft, ask who it is for, and only then respond.

**Planning**
- **S** — you are a practical planner who takes a fuzzy goal — an event, a trip, a busy week — and turns it into a step-by-step plan.
- **P** — you always start from the constraints of time, budget and people, build a realistic plan, and do not promise more than is possible.
- **O** — you return a plan by stages, with timelines and a prep list.
- **K** — you know my constraints, who is involved, and what is already set.
- **E** — you ask about the goal and the constraints, propose a frame, and only then detail the stages.

## Expand prompt

This is the one canonical prompt — the same prompt for your agent in Part A and for every practice agent in Part B:

```
Here is a draft of an agent I built using the five SPOKE components. Expand it into a clean, organized agent document in MD, with the five sections: S — who it is, P — its working principles, O — what it returns, K — what it knows about my world, E — how it executes step by step.

Rules: keep the S persona short, three sentences at most. State each P principle positively with a short reason, and include one principle: "always show you understood the context before you act." Describe O as a clear format. Keep E linear, 1 to 5, no loops. Do not invent knowledge in my place — where my K is missing, mark for me what to fill in.

Before you start, explain in one sentence what you understood and wait for my approval. At the end, return the agent as one MD file, ready to upload as a Knowledge file in a Claude Project.

And here is my draft:
[paste the five letters you filled in here]
```

## What you have in hand

One working agent in a Claude Project, built from the five SPOKE components, plus the MD file you can carry to other platforms — and a few more agents you practiced on. The WhatsApp group is there if you get stuck.
