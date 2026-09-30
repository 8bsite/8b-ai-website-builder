# 8B AI Website Builder for Claude

Make a website with [8B](https://8b.com) without leaving Claude. Describe your business and Claude does the rest:

1. It picks an 8B design.
2. It writes every text for your business and adapts the colors, fonts and photos.
3. It shows you a live, animated preview right in the conversation.

Ask for changes in plain words. When you like the site, download it as one HTML file. No account or API key is needed.

## Install

**claude.ai and Claude Desktop:**
1. Open Settings → Connectors → Add custom connector.
2. Paste `https://mcp.8b.com/mcp`.
3. In a new chat, ask: "Make a website with 8B for my bakery".

**Claude Code:**

```
/plugin marketplace add 8bsite/8b-ai-website-builder
/plugin install 8b-ai-website-builder@8b
```

## Tools

- `explore_designs` lists the 8B designs and the kinds of business each one suits.
- `get_design_brief` returns every text, color, font and photo of a design, with hints and length limits.
- `generate_site` builds the site, shows the preview and applies later changes.

## Data and support

- [Privacy policy](https://8b.com/privacy.html)
- [Terms](https://8b.com/tos.html)
- Support: s@8b.com
