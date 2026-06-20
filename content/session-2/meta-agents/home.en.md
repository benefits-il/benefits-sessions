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

Once the explanation comes back and you've read it, don't open a new conversation. In that exact same conversation, right below the explanation you got, paste the following prompt. Now Claude builds the agent itself, out of the same insights it just organized for you.

```
Now I want to build an agent that builds agents, based on all these insights.
This agent is going to live on all kinds of platforms and needs to fit them all —
write it in an adaptive way. It should help me with anything to do with
creating the content of agents: if I need skills — it should know how to build
skills too. It needs to know not just how to write an agent's instructions, but also how
to guide another system to build an agent. Call it Banay.
```

## Stage 4: Install Banay

What Claude returned is the agent itself, written and ready. Install it somewhere you'll easily come back to — most naturally that same project in Claude, so it keeps Banay alongside the research results it leans on. From this moment Banay is no longer a draft; it's a working tool.

## Stage 5: Build your first agent with it

And this is the best part. Open a conversation with Banay, and tell it in your own words which agent you need and what it should do. It'll write it for you.

What you've got here isn't just one more agent on a list. It's the tool that builds your tools. From today, any agent you need, Banay builds for you.
