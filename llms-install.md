# Installing the 8B MCP server

8B is a remote MCP server. There is nothing to clone, build or run locally, and no API key or account.

Add this server to the MCP settings:

```json
{
  "mcpServers": {
    "8b": {
      "type": "streamableHttp",
      "url": "https://mcp.8b.com/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

- Transport: Streamable HTTP. Authentication: none.
- After connecting, the server lists three tools: `explore_designs`, `get_design_brief`, `generate_site`.
- To check it, ask: "Make a landing page for my bakery Crumb in Lisbon with 8B." The result gives a preview link and a
  download link for one HTML file.

How to use the tools well: https://8b.com/mcp/index.md
