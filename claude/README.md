# 8B AI Website Builder for Claude

Make a website with [8B](https://8b.com) without leaving Claude. Describe your business, and Claude picks a fitting 8B design, writes every text for you, adapts the colors, fonts and photos, and shows a live, animated preview right in the conversation. Ask for changes in plain words; when you like the site, download it as one HTML file.

## What's inside

- **Connector `8b`** — the 8B MCP server with three tools:
  - `explore_designs` — lists the 8B designs: look, structure and the kinds of business each one suits (read-only)
  - `get_design_brief` — returns every text field, color, font and photo of a design with a hint for each (read-only)
  - `generate_site` — builds the site from the design and the values Claude wrote, shows it in the conversation, and applies later changes
- **Skill `site`** — teaches Claude the order of steps: choose a design, write the site for your business, build the preview, show it

## Examples

- "Make a website for my ice cream factory «Plombir»"
- "I run a dance studio in Lisbon, show me what our site could look like"
- "Landing page for a legal and tax advice firm"

## Data

To build a preview, the plugin sends the 8B server the business name, your request, the chosen design and the texts, colors, fonts and photo search queries Claude wrote for it. The server looks up photos on Unsplash by those queries. Previews are stored by 8B and are reachable by their link. Privacy policy: https://8b.com/privacy.html

## Support

s@8b.com
