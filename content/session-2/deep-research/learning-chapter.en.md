# When the AI Works for You for Half an Hour

Until now we worked with knowledge you already had in hand. You threw files at the agent, you told it about your world, you gave it context. But what happens when you do not have the knowledge yet? When you need to go outside, to the internet, and bring back information you do not have yet? That is exactly the moment for Deep Research, and it is not just a faster chat. (You will see why in a second.)

## What you will be able to do by the end

To tell Deep Research apart from a regular chat and from Google, to understand why every good piece of research rests on a research plan, to know the five fields that make up such a plan, and to run that same plan across several research tools at once. By the end you have in hand a first knowledge base gathered from several sources, not one hurried answer from one place.

**Before this chapter:** You already know what a Skill is, you built an agent according to SPOKE™, and you know the idea of input, context, and output. That is what we stand on here.

**What to have open:** A Claude account, and the research-architect Skill installed.

**Chapter map:** First we will understand what Deep Research even is, and how different it is from what you know. Then we will see why it must have a research plan, and break that plan into five fields on a real example. After that we will get to know the tool landscape, and why you run several in parallel. At the end you will take it to your own world.

---

## The story that starts it all

How long would it take you to build a market review on a new competitor? Two days? A week? Deep Research does it in a quarter of an hour, but it is not a chat and not Google. It is a third thing. And in Ben's words from the lesson: *"Deep Research is honestly real research on the internet."* Not a quick search, not a short summary. Real research, the kind someone would sit on for days and do for you.

And here is the part that changes how it feels. In a chat you sit in front of the screen and wait for the answer. In Deep Research you press run, and it goes off on its own for five to thirty minutes. In most cases it comes back after ten to twenty. You are not waiting. You go do other things, and when it finishes you come back to a report. That is why it feels so different. The AI is not answering you faster. It is working for you for a quarter of an hour and coming back with a cited product.

---

## Wait, but isn't this basically like asking a chat to search?

Good question, and a lot of people mix up the three. So let us sharpen the difference once, clearly.

**Google** gives you **links**. You get a list, and now it is on you to open them, read, and assemble the picture yourself.

**A chat** gives you **an answer**. It answers now, fast, off the top of its head or from a short search. Convenient, but without depth and without real sources you can lean on.

**Deep Research** gives you **a report**. It does not answer off the top of its head. It writes itself a plan, goes out to the internet, searches years back, reads many sources, synthesizes, and returns a full report with the links and sources it gathered from. This is a whole new category: a research agent that works autonomously.

The difference is not the speed. The difference is the report and the sources. A chat answers you now, Deep Research investigates and brings evidence.

---

## Cycle 1: Why you need a research plan

### The idea

Now the most important point in this unit, so sit with it for a moment. Every tool that can do Deep Research can also write itself a research plan. Which means that always, in every case, there will be some research plan behind the run. The only question is whose plan it is, yours or the one the model guessed for you.

And if you throw in a general question, you get a generic report. If you give a precise plan, you get exactly the information you wanted to gather, in a form you can work with afterward. That is the whole difference between a report that needs three more rounds and a report you can work with right away.

It is important you understand something: you will not write this plan by hand. A Skill will do it for you, and we will meet it in a moment. But before you let the Skill work, you have to know what is inside, so you can tell whether what came out is any good.

### The five fields

Every good research plan is built from five fields:

- **Goal** · what you want to get out of the research, what you will do with the report in the end.
- **Main question** · what you are actually asking, the central thing you want to know.
- **Sub-questions** · three to five sub-questions that break the main question down.
- **Scope** · where to search, and no less important, what is out of range.
- **Output format** · the form in which you want to receive the report.

### What it looks like

Take a contrasting example, two versions of the same research. The generic version: *"Review the AI market for education."* Out of that comes a broad, flat report that needs three more rounds. Now the precise version, the exact same topic with the five fields:

- **Goal:** to understand which platforms are a fit for a partnership, ahead of a business decision.
- **Main question:** what are the five leading AI platforms for financial education?
- **Sub-questions:** who is each one's target audience? How do they price? How much do they allow personalization? How do they hold up against regulation?
- **Scope:** only platforms for financial education, ages 25 to 40 in the United States. Out of range: general education tools that are not financial.
- **Output format:** a comparison table across four dimensions, with links to sources beneath it.

Notice how precise this is. It is no longer "tell me about the AI market for education." It is a plan that knows exactly what it wants, and returns a report you can hand straight to a client.

### Now you

Before you go on, take a moment with one topic that genuinely interests you, something from your own world, and try to fill in the five fields for it in your head. Just to get the feel of it. Do not strain for perfect phrasing, just see what questions come up for each field.

### Self-check

How will you know you have a good plan and not a generic question? If you can hand the plan to a stranger and they know exactly what to search for, where, and in what form to return it, that is a plan. If there is room left for guessing, it is still too general.

**Common mistake:** skipping the Scope field. Without "where to search and what is out of range," the model scatters energy in every direction and brings back a report that is broad but flat. The scope is what focuses it.

> **In your own words:** what is the difference between a generic question and a research plan, in one sentence?
> *(Example answer: a generic question lets the model guess what you want; a research plan defines a goal, questions, scope, and format for it, and therefore returns a report you can work with right away.)*

---

## Cycle 2: The Skill that writes the plan for you

### The idea

I promised you would not write this plan by hand, and that is true. The Skill called **research-architect** does exactly that: you give it a topic, and it builds you an organized research plan across the five fields. It even asks you clarifying questions before it sets off.

The name sounds like an agent, right? You are right that it sounds that way, but it is a Skill. You load it as is, without opening it. Here is the download and installation, to copy:

https://benefits-il.dev/orbit-plugin/research-architect.zip

Download -> in Claude: Settings -> Skills -> Upload skill -> choose the ZIP. (In Claude Code you can also drop it into `.claude/skills/` and run `/research-architect`.)

### What it looks like

A sample topic: an investigation of the world of teaching and learning and everything related to AI at conferences. When you run the Skill on a topic like this, it does not jump straight to a plan. It starts asking questions. In what language do you want the report? Because sometimes you will want a knowledge base in Hebrew, sometimes in English. Which tool is it for? What is at the center of the investigation, how AI is taught at conferences, tools for the teaching itself, or trends?

And only after it understands what you want, it puts out an organized plan: context and background, scope, sub-questions, and the format you want the report in. Exactly the five fields, beautifully phrased.

Worth knowing one more point: you do not have to come to the Skill empty-handed. It does ask clarifying questions, but usually, by the time you really get to it, you will come with information from outside. Not from scratch, but out of a project you are already working on according to STUDIO™, one you already have a clear picture of. You will not come and say "tell me about teaching" from scratch. You will come and tell it exactly what you need, and it will build a precise plan around that.

### Now you

The Skill is installed. Give it one topic from your own world, and watch a plan come back with a goal, a main question, sub-questions, scope, and format. If it asks you a question before it builds, great, that is exactly its job.

### Self-check

How will you know the Skill worked right? If it asked you at least one question before it put out a plan, and if the plan that came out covers all five fields. If it jumped straight to a plan without asking anything, you probably gave it so much information up front that there was nothing left to clarify, and that is perfectly fine too.

> **In your own words:** why is it good for the Skill to ask you questions before it builds the plan?
> *(Example answer: because clarifying questions turn a vague topic into a precise plan, and a precise plan returns a report you can work with, not a generic one.)*

---

## Cycle 3: The tool landscape, and running in parallel

### The idea

Now the question: where do you run this plan? And the answer is that there are tons of tools that do the same thing in 2026, and no two do it exactly alike.

Here are six sites where you can do deep search with no registration or a quick one. Think of them as one set, not as a competition:

- **Perplexity** · perplexity.ai. The fastest, brings citations inside the text.
- **Grok** · grok.com. Strong on what is happening right now.
- **Qwen** · chat.qwen.ai. Multimodal, can work on images and files too.
- **Arena** · arena.ai. Runs several models side by side and compares them.
- **Gemini** · gemini.google.com/app. Brings the most sources, lives inside Google's workspace.
- **Claude** · especially strong on your own files.

They all do more or less the same job, and each gets there from a different angle.

### Running in parallel, and your tool group

And here comes the power move, the thing you do in the moments you want a genuinely broad knowledge base. Instead of choosing one tool, you take the same research plan and run it in several tools in parallel. You start them all, let each one run on its own, go do other things in the background, and at the end you gather all the outputs into one place. The name of this pattern is **Ensemble**.

And then the good question comes up: is it really critical to run in several places? Can't you just run it in Gemini and be done?

The answer is yes, and this is the heart of it. The whole idea is that you go to several places in order to find different sources for the information. Every model thinks a little differently, and reaches different sources. One tool alone will give you one picture. But when you run the same plan in several tools, you get a broader pool, cross-checked and varied. Information that shows up in several of them is probably reliable, and unique information that shows up in only one widens the picture for you. You are not leaning on one source. You are building knowledge from several angles at once. That is the difference between one tool and several independent points of view that cross each other.

*(Note: how you actually merge all the outputs and cross-check them is a topic for a later unit. For now it is enough that you understand why you run several, and that you gather everything into one place.)*

### Now you

This is the live part. Soon, in the "Take it to your own world" section, you will run the plan the Skill built you, in several tools in parallel. For now, just hold the pattern in your head: start them all, leave, come back, gather into one place.

### Self-check

If someone asks you "why not just run it in Gemini and be done?", what will you answer? If you can say that different tools reach different sources and think differently, and therefore running in parallel gives a broad, cross-checked pool, you have got the core.

**Common mistake:** waiting in front of the screen until the first run finishes, and only then starting the next. No. You start them all in a row, and then you leave them all together. That is exactly the advantage: thirty minutes of the AI's work become a quarter of an hour of yours because everything runs in parallel.

> **In your own words:** what is Ensemble, and why is it stronger than running in one place?
> *(Example answer: Ensemble is running the same research plan in several tools in parallel and gathering everything into one place; it is stronger because different models reach different sources, so the pool comes out broad, varied, and cross-checked.)*

---

## Putting it together

So what did we have. **Deep Research** is not a chat and not Google, it is a research agent that goes out to the internet and comes back with a cited report, and runs five to thirty minutes while you do other things. Every good run rests on a research plan with five fields: Goal, Main question, Sub-questions, Scope, and Output format. You do not write it by hand, **research-architect** does that and asks you clarifying questions. And that same plan you run in several tools in parallel (Ensemble), and gather everything into one place, because different sources give a broad, cross-checked pool.

Three questions to consolidate:
1. What is the essential difference between a Deep Research report and a chat's answer?
2. Which of the research plan's fields is responsible for "where to search and what is out of range"?
3. Why is running in parallel across several tools better than one run in a single tool?

*(Answers: 1, Deep Research returns a cited report with real sources after researching for minutes, a chat answers now off the top of its head with no sources. 2, Scope. 3, because each tool reaches different sources and thinks differently, so you get a broad, varied, cross-checked pool.)*

**Note to self:** one sentence, which topic you would want to research first in Deep Research, and why.

---

## Take it to your own world

This is the moment to really run it. The order matters, so take it step by step.

**Step 1: the plan.** Open the Skill and give it one real topic from your own world. Let it ask you, approve, and take the ready plan. Here is the prompt to open the Skill, to copy:

```
I want to produce a research plan using research-architect in order to research [your topic].
Ask me the clarifying questions you need, then build an organized research plan with a goal, a
main question, sub-questions, scope, and output format. Write in English. Intended for several
different Deep Research tools. Explain what you understood and wait for approval to continue.
```

**Step 2: running in several tools.** Take the plan that came out, and run it in every Deep Research tool you have access to, out of the six: Perplexity, Grok, Qwen, Arena, Gemini, Claude. You start them all, and you leave. Do not wait for one before you start the next. The more tools you run in, the broader and more cross-checked the pool comes out.

**Step 3: gathering.** When all the runs come back, gather all the reports into one folder. This is your knowledge base, gathered from several different sources.

---

## Quick reference

**The three tools, one difference:** Google = links · chat = answer · Deep Research = a cited report (runs 5 to 30 minutes, run and forget).

**The five research-plan fields:** Goal · Main question · Sub-questions · Scope (where to search + what is out of range) · Output format. All of them built by **research-architect**, and it asks clarifying questions.

**The six sites for deep search:** Perplexity (perplexity.ai, the fastest) · Grok (grok.com) · Qwen (chat.qwen.ai) · Arena (arena.ai) · Gemini (gemini.google.com/app, the most sources) · Claude (on your own files).

**Ensemble:** the same plan, several tools in parallel, run and forget, then gather everything into one folder. Why several and not one? Because each model reaches different sources, and several tools are several independent points of view that cross into a broad pool.

**The run order:** a plan from the Skill → run that same plan in the several tools you have access to → gather everything into one folder.

**Where to next:** now you really run it. In the next unit, in the same session, **meta-agents**, you take exactly this pattern and turn it on one big question: how the world builds agents. From those Deep Research results you will build **Banay**, an agent that builds agents for you. This is the move from "I built an agent" to "I built a tool that builds my tools."
