---
name: site
description: Build a website with 8B. Use when the user asks to make, create or design a website, landing page or homepage for a business, project, event or person, or wants to see what their site could look like.
---

# Build a site with 8B

1. Work out what the site is for, the name of the business or project, and the language of the site (the user's language unless they say otherwise). If the name is missing, ask once; if the user doesn't care, use a short working name. Don't ask for more: invent plausible details and say the user can change them.
2. Call `explore_designs` and choose the design whose `fits` and `style` suit the business best. Say in one line what look you chose and why, describing the look itself (colors, type, mood) rather than the design id.
3. Call `get_design_brief` for it with `language` set to the site's language code (for example `"ru"`), so the length limits fit that language. Write the whole site for the user's business:
   - **texts**: a new value for every field, following each field's `hint` and `max`; where a field has `word`, no word may be longer than that. Keep `{1:...}` markers. Names, prices, addresses, reviews and team members should be plausible for this business; the user will replace them.
   - **colors**: a palette that suits the business, derived from the design's palette so the layout still works. Keep the readable pairs named in each color's `role`.
   - **fonts**: if the site is not in Latin script, replace every font with `cyrillic: false` by a Google Fonts family with the needed glyphs and a similar character. Otherwise change fonts only if the business needs a different mood.
   - **images**: for each photo, following its `hint`, an English Unsplash search query and a short description of the photo in the site's language: `{"query": "...", "alt": "..."}`. Photos of the same kind share one query (all team portraits, all product shots): each place still gets a different photo. Usually 3–8 distinct queries cover the whole site. Where a photo must match its text, split the query by it: portraits of named people get "male … portrait" or "female … portrait" to match each name.
4. Call `generate_site` with `design_id`, `site_name`, `language`, `texts`, `colors`, `fonts` and `images`. If the result lists warnings (length, long words, fields not filled), send just those texts again with `base_preview_id`.
5. Show the result:
   - In chat, the preview appears as a card in the conversation. Tell the user that **Open preview** shows the live site full screen.
   - Where no card is shown (for example in Claude Code), give `preview_url` as a link. If a built-in browser tool is available, open `preview_url` in it so the user sees the site with its animations.
6. Mention once that the finished site can be downloaded as one HTML file (the **Download** button, or `download_url`). Don't repeat the link in later messages unless the user asks.
7. For changes ("warmer colors", "another headline", "the clinic is in another city"), call `generate_site` with `base_preview_id` set to the `id` of the preview being changed, and only the values that change. Everything else is kept, so don't send the other texts again.
