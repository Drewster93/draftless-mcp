# Installing the Draftless MCP server (for AI agents)

Draftless is a **remote** MCP server. Do not clone, build or run anything.

1. Add this server to the MCP settings of the client:
   ```json
   { "mcpServers": { "draftless": { "url": "https://mcp.draftless.dev/mcp" } } }
   ```
   If the client cannot connect to remote Streamable HTTP servers with OAuth, use the `mcp-remote` bridge instead:
   ```json
   { "mcpServers": { "draftless": { "command": "npx", "args": ["-y", "mcp-remote", "https://mcp.draftless.dev/mcp"] } } }
   ```
2. On first connect the client opens a browser sign-in (OAuth). Ask the user to sign in or create a free Draftless account at https://draftless.dev.
3. Verify: call `discover` with `{ "action": "list_capabilities" }`. It should return node types and models.
4. Before any paid generation, call the action without `confirm` to get the price preview and show it to the user. Only confirm after the user approves.
