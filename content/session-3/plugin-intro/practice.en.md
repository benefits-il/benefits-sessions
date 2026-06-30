# Prep — What is a Plugin

## The unit video

<!-- video set: DMX81pA1dYE (youtu.be/DMX81pA1dYE, unlisted) — the engine builds the embed from video: in the frontmatter when this moves to the site -->

The video explains the idea in a nutshell. You can watch it first, or just jump straight into the practice below.

## Before we start

By now you've built skills, connected connectors, run commands, and set up agents. Each one stood on its own, and each one needed its own separate install. A plugin is simply a package — a way to gather a few of those tools into one bundle, and install them all in a single move.

So a plugin isn't a new concept to learn. It's a package of things you already know. Open up a plugin, and inside you'll find exactly these pieces:

- **Skill** — one capability. Something the system knows how to do.
- **Connector** — a door to an outside tool.
- **Command** — an action that starts with a slash and fires off something with one click.
- **Agent** — a persona with a role (a sub-agent) that handles a task end to end.

And one more thing, so you don't get confused later: chances are you won't build a plugin for yourself. A plugin is mostly a way to **package** a set of tools and hand it to someone else, or to take a package someone already made and bring it to you. That's exactly what you'll do here — install a rich, ready package and play with it. Building a plugin of your own, we'll do together in class.

And most important of all: everything you build here is about **your own world**. Not some stranger's company, not a demo — your brand.

What needs to be ready: Claude Desktop with Cowork, exactly like at the end of the previous unit. The install happens inside Cowork, so if it's already open for you — you can start.

## Installing BUILD YOUR BRAND

The plugin we'll play with is called **BUILD YOUR BRAND**. You install it through the Cowork interface, without typing a single command:

1. In Cowork, go to **Customize**, then the **Plugins** tab.
2. Under **Personal plugins**, click the plus, and choose **Add marketplace**.
3. Type the marketplace address `benefits-il/brand-studio`, and click **Browse plugins**.
4. From the marketplace, install **BUILD YOUR BRAND**.

**If you get stuck on the install:** sometimes the Personal plugins area looks empty, with no Add marketplace button at all. That's a known bug in Claude, not a fault in the plugin — the button only shows up after you already have some other plugin installed. The fix is simple: install any other plugin first, and the moment there's one installed, the Add marketplace button opens up and you continue as usual.

## Connect once — Higgsfield and Gmail

Before you start, there are two short connections to switch on just once:

- **Higgsfield** — this is the one that draws the images. In the Connectors list, choose **Add custom connector**, name it Higgsfield, paste in the address `https://mcp.higgsfield.ai/mcp`, click **Connect**, and sign in with a Higgsfield account. It's free, no credit card.
- **Gmail** — for the email drafts. Make sure it's connected. Every email that gets created is always saved as a **draft** — nothing goes out without you.

## The chain — five steps, window after window

Now the magic. BUILD YOUR BRAND works as a chain: five skills, each one running in a new window, and all of them reading and writing to the same work folder. Nothing to download, nothing to attach — the work folder is what carries the information from window to window, and each step simply picks up where the last one left off.

Each step spells out what it produces, so you know exactly what you're getting in hand:

1. **`/start-here`** — start here. The plugin asks which folder to work in, then three easy questions: who you are, what you do, and what your role is. From that, it builds you a rich starter set for the brand — a brand page, a voice profile, a post idea, welcome points, a visual brief, and more — then stops. Don't have a business, or not sure? The plugin invents a whole direction and fills it in on its own, without asking anything of you.
2. **`/marketing-email`** — reads the folder and produces a marketing email in your brand's voice, plus a ready draft in Gmail.
3. **`/design-system`** — produces a rendered, good-looking design-system page, plus a tokens file that every step after it builds on, so everything stays consistent.
4. **`/carousel`** — a multi-slide carousel, locked to the colors and tokens of your design system.
5. **`/landing-page`** — an animated, standalone landing page, about your brand.

Every skill ends by telling you to open a new window and run the next one. You don't have to do all five in a row, but it's worth going all the way — the carousel and the landing page are the moment you see a whole brand assemble itself in front of your eyes.

## What you saw here

Inside one package, you met all four pieces together: **skills** (the five steps), **agents** (a content writer and a visual producer working in the background), **commands** (every `/` command you ran), and **connectors** (Higgsfield and Gmail, which opened a door to the outside). That's all a plugin is — a package that gathers all these pieces into one place, and installs them in a single move.

## Checklist before class

Run through the list, and when it's all ticked you're ready:

- You installed **BUILD YOUR BRAND** from Customize, the Plugins tab.
- You connected **Higgsfield** and **Gmail**.
- You ran `/start-here`, answered the three questions, and got the starter set in your folder.
- You continued at least one more step in the chain: email, design system, carousel, or landing page.

That's it. Now you know a plugin is really just a package of familiar pieces, and you've also seen how the output of one step becomes the raw material for the next. In class we'll start assembling a plugin of our own.
