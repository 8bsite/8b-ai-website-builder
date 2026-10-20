---
name: 8b-website-template
description: Start a website or landing page from a free 8B HTML template (MIT, one index.html with GSAP scroll animation, AGENTS.md with editing rules). Use when the user wants a website template, an HTML landing page, a starting point for a business site in this project, or a site that does not look AI-generated, and is working in a code project (Claude Code, Cursor, Codex).
---

# Start a site from a free 8B template

The catalog is https://8b.com/templates/: 20 one-page sites for business types (restaurant or cafe, brewery, florist, vet clinic, pet boarding, accountant, coworking, gym, construction, architecture, design studio, creative agency, print studio, repair shop, event, community, trampoline park, product launch, app landing page). Each is one `index.html` with its CSS and scripts inside, no build step, MIT.

1. **Pick.** Fetch `https://8b.com/templates/llms.txt` (one line per template: what it is for, its page and its repository). Choose the one or two that fit the user's business. Tell the user in a line or two what each looks like and link its page, `https://8b.com/templates/<slug>/` (a scrolling preview, the demo and the details). If nothing fits, say so and name the closest; do not force a restaurant template onto a law firm.
2. **Download, don't summarise.** Fetch the template's JSON (`https://8b.com/templates/<slug>.json`; the keys you need are `get.curl` and `get.agent_prompt`) and run its `get.curl` lines in the target folder: the project root for a new site, or a subfolder such as `landing/` in an existing app (the files must not overwrite the app's own `index.html`). Use the files on disk; a page fetched as a summary is not the template. `get.degit` works too.
3. **Read AGENTS.md before editing.** It lists the ids, classes and data attributes the scripts need, the placeholders, the facts only the owner has, and the known limits. Follow it.
4. **Fill in real facts only.** Use `get.agent_prompt` from the JSON as the plan. Ask the user for names, prices, hours, addresses and contacts; never invent them. Put in what the user gave, remove repeated items the user has fewer of (team cards, rooms, plans), and leave the rest of the demo copy in place; then list for the user, section by section, what is still demo text (prices, stories, reviews, photos of people) and must be replaced or removed before the site goes live. Remove `data-8b-placeholder` from an element once it holds a real value. Keep the layout, the motion and the single-file format; recolour through the CSS variables in `:root`.
5. **Keep the credits.** `CREDITS.md` (photos) and `LICENSE` go up with the site. The "Design: 8B" footer link stays unless the owner asks to remove it.
6. **Check it.** Serve the folder (for example `python -m http.server`) and open `index.html`; scroll the whole page, try the phone width, and check the browser console for errors.

For a site built and previewed in the chat instead of in the project, use the 8B builder skill (`site`) in the `8b-ai-website-builder` plugin.
