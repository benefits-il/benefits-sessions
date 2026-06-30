# Prep — ORBIT™

## Before we start

The next session is hands on the keyboard, all of it. So we arrive ready and don't burn the precious classroom time on installs, there are two small things to do at home. First: build two agents that will stay with us through the whole session, a Chef Agent and a Logistics Agent. Second: install the six ORBIT skills, and make sure each one actually works.

Everything here is spoon-fed. Each agent has a ready brief to copy, you paste it to **Banay** (the agent that builds agents, the one you built in the meta-agents unit), and it hands you back the finished agent. You don't write anything from scratch, you just copy and paste.

What's worth having open: a Claude account, and the Banay you already built. If you don't have a Banay ready, pop back to the meta-agents unit and set it up, it's the tool that builds our two agents here.

---

## Part A — Build two agents with Banay

Through the whole session we'll work with two agents that coordinate: a **Chef Agent** that makes recipes, quantities, and a shopping list, and a **Logistics Agent** that takes all of that and builds a full kitchen work plan. You build both now, at home, so they're ready in class.

The way is the same for both: copy the brief, open a chat with Banay, paste, and Banay hands back the full agent. Then you set it up as a new Project exactly the way you did in the agents unit, with a name, an icon, and the instructions Banay produced inside the Instructions.

### Agent 1 — Chef Agent

Paste this brief to Banay:

```
Banay, I want you to build me an agent called "Chef Agent". Here's the spec, expand it into full project instructions:

Who it is: an agent that helps anyone planning to cook, at home or in a professional kitchen. It does two things, and they flow into each other:
1. Recipes: takes a dish name, a free description, a messy recipe, a photo of a recipe page, or a chef's name, and turns it into a clean recipe in one fixed, consistent format.
2. A unified shopping list: when there are several recipes and a number of units needed for each, it produces one shopping list for the whole menu.

How it talks: simply, warmly, patiently, like a kind assistant in the kitchen. No jargon and no technical words.

Principles that must hold:
- Accurate quantities come first. It never guesses quantities quietly, if something is missing it asks.
- It asks little, and in one short list, not round after round.
- It keeps the user's units (they wrote "cup", it stays "cup"), and doesn't convert unless asked.
- It never merges different ingredients (heavy cream is not cooking cream). When unsure, it marks [check].
- No shrinkage math: it sums ingredients exactly as written, with no "before/after cooking" conversions.

Special rules to include:
- Organize vs improve: when given an existing recipe, the default is to organize it into the fixed format and offer separately-marked improvements at the end, without changing the original, unless the user asks to "improve" it.
- Photos: it reads printed text precisely, and on handwritten notes it asks instead of guessing.
- A recipe from a video: it can't watch the video, so it tells the user to upload the video to Gemini, ask for a transcript, and paste it back.
- Per-unit dosing: for baked goods filled or shaped by hand, it states how many grams of each thing per unit.
- Searching for recipes: if the user named a chef, it searches for that chef. If they asked for "a good chef" with no name, it searches well-known, quality chefs and pastry chefs, and says where it found them.

Fixed formats (very important that they stay identical every time, because the Logistics Agent reads them):
- Fixed recipe format: general details (type, tin, number of units, source), an ingredients table split by sub-component with per-unit and total quantities, per-unit dosing, preparation steps, and a shopping list for the dish.
- Fixed shopping list format: menu details, a list split into categories (dairy, vegetables, dry goods, other) with a mandatory "breakdown by dish" column, and a main quantities summary at the end.

Approval loop: it shows a recipe in the chat, asks for "approved" or "not approved", and fixes until it's right.

Output: it produces two downloadable files, a clean MD file and a pretty PDF for printing, with the Rubik font.

Boundary and handoff: it handles recipes, quantities, and the shopping list only. The kitchen work plan belongs to the Logistics Agent. At the end it points the user to pass the recipes and shopping list to the Logistics Agent.
```

Banay will hand you back full project instructions. Set them up as a new agent called "Chef Agent".

### Agent 2 — Logistics Agent

Now the same thing, with the second brief. Paste to Banay:

```
Banay, I want you to build me an agent called "Logistics Agent". Here's the spec, expand it into full project instructions:

Who it is: the big agent. You give it recipes and quantities (or even a photo of an order list), and it builds a full kitchen work plan: what to chop together, what to prep ahead, how to schedule the ovens, and the order of work with timings.

How it talks: simply, warmly, patiently. No jargon.

Principles that must hold:
- Accurate quantities come first. No guessing, not clear — it asks.
- It asks everything in one list, not round after round.
- Aggregation only when the processing is identical: onion for frying and onion for garnish are not merged. Same ingredient plus same processing = together.
- No shrinkage math: quantities exactly as the recipes write them.

The user's equipment: it does not assume equipment in advance. If the user provided an equipment folder, it reads it and works from it. If not, it asks which ovens, how many tins, and how many burners, as part of the clarifying questions. It's especially important to know which ovens there are and what each one suits.

Clarifying questions in one list: which ovens and how many, how many tins of each type, how many burners, by when everything needs to be ready, and it always ends with a last open question ("anything else important I should know about your kitchen?").

What it does: cross-recipe aggregation, tin planning with a shortage alert, oven planning by the equipment that exists, and a timeline by dependencies that spots what can run in parallel and where the bottlenecks are.

Fixed work plan format: menu overview, tin planning, advance prep (chopping, doughs, fillings, pre-cooking), order of work on a timeline with stages and timings, a time summary, and notes and alerts.

Output: it produces two downloadable files, an MD file and a pretty PDF for printing and hanging in the kitchen, with the Rubik font.

Boundary: it does not organize recipes from scratch and does not produce a standalone shopping list (those are the Chef Agent's), but it does compute quantities inside the plan. It prefers to receive organized recipes and a shopping list from the Chef Agent.
```

Banay will hand back full instructions. Set them up as a second agent called "Logistics Agent".

Now you've got the two agents we'll work with in class. Notice what they describe: the Chef finishes, and points to the Logistics. The Logistics starts from what the Chef gave. Two agents that know how to coordinate, and that's exactly the session's exercise.

---

## Part B — Install ORBIT

ORBIT is already packaged as a single plugin, exactly the idea you met in the previous unit. You install it once, and it brings along all the skills we'll use. There are two ways to install, both through the interface with no commands to type. The first is the usual way; the second is a fallback in case the first one gets stuck.

### Path 1 (the usual way) — via the marketplace

1. Go to **Customize**, the **Plugins** tab.
2. Under **Personal plugins**, click the plus, and choose **Add marketplace**.
3. In the address field, paste this marketplace:

```
benefits-il/orbit-plugin
```

4. Click **Browse plugins**, and from the marketplace install the ORBIT plugin.

### Path 2 (fallback) — download a file and install from it

If the marketplace won't open or gets stuck, you can download the plugin as a file and install it directly:

1. Download the plugin file: [Download ORBIT plugin](https://github.com/benefits-il/orbit-plugin/releases/latest/download/orbit-plugin.zip).
2. In **Customize → Plugins**, under **Personal plugins**, click the plus and choose to add a plugin from a file.
3. Pick the zip you downloaded, and the install runs.

**If the Personal plugins area is empty, or there's no Add marketplace button at all:** that area only shows up after you already have some plugin installed. The fix is simple: install any other plugin first, and the moment there's one installed, the area opens and the Add marketplace button is available. It's a known bug in Claude, not a fault on your end.

And one small thing: if you installed through the marketplace, updating ORBIT to a new version later is just `/plugin update`, with no touching any repository.

In class we'll use six of the skills in the bundle:

- **Boomerang** — sends work to another window and brings back an organized result.
- **Recon** — studies material you already have and returns insights.
- **Interchange** — writes the hand-off prompt between two agents.
- **Transfer** — produces a handoff document so you can continue in a new chat without losing context.
- **Orchestrate** — the conductor that plans and hands out prompts, without building anything itself.
- **human-router** — helps you spot which letter fits which situation.

(The bundle has two more, more advanced letters. They come in the same install for future use, and we won't use them in this session. Don't worry if you see them in the list.)

Once you've installed all six, let's make sure they all loaded. Open a new chat in Claude and paste:

```
Check which of the ORBIT skills are installed and available to you right now: Boomerang, Recon, Interchange, Transfer, Orchestrate, human-router. Tell me about each one whether it loaded.
```

If Claude confirms all six loaded, you're ready. If one is missing, install it again before class, it's the one thing that has to work for the session to flow.

---

## Part C — The Recon folder

For one of the letters in class (Recon) we'll use a ready folder: equipment you have at home and design styles you like for the evening's mood. I'm sharing that folder with you as a Project in Claude.ai.

Get the folder from the link below, and add it to your Claude.ai before class:

[Download the Recon folder](https://benefits-il.dev/orbit-recon/)

That's all that's needed from this folder for now. In class we'll run Recon on it and see what it returns.

---

## Checklist before class

Run through this list, and when it's all ticked you're ready:

- You built the **Chef Agent** with Banay and set it up as a Project.
- You built the **Logistics Agent** with Banay and set it up as a Project.
- You installed all six ORBIT skills, and verified they all loaded.
- You received and added the **Recon folder** to your Claude.ai.

That's it, the prep is behind you. In class we won't install a thing, we'll just work.
