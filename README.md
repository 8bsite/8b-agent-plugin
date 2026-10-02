# 8B AI Website Builder for AI agents

Free AI website builder for Cursor, VS Code with GitHub Copilot, OpenAI Codex, Kiro, Gemini CLI, Cline and any other
agent that takes an MCP server. Your agent creates a new website or landing page from scratch: it picks an 8B generated
design, writes every text, color, font and photo search for the business, and the 8B server builds the animated site.
You get a preview, edits in plain words and one HTML file to download. No account, sign-in, API key or credits.

- MCP server: `https://mcp.8b.com/mcp` (Streamable HTTP, no authentication)
- Tools: `explore_designs`, `get_design_brief`, `generate_site`
- Documentation for agents: https://8b.com/mcp/ (Markdown: https://8b.com/mcp/index.md)

This repository is the plugin package: the MCP server configuration plus a skill that tells the agent when to use 8B
and how to fill a design. It follows [Agent Plugins 1.0](https://agent-plugins.org/) and also carries a Gemini CLI
extension manifest. The server itself runs at 8B; nothing runs on your computer.

## Install

| Client | How |
|---|---|
| Cursor | **Add to Cursor** on https://8b.com/mcp/cursor.html, or add `mcp.json` to `.cursor/mcp.json` |
| VS Code with GitHub Copilot | Command Palette → **Chat: Install Plugin From Source** → `https://github.com/8bsite/8b-agent-plugin`, or **Install in VS Code** on https://8b.com/mcp/vscode.html |
| OpenAI Codex | `codex mcp add 8b --url https://mcp.8b.com/mcp` (details: https://8b.com/mcp/codex.html) |
| Gemini CLI | `gemini extensions install https://github.com/8bsite/8b-agent-plugin` |
| Kiro | Add `{"mcpServers": {"8b": {"url": "https://mcp.8b.com/mcp"}}}` to `.kiro/settings/mcp.json` (details: https://8b.com/mcp/other-clients.html#kiro) |
| Cline | Ask Cline to install the MCP server from this repository (it follows `llms-install.md`) |
| Claude and Claude Code | Use the Claude plugin: https://github.com/8bsite/8b-ai-website-builder, or see https://8b.com/mcp/claude.html |
| Any other MCP client | Add a remote server with the URL `https://mcp.8b.com/mcp`, no authentication: https://8b.com/mcp/other-clients.html |

Then ask: "Make a landing page for my bakery Crumb in Lisbon with 8B."

## What you get

- A finished, animated one-page site in an 8B generated design, written for the business
- A preview link to open and share; edits in plain words, rebuilt in about a second
- One HTML file to download and host anywhere. The design code can be used and edited for any site, including commercial
  ones and client work; it cannot be resold or distributed as a template or theme. No credit is required

Limits: one page with fixed sections, no backend, forms only show a thank-you message, photos come from Unsplash
searches. Previews are kept for 90 days after they were built or last downloaded. Details: https://8b.com/mcp/

## Privacy, terms and support

- Privacy: https://8b.com/privacy.html
- Terms: https://8b.com/tos.html
- Support: s@8b.com, or an issue in this repository

8B is made by 8b Tech Ltd. Plugin files are MIT licensed.
