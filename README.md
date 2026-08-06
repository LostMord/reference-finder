<div align="center">
  <img src="./assets/logo.svg" width="128" alt="Reference Finder logo">

# Reference Finder

**Stop designing from vibes alone.**

A plugin for Codex and Claude Code that searches Pinterest, curates strong visual references, and helps you choose a clear design direction before implementation begins.

</div>

## What it does

Tell Reference Finder what you are designing: a landing page, dashboard, product card, mobile navigation, or an entire website.

It will:

- turn your brief into focused Pinterest searches;
- collect and filter relevant visual references;
- present a diverse shortlist instead of a random image dump;
- explain what each reference is useful for;
- ask which directions feel right;
- convert your choices into practical design constraints.

The plugin keeps research separate from implementation. It will not redesign the project or generate assets until you approve the direction.

## How it works

1. **Describe the task**

   Tell the agent what you are building and what kind of feeling you want.

2. **Explore different directions**

   Reference Finder searches Pinterest using several focused queries and removes duplicates, filler, and irrelevant results.

3. **Choose your references**

   You receive a compact shortlist with previews, direct Pin links, and notes about composition, typography, color, imagery, or motion.

4. **Lock the direction**

   Pick up to three references and explain what you like, or what should never appear in the final design.

5. **Start designing**

   The agent turns your selection into a clear visual direction and waits for approval before touching the project.

## Try it

```text
Find Pinterest references for a premium architecture portfolio.
Focus on editorial typography, restrained colors, and unusual project navigation.
```

Or simply:

```text
Use Reference Finder before we redesign this page.
```

## Install for Codex

Clone the repository:

```bash
git clone https://github.com/LostMord/reference-finder.git
```

Then connect the cloned directory as a personal plugin source in Codex and install **Reference Finder**.

## Install for Claude Code

Add the public marketplace and install the plugin:

```bash
claude plugin marketplace add LostMord/reference-finder
claude plugin install reference-finder@lostmord-tools
```

Enable the native Chrome integration with `/chrome`, or start Claude Code with:

```bash
claude --chrome
```

Claude in Chrome shares the browser's signed-in session, so you can sign in to Pinterest normally without exposing passwords, cookies, or tokens to the plugin.

## Requirements

### Codex

- Codex with Browser integration
- An authenticated Pinterest session in the selected browser

### Claude Code

- Claude Code 2.0.73 or later
- Claude in Chrome extension 1.0.36 or later
- Chrome integration enabled with `/chrome` or `claude --chrome`
- A direct Anthropic Pro, Max, Team, or Enterprise plan

## A reference is a direction, not a template

Reference Finder extracts principles instead of copying someone else's work pixel for pixel.

Use references to understand what feels right. Then build something original.

---

Made by [LostMord](https://github.com/LostMord).

