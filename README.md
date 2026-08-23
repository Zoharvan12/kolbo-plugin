# Kolbo.AI for Cursor

Create and edit images, video, music, speech, sound and 3D from inside your agent —
100+ creative models, consistent characters via Visual DNA, everything synced to your
Kolbo projects and media library.

## Install

From the Cursor marketplace:

```
/add-plugin kolbo
```

Or browse to [cursor.com/marketplace/kolbo](https://cursor.com/marketplace/kolbo).

The same plugin is available in Grok Bot, which reads the same catalog.

## What you get

| Component | |
|---|---|
| **Skills** | `generate-image`, `generate-video`, `generate-audio` |
| **Command** | `/kolbo` — run Kolbo workflows in natural language |
| **MCP** | `kolbo` → `https://api.kolbo.ai/mcp` |

## Authentication

The MCP server uses OAuth. The first tool call opens a browser sign-in to your
Kolbo account; nothing is stored in this repo and no API key is required.

A Kolbo.AI account is required. Generation spends credits.

## Manual setup

If you would rather wire it up by hand, add this to your MCP config:

```json
{
  "mcpServers": {
    "kolbo": {
      "type": "http",
      "url": "https://api.kolbo.ai/mcp"
    }
  }
}
```

## Links

- [Kolbo MCP](https://kolbo.ai/kolbo-mcp)
- [Documentation](https://docs.kolbo.ai/developer-api)
- [Privacy policy](https://kolbo.ai/privacy-policy) · [Terms of service](https://kolbo.ai/terms-of-service)
- Support: support@kolbo.ai
