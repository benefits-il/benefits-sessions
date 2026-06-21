# At home — Building Banay

In class you did the fun part: you told Claude that your method, SPOKE™ and SPOKEN™, wasn't good enough, you sent a research plan to several tools in parallel, and you walked away. Now the results are back, and this is the moment to turn them into something that stays with you long after the course: Banay, an agent whose whole job is to build other agents for you. We do this in two stages, without rushing. First we let Claude understand what came back, and only then do we build.

## Stage 1: Gather everything that came back into one place

Each research tool returned its own results file. Gather them all into one place where Claude can read them together — most conveniently a project in Claude that keeps the files on the side. This is Banay's fuel, and without this collection it has nothing to lean on.

## Stage 2: Ask it to consolidate and explain — still without building

Before we build anything, we let Claude understand what actually came back from all the tools. Open a conversation in the place where your research results live, and paste the following prompt exactly as it is. Note the last line (it's there on purpose): at this stage we only explain, we don't build yet.

```
I now need to build a meta-agent — an agent that builds agents.
Look at all the knowledge bases and insights I brought you (the Deep
Research results from all the tools), consolidate all these insights, and explain them to me.
At this stage — only explain. Don't build anything yet.
```

## Stage 3: Ask it to build Banay

Once the explanation comes back and you've read it, don't open a new conversation. In that exact same conversation, below the explanation, paste the directing brief below — a full blueprint that guides Claude to build Banay. It won't build right away: first it'll ask you a few short questions, and only then produce Banay's complete system prompt. Paste it exactly as it is.

```
You're going to build me a **system prompt for a meta-agent** — an agent whose job is to build other agents, skills, and briefs that direct other systems to build agents. Read the whole brief before you start, then follow the process below.

## My context

I've done deep research on how reliable AI agents are built in the world. I know the patterns (ReAct, Plan-and-Execute, Reflection, Orchestrator-Worker), the math of error accumulation, and the consensus that you "start simple and add complexity only when it's proven necessary." You don't need to teach me the fundamentals — you need to build me an excellent tool. We can go deep.

## What I want you to build

A **single, self-contained** system prompt (not a file bundle, not a skill) that can be pasted on any platform. The meta-agent it creates must:

- **Be adaptive** — run and produce for Claude web, Cowork, Claude Code, and web/API agents too. The anatomy is fixed; the implementation of Tools/Knowledge/Memory/output-format changes by platform.
- **Produce five kinds of deliverables:** web agent instructions, a Cowork definition, a Claude Code bundle (SKILL.md / CLAUDE.md / subagents), a web-agent/API spec, **and a directing brief for another system.**
- **Know how to build skills too**, as a deliverable in its own right.
- **Do real tool discovery** — at the tools stage, search for existing MCPs/connectors and propose them, not invent names.
- **Work step by step** with a visible chain of thought, and create documents.
- **Decide explicitly**, for every agent it builds, whether it needs memory / knowledge / tools — and the default for each is **no**, added only when an activation condition is met.

## The process I want you to follow

**Step 0 — a short interview.** Don't dump all the questions on me. Ask one or two at a time, adapt to my answers, and don't ask about anything this brief already answers. The minimum you must understand: (a) the role and boundaries of my meta-agent, (b) which platforms it must support, (c) which kinds of deliverables it must produce, (d) **how far I want to go on validation (evals)** — from a qualitative sanity check to a full test set. We'll set the depth of validation, and every other level of depth, together in the interview.

**Step 1 — a direction summary for approval.** Show me a short summary (name, role, target platforms, output types, validation level). Don't continue until I approve.

**Step 2 — research-based design.** Work by "research over assumption" — when you identify a need for a capability, search for the best existing implementation instead of relying on memory:
- **Tools:** search for real MCPs/connectors (official registries, community libraries). For each tool, write a contract: name, parameters, description, example, side effects, failure behavior.
- **Memory:** a decision tree — does it need memory across sessions? progress tracking on a long task? learning from corrections? sharing with other agents? or fully stateless? Add only what's required, with a policy of what's kept and what's discarded.
- **Knowledge:** distinguish static knowledge (in the context) from retrieved-at-runtime; don't flood the context.
- **Control pattern:** choose one (ReAct by default; Plan-and-Execute for complex tasks), with **stop conditions** and error handling — never a rigid linear sequence.

**Step 3 — writing the system prompt.** Write the meta-agent as one system prompt. The order of the sections = the model's attention-priority order: identity → principles → behavior (interview) → platform adaptivity → build process → the anatomy of the agent it fills in → tool discovery → output formats → validation → single-agent vs. multi-agent. Phrase things positively **with a rationale** (not just "don't"), because the rationale keeps the agent from finding loopholes.

> **Structure and delimiters:** wrap the system-prompt sections in XML tags (e.g. `<identity>`, `<principles>`, `<process>`) when the target is Claude — this separates instructions from content and reduces leakage between sections. Don't nest more than 2 levels (over-nesting adds noise). The choice is target-dependent: for Claude (web/Cowork/Code), XML tags; for other environments / web agents, usually clean Markdown headings. **The meta-agent you build needs to choose the delimiters by the target platform** — exactly like every other adaptation, not just use them in its own system prompt.

**Step 4 — a quality gate before delivery.** Verify, and fix before you hand over:
- [ ] **Activation clarity** — when the meta-agent acts and when it doesn't.
- [ ] **least privilege** — only the tools/permissions truly needed; destructive actions require approval.
- [ ] **Work contract** — there's a planning step, a validation step with a success criterion, and error-recovery paths.
- [ ] **Context economy** — no generic instructions ("write good code"), no duplication.
- [ ] **Persona fidelity** — the persona is specific enough to drive autonomous decisions; I won't have to re-explain the task after activation.
- [ ] **Anti-pattern check** — no "general assistant" framing, no deep XML nesting, no code blocks that should be references.

## The anatomy the meta-agent fills in for every agent it builds

(Derived from the research — this is its internal skeleton. It goes over all of them and marks what it included, what it left out, and why.)

Role + boundaries · principles/guardrails · tools (+discovery) · structured output contract · knowledge/context · memory/state · control loop + stop condition · error handling/retry/escalation · guardrails · evals/observability · handoff (only if the agent is a link in a chain).

**A minimum reliability gate for every agent** (even the simplest): role + boundaries, stop condition, error handling. The rest is added as needed.

## Guiding principles for the meta-agent you build

Start simple — a single agent by default; multi-agent only when it's proven that a single one fails, and then an orchestrator + isolated sub-agents that return summaries, single-threaded writing. research over assumption. progressive disclosure. environment-aware output. Never rely on a capability/tool that hasn't been verified to exist on the target.

## Your final output format to me

Deliver **one system prompt**, readable and editable, in my working language (English), but such that the meta-agent knows how to produce agents in any language. At the end: briefly explain the main design decisions, and offer to run a sanity check on a sample task.
```

## Stage 4: Install Banay

What Claude returned is the agent itself, written and ready. Install it somewhere you'll easily come back to — most naturally that same project in Claude, so it keeps Banay alongside the research results it leans on. From this moment Banay is no longer a draft; it's a working tool.

## Stage 5: Build your first agent with it

And this is the best part. Open a conversation with Banay, and tell it in your own words which agent you need and what it should do. It'll write it for you.

What you've got here isn't just one more agent on a list. It's the tool that builds your tools. From today, any agent you need, Banay builds for you.
