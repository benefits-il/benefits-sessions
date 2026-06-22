# 🧠 Session 2 Summary: From a Single Prompt to a Self-Building System

The first session gave you a single assistant. This session takes you from "I built an assistant" to "I have a system that builds and feeds itself." This isn't five separate units that you'll forget by the end of the night, it's a single narrative arc. Every unit here solves the exact limitation exposed by the unit before it, and that is no accident. In the end, these five parts connect into one working system, and you are the one in control.

## Memory Layers™

AI doesn't actually remember. It is stateless, and every message is a fresh reload of the history, reading everything from scratch every single round. So instead of struggling to make it remember, we stop trying and keep the memory outside, in a repository you control. We mapped six memory layers, and in the first four, the agent only reads. The fifth layer, Notion via MCP, is the first one where it also writes, with on-demand retrieval: index → select → load. And this is where the big realization of the unit clicked: when information changes from moment to moment, a knowledge base that you can see and edit by hand beats any clever semantic retrieval. With this, we built the Benefit agent, ready out of the box, an agent with a living memory.

## Agent Chaining™

A single agent works alone, but real work almost never ends with a single link. In the real world, one professional prepares a part and hands it off, and an agent can also be a link rather than the end of the line. The dishwasher principle explains why we split: you don't load and unload at the same time, first it goes in and then it comes out, and that is how we build a train of thought where one step spawns the next. To connect link to link, we add one letter on top of SPOKE™, the letter N for Next (who is next in line and what do they receive), and SPOKE™ becomes SPOKEN™. And then the magic happens: in the very same conversation, you ask the first agent to build the next one, and the chain builds itself.

## Deep Research

Up to this point, we worked with knowledge we already had on hand. But to build well, and to act on real information instead of guesswork, you need to go out to the internet. Deep Research is not a chat and not Google, it is a research agent that runs on its own for five to thirty minutes and returns with a cited report while you do other things. Every good run relies on a research plan with five fields: objective, primary question, sub-questions, scope, and output format, and the research-architect skill builds these for you. Then, you run that same plan across several tools simultaneously, a pattern called Ensemble, and gather everything into one place, because each model reaches different sources.

## Meta-Agents™

Up to this point, you built every agent by hand, one by one, and it started to feel like a lot of work. So we make a different move: instead of building every agent yourself, you build one agent that builds all the rest. You feed SPOKE™ and SPOKEN™ to Claude, challenge them honestly, ask for a research plan on how the world actually builds agents, run it in parallel, and from the results, you build Banay, an agent that builds agents. There is one way to look at this entire process: SPOKE™ and SPOKEN™ are the multiplication table, and Banay is the calculator you build for yourself. You need to know the multiplication table before you touch the calculator, but from today on, the calculator does the work. This is the big transition, from "I built an agent" to "I built a tool that builds my tools."

## NotebookLM

Remember how we left the sixth layer, RAG, for later? We have arrived. NotebookLM is the tool that answers only from the sources you feed it, with citations to the exact source, and that is precisely the sixth layer. It also generates quick and diverse outputs from your material: a mind map, an infographic, a table, a guide. But the most important rule of this unit, and also its visual metaphor: NotebookLM is a sketch artist, not a printer. You take inspiration and raw material from it, but it will almost never be the final output. And in Hebrew, we stick to text and visual outputs, and do not touch Audio and Video.

## Putting It All Together

Take a look back for a moment at what you have in your hands. A living memory you control, agents connected in a chain where each feeds the next, real research that brings in knowledge from the world instead of guesses, an agent that builds the rest of your agents, and a tool that generates outputs solely from your own material. This is not a pile of separate techniques, it is a single system that sustains and feeds itself, and you are at its center. In the next session, we will enter Orbit, and there we will see how all these methods stop working one by one and start working together, on autopilot.
