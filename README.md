# VoriOS MCP for Cursor

Connect Cursor to your grocery store's operations through the hosted Vori MCP server.

## What it does

Use natural language to search products, analyze sales and inventory, review invoices, and work with pricing, promotions, and ordering. Available tools and actions depend on your Vori account's permissions.

This repository packages the Cursor plugin configuration. The MCP service runs at [mcp.vori.com](https://mcp.vori.com); its server implementation is not included here.

## Connect

You need a Vori account with access to your store or banner.

Install the plugin through Cursor when its marketplace listing is available, enable the Vori MCP server, and sign in with your existing Vori credentials when prompted. No API key is required.

You can also connect directly before marketplace approval. Add this configuration to `~/.cursor/mcp.json` (user scope) or `.cursor/mcp.json` in your project:

```json
{
  "mcpServers": {
    "vori": {
      "type": "http",
      "url": "https://mcp.vori.com"
    }
  }
}
```

Restart Cursor if tools do not appear, then complete sign-in.

## Example requests

- Find products by name or barcode.
- Summarize sales and margin for my store over the last week.
- Show products that are out of stock.
- List invoices waiting for cost-change review.
- Preview the changes from selected invoice lines before applying them.

## Permissions and data

Authentication and role-based permissions scope tool access to the stores and actions your account is authorized to use. Some tools can change store data. Review proposed changes and previews before applying them. For a read-only connection, use an account with Vori's Read-only role.

The MCP service is in alpha; tool coverage may change. See the [Vori MCP documentation](https://help.vori.com/mcp/introduction) for current capabilities, troubleshooting, and data handling, and the [Vori privacy policy](https://www.vori.com/privacy).

## Plugin layout

- `.cursor-plugin/plugin.json`: Cursor plugin metadata.
- `mcp.json`: hosted HTTP MCP connection.

This package requires no build step or local server.

## Support

Use your normal Vori support channel or visit the [Vori Help Center](https://help.vori.com).
