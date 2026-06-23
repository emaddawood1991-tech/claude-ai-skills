# Setup Guide

This skill guides MCP usage but does not install MCP servers by being uploaded.
Configure the servers separately in Claude Code, Claude Desktop, or claude.ai.

## Requirements

- Node.js 20 or newer is recommended for the combined toolkit.
- Playwright MCP requires Node.js 18 or newer.
- Firecrawl requires a Firecrawl API key unless using a self-hosted endpoint.
- Clipia uses OAuth on claude.ai or an API key in local clients.
- Chrome MCP requires its Chrome extension and local bridge.

Never commit real keys. Replace placeholders locally or use environment
variables.

## Claude Code

### Playwright

```bash
claude mcp add playwright npx @playwright/mcp@latest
```

### Firecrawl

Set `FIRECRAWL_API_KEY` in the local environment, then add:

```bash
claude mcp add firecrawl -- npx -y firecrawl-mcp
```

If the client does not inherit the environment variable, configure the server
through Claude Code's MCP settings and pass `FIRECRAWL_API_KEY` there.

### Clipia

```bash
claude mcp add --transport http clipia https://mcp.clipia.ai/mcp \
  --header "Authorization: Bearer clipia_live_YOUR_KEY"
```

Use a `clipia_test_` key first when testing the integration.

### Chrome MCP

1. Download the extension from:
   `https://github.com/hangwin/mcp-chrome/releases`
2. Install the bridge:

```bash
npm install -g mcp-chrome-bridge
```

3. Load the unpacked extension in `chrome://extensions/`.
4. Start/connect the extension and use its displayed MCP endpoint, normally:

```text
http://127.0.0.1:12306/mcp
```

Add that Streamable HTTP URL through Claude Code's current MCP configuration.

## Claude Desktop

Merge `claude-desktop.example.json` into the existing
`claude_desktop_config.json`. Do not overwrite other configured servers.

Replace:

- `YOUR_FIRECRAWL_API_KEY`
- `clipia_test_YOUR_KEY` or `clipia_live_YOUR_KEY`

Restart Claude Desktop after changing the configuration.

Chrome MCP also requires the extension and bridge to be running. The config
file cannot install them.

## claude.ai

Clipia supports a direct custom connector:

1. Open `Settings > Connectors`.
2. Select `Add custom connector`.
3. Use `https://mcp.clipia.ai/mcp`.
4. Complete Clipia OAuth.

Local stdio servers such as Playwright and Firecrawl require a supported local
MCP host or Claude Desktop/Claude Code configuration. A Skill ZIP alone cannot
create those connections.

## Validation

Test one server at a time:

1. List tools or confirm connection status.
2. Run a read-only request.
3. Verify the returned source or visible browser state.
4. Test writes only in a safe environment.
5. Add the next server after the current one is stable.
