# 8B AI Website Builder

Make a website with [8B](https://8b.com) from your AI assistant. Describe your business and the assistant does the rest:

1. It picks an 8B design.
2. It writes every text for your business and adapts the colors, fonts and photos.
3. It shows you a live, animated preview.

Ask for changes in plain words. When you like the site, download it as one HTML file.

It works with any assistant that supports MCP servers over HTTP. No account or API key is needed.

**MCP server:** `https://mcp.8b.com/mcp`

## Claude

**claude.ai and Claude Desktop:**
1. Open Settings → Connectors → Add custom connector.
2. Paste `https://mcp.8b.com/mcp`.
3. In a new chat, ask: "Make a website with 8B for my bakery".

The preview appears as a card in the conversation.

**Claude Code:**

```
/plugin marketplace add 8bsite/8b-ai-website-builder
/plugin install 8b@8b
```

## Other assistants

These use the same server. Where the app can't show a preview card in the chat, the assistant gives you a link to the preview.

**ChatGPT:** Settings → Apps & Connectors → Create, then use `https://mcp.8b.com/mcp` as the server URL. This needs developer mode, depending on your plan.

**OpenAI Codex:** add to `~/.codex/config.toml`:

```toml
[mcp_servers.8b]
url = "https://mcp.8b.com/mcp"
```

**Cursor:** add to `~/.cursor/mcp.json`:

```json
{ "mcpServers": { "8b": { "url": "https://mcp.8b.com/mcp" } } }
```

**VS Code (Copilot):** add to `.vscode/mcp.json`:

```json
{ "servers": { "8b": { "type": "http", "url": "https://mcp.8b.com/mcp" } } }
```

**Skill:** agents that read Agent Skills (`SKILL.md`) can use [`skills/8b-site`](skills/8b-site/SKILL.md). It teaches the assistant the steps: choose a design, write the site, build the preview. The Claude plugin already includes it.

## Tools

- `explore_designs` lists the 8B designs and the kinds of business each one suits.
- `get_design_brief` returns every text, color, font and photo of a design, with hints and length limits.
- `generate_site` builds the site, shows the preview and applies later changes.

## Data and support

- [Privacy policy](https://8b.com/privacy.html) (section "8B AI Website Builder for Claude")
- [Terms](https://8b.com/tos.html)
- Support: s@8b.com
