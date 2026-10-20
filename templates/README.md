# 8B Website Templates for Claude Code

A skill that starts a website from one of the [free 8B templates](https://8b.com/templates/): 20 one-page sites for business types (restaurant, vet clinic, accountant, coworking, design studio, product launch and more). Each is one `index.html` with GSAP scroll animation, no build step, MIT, with an `AGENTS.md` that tells the agent what to keep and what to replace.

Ask for a site ("make a landing page for my coworking space from a template") and the agent:

1. picks the template that fits the business and shows you its live demo;
2. downloads `index.html`, `AGENTS.md`, `LICENSE` and `CREDITS.md` into the project;
3. replaces the demo copy with your real facts, asking for anything it does not know.

## Install

**Claude Code:**

```
/plugin marketplace add 8bsite/8b-ai-website-builder
/plugin install 8b-website-templates@8b-ai-website-builder
```

**Other agents (skills CLI):**

```
npx skills add 8bsite/8b-ai-website-builder
```

**OpenDesign:** `od plugin install https://github.com/8bsite/8b-ai-website-builder/tree/main/templates/skills/8b-website-template`

No account, API key or MCP server is needed: the skill reads https://8b.com/templates/llms.txt and downloads from GitHub.

## Good to know

- Templates are one page each, with no database, checkout or accounts. Forms need a form service (Formspree, Netlify Forms) to send anything.
- Photos load from Unsplash, the motion libraries from jsDelivr; credits are in `CREDITS.md`.
- Browse them all with live previews: [8b.com/templates](https://8b.com/templates/). Source: [github.com/8bsite](https://github.com/8bsite).
