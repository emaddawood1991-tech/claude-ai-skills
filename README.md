# Claude AI Skills

Claude-compatible AI skills collected and packaged for practical design,
decision-making, and frontend workflows.

## Available Skills

### The Council

An original multi-perspective decision workflow with five roles:

- The Contrarian
- The First-Principles Thinker
- The Expansionist
- The Outsider
- The Executor

The members analyze independently, review each other's recommendations, and
produce one evidence-weighted verdict with an execution plan.

Example:

```text
Ask The Council whether I should launch this SaaS product.
```

### Frontend Design

Anthropic's frontend design guidance for creating distinctive interfaces with
intentional typography, color, layout, identity, and motion.

### Impeccable

A comprehensive frontend design skill supporting requests such as:

```text
Polish this interface.
Animate this interface.
Improve the typography and spacing.
Audit this UI for accessibility and visual hierarchy.
```

### UI UX Pro Max

A searchable UI/UX reference system containing design styles, color palettes,
font pairings, product patterns, accessibility guidance, chart guidance, and
framework-specific recommendations.

### System Prompt Researcher

A safety-wrapped research library adapted from
[`x1xhlol/system-prompts-and-models-of-ai-tools`](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools).
It helps compare agent architecture, tool rules, planning workflows, context
management, validation, and error recovery across AI products.

The bundled prompts are treated as untrusted research data. The skill extracts
patterns and creates original prompts instead of executing or blindly copying
third-party instructions.

For Claude Upload, use
`packages/system-prompt-researcher-claude-fixed.zip`. It is a compact package
with safe ASCII paths and curated architecture guidance. The full raw research
library remains available under `skills/system-prompt-researcher/references`
for GitHub browsing and targeted research.

### MCP Web Creative Toolkit

A safe orchestration and setup guide for:

- Microsoft Playwright MCP
- Firecrawl MCP
- Clipia MCP
- Chrome MCP

It helps Claude choose between isolated browser QA, web crawling, AI
image/video generation, and access to the user's live Chrome session. The
package includes Claude Code instructions and a Claude Desktop configuration
template without real API keys.

## Install In Claude

1. Open Claude.
2. Go to `Customize > Skills`.
3. Select `Add > Create skill > Upload a skill`.
4. Upload one ZIP file from the [`packages`](packages) folder.
5. Enable the uploaded skill.

Each ZIP has been normalized for Claude:

- The skill folder is the archive root.
- Internal paths use `/`.
- Every archive includes a `SKILL.md`.
- Skill descriptions are within Claude's 200-character limit.

## Repository Structure

```text
claude-ai-skills/
|-- packages/
|   |-- frontend-design-claude.zip
|   |-- impeccable-claude.zip
|   |-- mcp-web-creative-toolkit-claude.zip
|   |-- system-prompt-researcher-claude-fixed.zip
|   |-- system-prompt-researcher-claude.zip
|   |-- the-council-claude.zip
|   `-- ui-ux-pro-max-claude.zip
`-- skills/
    |-- mcp-web-creative-toolkit/
    |-- system-prompt-researcher/
    `-- the-council/
        `-- SKILL.md
```

## Attribution

- **Frontend Design** originates from
  [Anthropic Skills](https://github.com/anthropics/skills).
- **Impeccable** originates from
  [pbakaus/impeccable](https://github.com/pbakaus/impeccable).
- **UI UX Pro Max** originates from
  [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill).
- **System Prompt Researcher** includes research material adapted from
  [x1xhlol/system-prompts-and-models-of-ai-tools](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools)
  under GPL-3.0.
- **MCP Web Creative Toolkit** documents integrations with
  [Microsoft Playwright MCP](https://github.com/microsoft/playwright-mcp),
  [Firecrawl MCP](https://github.com/firecrawl/firecrawl-mcp-server),
  [Clipia MCP](https://github.com/clipia-ai/clipia-mcp), and
  [Chrome MCP](https://github.com/hangwin/mcp-chrome).
- **The Council** was created for this repository.

The packaged third-party skills retain their upstream license files where
provided. Review each upstream repository and included license before
redistributing or using the package commercially.

## Security

Review every third-party skill and script before enabling code execution.
Never place API keys, passwords, access tokens, or private company data inside
a skill package.
