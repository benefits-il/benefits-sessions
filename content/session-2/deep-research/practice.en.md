# Practice — Deep Research

## Before you start

In the video you saw what Deep Research is, and why it is not a chat and not Google but a third thing: an agent that goes out to the internet, genuinely researches, and comes back with a cited report. Now you get to try it yourself. Three exercises: you install the Skill that writes your research plan for you, you run a real research in a few tools at once and save it, and you sort out the tool landscape for yourself.

You come to class after you have already tried it, so in the session we can run straight on what you gathered.

What is worth having open: a Claude account, and access to at least one more research tool.

---

## Where Deep Research lives, and who really does it

In every tool this feature hides in a slightly different place, but it usually sits in the chat window, inside the menu that opens from the plus button (+). In most tools it is called Deep Research, and in Claude it is actually called Research. When you open a new tool, look for it there.

It is also worth telling apart two kinds of tools. There are tools that only search the internet and bring back sources quickly, like DeepSeek, Grok, and Arena. And there are tools that do real Deep Research, meaning they build a plan, go out to search in depth, and synthesize a cited report, like Claude, ChatGPT, Gemini, and Perplexity. We will use both kinds: the quick search is good for a fast check, and Deep Research for real research.

---

## Exercise 1 — Installing research-architect

You already know how to install a Skill. Now you install **research-architect**, a Skill with one single job: to take a topic and return an organized research plan, so you never have to write one manually.

1. Download the Skill from the ORBIT page, with the "download only the Skill" option: https://benefits-il.dev/orbit-plugin/research-architect.zip
2. Install it in Claude: Settings -> Skills -> Upload skill -> choose the ZIP file.
3. Test it: give it a sample topic, for example "the market for X", and make sure it returns a plan with the five fields:
   - **Goal** — what you will do with the report in the end.
   - **Main question** — the main question.
   - **Sub-questions** — three to five sub-questions.
   - **Scope** — where to search, and what is out of range.
   - **Output format** — the output format.

If you got a plan with all five fields, the Skill works. This is the same plan you used to have to write manually before every run.

---

## Exercise 2 — Deep Research on the world of Deep Research

Now you run a real research, and the topic is Deep Research itself: which tools exist and what sets each one apart. You will save the result to a file, and we will take it with us to class.

**Step 1 — the plan.** Open research-architect and paste this prompt. It asks the Skill to build a research plan about the world of Deep Research:

```
I want to produce a research plan using research-architect in order to research the world of
Deep Research: which tools exist that do deep research, what each one is, and what makes it
unique. Put emphasis on Perplexity, Grok, Qwen, Arena, Gemini, and Claude. Ask me the
clarifying questions you need, then build an organized research plan with a goal, a main
question, sub-questions, scope, and output format. Write in English. Intended for several
different Deep Research tools. Explain what you understood and wait for approval to continue.
```

The Skill will ask you a question or two, then return an organized plan. Approve it and take it.

**Step 2 — running it in a few tools.** Take the plan that came out, and run it as Deep Research in both Claude and Gemini. You start both runs, and you do not wait for one before you start the other. Each tool runs on its own for a few minutes, and in the meantime you are free.

**Step 3 — reading and saving.** When the runs come back, read both reports, and save the results into one MD file on your computer. This is your first knowledge base, gathered from two different sources. Save it somewhere you will find it, because we will take it to class and work on it there.

---

## Exercise 3 — The tool landscape

Now we will sort out everything you gathered. And instead of us telling you what each tool does, we will let your own research do it.

Open a new conversation, paste into it the two research reports you saved in Exercise 2 (the Gemini one and the Claude one), and after them this prompt:

```
Attached are two research reports on the world of Deep Research. Go through them, and extract
from them all the tools that appear. Show me a clear table with a column for each of these:
the tool name, whether it does real Deep Research or only searches the internet, what is
unique about it, and whether it requires registration. At the end of the table, mark which
tools are most worth my opening and starting to work with. Explain what you understood and
wait for approval to continue.
```

You got a table that sums up the whole tool landscape, from the research you ran, not from a ready-made list someone handed you.

And now open at least five of the tools, and save them in a favorites folder named "Deep Research" in your browser, so you have them on hand in one place. A few tools are accessible without registration or with a quick registration:

- **Do real Deep Research:** [Claude](https://claude.ai) · [ChatGPT](https://chatgpt.com) · [Gemini](https://gemini.google.com/app) · [Perplexity](https://perplexity.ai).
- **Quick internet search:** [DeepSeek](https://chat.deepseek.com) · [Grok](https://grok.com) · [Arena](https://arena.ai).

---

## More tools to explore, if you feel like it

Want to look further out? There is a whole other layer of tools that know how to search and research, some of them names you probably have not met. None of them are needed to finish the exercise — this is simply the full map, if you feel like wandering through it. These are the tools I roam among myself:

[Jina](https://search.jina.ai/) · [Consensus](https://consensus.app/) · [Elicit](https://elicit.com/) · [Undermind](https://app.undermind.ai/) · [Semantic Scholar](https://www.semanticscholar.org/) · [SciSpace](https://scispace.com/) · [Scite](https://scite.ai/) · [You.com](https://you.com/home) · [Exa](https://exa.ai/) · [Perplexity](https://www.perplexity.ai/) · [DeepSeek](https://chat.deepseek.com/) · [Grok](https://grok.com/) · [Mistral](https://chat.mistral.ai/chat) · [Qwen](https://chat.qwen.ai/) · [MiniMax](https://agent.minimax.io/) · [Claude](https://claude.ai/new) · [Gemini](https://gemini.google.com/app) · [Arena](https://arena.ai/) · [NotebookLM](https://notebooklm.google.com/) · [ChatGPT](https://chatgpt.com/)

---

## Materials and links

- **research-architect** — [download only the Skill](https://benefits-il.dev/orbit-plugin/research-architect.zip).
- **The tools:** [Claude](https://claude.ai) · [ChatGPT](https://chatgpt.com) · [Gemini](https://gemini.google.com/app) · [Perplexity](https://perplexity.ai) · [DeepSeek](https://chat.deepseek.com) · [Grok](https://grok.com) · [Arena](https://arena.ai).
