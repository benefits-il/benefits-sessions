# 🔗 When One Agent Isn't Enough

> Learning chapter. Agent-chaining unit. Story voice. Written from the canonical unit: the lesson plan, the slides, the exercise, and the summary page.

## What you will be able to do by the end

To identify when a single task splits into two separate roles, to add the letter **N** to the agent you already have to turn it into a link in a chain (SPOKE™ becomes SPOKEN™), and to build the next agent in that same chat without writing it from scratch. By the end, you will have two connected agents in hand, and you will know when a chain is actually worth it instead of one overloaded agent.

**Reading time:** About 20 minutes, including 10 minutes in front of the screen while you build.
**What to have open:** A Claude account with the agent you built in the agents unit, or the repository of pairs attached to this unit if you do not have an agent ready.
**What it builds on:** The agents unit. You built an agent according to **SPOKE™** (five letters: Self, Principles, Outputs, Knowledge, Execution), you know the "expand" prompt, and you know the concept of input and output. The chain just adds one letter on top of all that.

**Chapter map:** First, we will understand that in the real world, a task passes between several professionals, and an agent can also be just a link and not the end. Then we will see when a chain is actually better than a single agent. Next, we will add the single letter that connects link to link, see how the chain builds itself, and wrap up with the question of who actually runs all of this.

---

## The story that starts it all

Up until now, every agent you built has produced its final product. You built a recipe agent, its output is a recipe, the end. You built a summarizing agent, its output is a summary, the end. You looked at what came out, and that was it.

But in the real world, it is almost never like that. A single professional does not prepare the entire thing alone. They prepare a part, and pass it on to someone else. Think of an **architect**: they design, and in the end hand over the plans to a **contractor** who builds. Or a **screenwriter** who wrote a script, and hands it over to a **director** who turns it into a movie. In each of these cases, the first produces an **intermediate product** (a plan, a script), and the second turns it into the final product.

This happens in the tech world too. A **product manager** writes a requirements document, a PRD. No product manager wakes up in the morning and prepares a spec document just because they feel like it. They write it to pass it on to an **architect**, who builds the product's architecture from it. The PRD is the intermediate product, the architecture is the final product. That is what passes between the links.

This is exactly what this chapter is all about. **An agent can also be a link.** It produces an intermediate product and passes it on, it is not always the end. And the beautiful thing is that you do not build this chain from scratch. We are going to see how it **assembles itself**.

---

## Cycle 1 - When do you actually need a chain

### The idea

How do you know you have a chain and not just a single agent? When you realize that the agent's scope is **not** the final product. It is a link: it does its part, passes it on, and the product passes from link to link until the end. That is its scope, just a single link in a chain.

You already know about splitting tasks. We talked about it in STUDIO™, about the separation of roles. The chain is the next step: not just splitting the task in your head, but giving each part **its own agent**, and connecting them.

And here it is important to stop and ask one question: why split into two agents at all, if one good agent can do both? There is a simple logic to this from the kitchen. You do not stand over someone and say, "peel the vegetables, and when you are done we will talk about what is next." You say, "peel, chop, fry," step by step, each one building on what came before it. Like a dishwasher: you do not load and unload at the same time, first it goes in and then it comes out. That is exactly how a train of thought is built, step by step, and that is why you do not push everything into one crammed prompt. The answer is also the same reason we discussed in the memory unit, when we wanted one clear persona for each agent. Two truly separate roles confuse a single agent. Take the chain we will build here: summarizing a meeting and extracting tasks from it. If the transcript is short, a single agent solves it in one breath. But meetings are different: there is a client call, there is a team meeting, there is a phone call where you explained something and you want to turn it into a knowledge document. When the transcript is long, you want an agent that focuses **only** on the summary, so it does not start scattering its focus onto tasks as well. One summarizes cleanly, the other extracts tasks cleanly.

### What it looks like

Take the pair we will use throughout the chapter, because it is concrete for everyone: everyone knows a meeting that needs to be summarized and have tasks extracted from it. **meeting-summary agent → task-extraction agent.**

The first receives a transcript of a meeting and returns a focused summary: topics discussed, decisions made, open points. This is the intermediate product. The second receives this summary as input, and returns an organized task list. This is the final product. Notice what passes between them: not the original meeting, but the **summary** that the first produced. That is the input for the second.

There are pairs like this in every field. **researcher → writer:** the first gathers sources and summarizes findings, the second turns them into an article. **campaign strategist → copywriter:** the first defines the audience and message and creates a marketing brief, the second actually writes the copy. In each of them, it is the exact same axis: the first produces an intermediate product, the second turns it into a final product, and what passes between them is the output of the first.

### Now you

Stop for a moment and think of one real task from your work that splits into two separate roles. Mark for yourself: what the first link produces (the intermediate product), and what the second link receives and does (the final product). If you struggle to find what passes between them, it is probably a single role and one agent is enough.

### Self-check

How do you know you have identified a real chain? There are three things that must be clear between two links:
- **What the output** of the first link is, what it passes on.
- **When it has finished** its part.
- **What the input** is that the second link receives, because it needs to know what the previous one passed to it.

If you cannot answer these three, you do not have a chain, you have a single task that you are trying to force into two.

**Common mistake:** Splitting into two links that basically do the same thing. If the product of the first is not the input of the second, it is not a chain.

> **In your own words:** In one sentence, when is a chain better than a single agent?
> *(Example answer: When there are two truly separate roles, one producing an intermediate product and the other turning it into a final product, and the output of the first is the input of the second.)*

---

## Cycle 2 - The letter that expands SPOKE™

### The idea

Now, where do we define all this? Not in a new framework. Inside the agent itself, within the SPOKE™ you already know, there is a place for it. **One letter.**

Remember the five letters, Self, Principles, Outputs, Knowledge, Execution? Now we get the sixth letter: **N**. That is **Next**, the next in line in the chain. And when we add it, SPOKE™ becomes **SPOKEN™**.

The letter N says two things, and that is all it says:
- **This agent is part of a chain.** Its product is an intermediate product, not the end.
- **Who the next link is.** What the next agent does, and that it receives my product as input.

That is it. One letter on top of what you already know. All the power of this unit is hidden in what that one letter enables, and you will see it in a moment.

### What it looks like

Take the meeting-summary agent. Its SPOKE™ is already written, which is exactly what you saw in the agents unit:
- **Self:** An agent that summarizes a transcript or recording of a meeting.
- **Principles:** It does not track tasks, it only summarizes, and avoids inventing things that were not said.
- **Outputs:** A focused summary including topics, decisions, and open points.
- **Knowledge:** The transcript itself, who the participants are, and what the purpose of the meeting is.
- **Execution:** It reads the transcript, identifies decisions, and summarizes briefly.

Up to here, it is exactly a regular SPOKE™ agent. Now we just add one line on top, the N:

```
N - next in the chain:
My output is an intermediate product, not the end.
The next link is a task-extraction agent. It receives my summary as input,
and its output is the final task list.
```

That is the whole difference. The exact same agent, plus one statement that tells it, "you are not the end, there is someone after you, and they receive from you."

### Now you

Open your agent from home, or choose a pair from the repository attached to the unit. Under the five existing letters, add a line for **N**: declare that the agent is part of a chain, who the next link is, and what it receives as input. Here is the text to copy, just fill in the description in parentheses for your next agent:

```
N - next in the chain:
My output is an intermediate product, not the end.
The next link is [description of the next agent: what it does, what its final output is],
and it receives my output as input.
```

Now it is SPOKEN™.

### Self-check

How do you know you wrote a good N? If by reading it you know **exactly** what the next link gets in hand. If your N only says "there is another agent after me" but does not say what it receives and what it outputs, you are missing the most important part.

**Common mistake:** Writing an N that describes the next agent, but forgetting to say that it receives **my output** as input. This is the glue of the chain. Without it, you have two separate agents, not a chain.

> **In your own words:** What is the difference between SPOKE™ and SPOKEN™?
> *(Answer: SPOKEN™ is SPOKE™ with a sixth letter, N, which declares that the agent is a link in a chain and specifies who the next link is. SPOKE™ alone describes an agent that produces a final product.)*

---

## Cycle 3 - The chain builds itself

### The idea

Now comes the moment that is the heart of the unit. After you have written the N, the first agent **already knows** who comes after it and what they are supposed to receive. So instead of writing the second agent from scratch, you simply ask the first one to build it. The chain assembles itself, and you walk away from that same chat with two agents.

### What it looks like

Step one: take the SPOKEN™ you wrote (the five letters + N) and ask the model to expand it into an organized system prompt, just like the "expand" prompt from the agents unit. Paste this after the spec:

```
Above, I detailed an agent spec according to the SPOKEN method. Review the spec, organize it into logical parts, correct what I said, and expand it into a precise system prompt that an AI model will work well with as an agent. Make sure to include the letter N - who the next link is and what it receives as input. Explain what you understood and wait for approval to continue.
```

It will return the full first link to you and stop for approval. You review and approve.

Step two, and this is the magic: **in the same chat**, paste the following prompt. The agent already knows what its N is, so it knows exactly who to build:

```
Now build the next agent in the chain, matching the SPOKEN framework.
Describe it according to the five components (Self, Principles, Outputs, Knowledge, Execution),
where its input is my output, and its output is the final product.
Explain what you understood and wait for approval to continue.
```

It will return the second agent, the task-extractor, built according to SPOKEN™, with its input being the summary that the first produces. Notice what you did here: you did not build it. **You wrote N, and the chain built itself.**

Step three: set both of them up. Take the two system prompts, and set up each agent separately, just like you set up an agent in the previous unit (a Project with a name and icon, the system prompt in the Instructions). You walk away with two: a meetings agent and a tasks agent.

And then you run them. Feed a real transcript to the meetings agent, and it returns a summary: topics, decisions, open points. This is exactly the output you defined. Take this summary, paste it into the tasks agent, and get an organized task list. The chain is running.

### Now you

Take the SPOKEN™ you wrote in Cycle 2, run the expansion prompt on it, and in the same chat ask to build the next agent. Set up both of them, and run the first link on real input. If its output feeds nicely into the second link and produces a final product, you have a running chain.

### Self-check

How do you know it succeeded? When the second agent you got **starts** from the product of the first, and does not ask you for the raw material all over again. If the second agent asks you for the original meeting again, the N was not incorporated correctly, and it does not know it receives the summary as input.

**Common mistake:** Forgetting that this needs to happen **in the same chat**. If you opened a new chat to build the second agent, you lost the context of the N, and it does not know what it is continuing from.

> **In your own words:** Why does building the second agent happen in the same chat as the first, and not in a new chat?
> *(Answer: Because in the same chat, the first agent already knows what its N is, so it builds the next one exactly according to what needs to pass between them. In a new chat, this context is lost.)*

---

## Who runs the chain

One point worth clearing up before we move on, because it is the heart of the unit. After you have built two agents, you are the one who takes the output of the first and pastes it into the second. This feels like annoying manual work, and you might think you are just passing packages in the middle.

But you are not just passing packages. You hold the knowledge, you know what the first product is supposed to be, and you look at the summary that came out and approve that it is correct before it moves on. **This is exactly the review we talked about in the first unit.** The copy-paste is not the work, it is your control point.

And why manually at this stage, rather than letting the agents pass to each other directly? Because this way you understand how it works from the inside, and you keep the ability to stop and check each link before it runs forward. As chains grow, you will not hold all the links in your hand at once, but you will usually stay in the middle on purpose, at points where human review is worth the pause. We will see advanced coordination, how a long chain manages itself, later in the course. Here we have laid the foundation: link → product → link, and you are the control point between them.

---

## Putting it together

So, what did we have? In the real world, a task passes between professionals, each producing an intermediate product and passing it on. An agent can also be a link and not the end, when its scope is not the final product. To connect link to link, we add one letter, **N**, on top of SPOKE™, and that turns it into SPOKEN™. The N declares that the agent is part of a chain, who is next in line, and what they receive. Then, in the same chat, we ask the agent to build the next in line, and the chain builds itself.

Three questions to consolidate:
1. You wrote an N that says "the next link is an agent that prepares a presentation." What else must appear in the N for it to work?
2. Why is it important that building the second agent happens in the same chat as the first?
3. When is it **not** recommended to split into a chain and instead keep a single agent?

*(Answers: 1 - That the next agent receives my output as input, and what its final output is. 2 - Because in the same chat, the first agent already knows what its N is, so it builds the next one exactly according to what needs to pass between them. 3 - When it is a single role, or when the input is short and a single agent solves everything in one breath.)*

**Note to self:** In one sentence, what chain will you build in your work and what passes between the two links.

---

## Take it to your own world

Choose one real task from your work that actually splits in two, from one of the examples you saw or your own: research that ends in writing, strategy that ends in copy, a summary that ends in tasks. Build both links in a single chain: write N for the first link, expand it, and in the same chat ask to build the second. Run real input through both, and see that the product of the first feeds nicely into the second. If that happened, you have built a chain that works on your real work, not on an example.

---

## Quick reference

**SPOKEN™** = SPOKE™ + N. Self · Principles · Outputs · Knowledge · Execution · **Next** (who the next link is and what it receives as input).

**The N text** (for copying, above the existing SPOKE™):
```
N - next in the chain:
My output is an intermediate product, not the end.
The next link is [description of the next agent: what it does, what its final output is],
and it receives my output as input.
```

**Expansion prompt** (after you wrote N):
```
Above, I detailed an agent spec according to the SPOKEN method. Review the spec, organize it into logical parts, correct what I said, and expand it into a precise system prompt that an AI model will work well with as an agent. Make sure to include the letter N. Explain what you understood and wait for approval.
```

**"Build the next" prompt** (in the same chat):
```
Now build the next agent in the chain, matching the SPOKEN framework.
Describe it according to the five components, where its input is my output,
and its output is the final product. Explain what you understood and wait for approval.
```

**The rule:** A chain only when the two roles are truly separate, one preparing an intermediate product and the other turning it into a final product. If it is a single role, one agent is enough. And in any case: you are the control point in the middle, the knowledge and the review are yours.

**Where to next:** Now you know how to connect agents into links. But an agent that works on guesswork rather than real knowledge will build a weak chain. To give agents real-world knowledge, and to conduct serious research for them to build on, we will reach the **deep-research** unit. There we will see how to bring in knowledge from the world in an organized way, instead of letting the AI guess.
