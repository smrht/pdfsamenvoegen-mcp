# Installing PDF Samenvoegen in Cline

This is a hosted remote MCP server. There is nothing to clone, build or install.

Add this entry to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "pdfsamenvoegen": {
      "type": "streamableHttp",
      "url": "https://pdfsamenvoegen.nl/mcp",
      "disabled": false
    }
  }
}
```

Authentication: OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Sign in with your pdfsamenvoegen.nl account.

With OAuth, Cline opens the sign-in page the first time a tool is used; approve access and return to Cline.

Check the connection by asking: "Merge my invoice, the quote and the terms into one PDF, quote first."
