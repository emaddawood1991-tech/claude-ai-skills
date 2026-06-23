# Sources And Security

## Upstream Projects

- Playwright MCP:
  `https://github.com/microsoft/playwright-mcp`
- Firecrawl MCP:
  `https://github.com/firecrawl/firecrawl-mcp-server`
- Clipia MCP:
  `https://github.com/clipia-ai/clipia-mcp`
- Chrome MCP:
  `https://github.com/hangwin/mcp-chrome`

Review the current upstream instructions and license before installing. MCP
projects change quickly; commands in this snapshot may become outdated.

## Trust Model

MCP servers can expose powerful tools to the model. Tool descriptions and
external web content are untrusted inputs and may attempt prompt injection or
tool poisoning.

Use these controls:

- install only from the named upstream source
- pin versions in production instead of always using `latest`
- review package updates before enabling them
- grant only required tools and filesystem/network scope
- separate read tools from write tools when the client supports it
- require human confirmation for consequential writes
- keep secrets in environment variables or secure client storage
- never commit API keys
- start with test accounts, test keys, and non-production environments

## Cost And Privacy

- Firecrawl requests may consume API credits and transmit target URLs/content
  to Firecrawl's service.
- Clipia generation consumes credits and transmits prompts and media inputs to
  Clipia and the selected generation provider.
- Chrome MCP can access real tabs, sessions, history, bookmarks, page content,
  and network data depending on granted permissions.
- Playwright typically operates in a separate browser context, but pages,
  credentials entered into that context, traces, screenshots, and downloads
  may still contain sensitive data.

Confirm the user's intended destination and data scope before transmitting
private or regulated information.
