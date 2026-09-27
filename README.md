# opointo MCP server

**Design your app visually. Get a working native app.**

[opointo](https://opointo.com) is an App Builder: you design your app in the browser (screens,
blocks, navigation drawn as arrows, your theme), and your coding agent turns it into a real Expo
project you own. One codebase for iOS and Android, with Liquid Glass on iOS 26 and Material 3
Expressive on Android.

This MCP server is how the design reaches your agent. It lives at:

```
https://opointo.com/api/mcp
```

Streamable HTTP. This repository holds the server's public listing and setup instructions, not its
source.

## Tools

**Free, no account:** everything your agent needs to use the components correctly.

| Tool | What it does |
|---|---|
| `list_components` | The shipped components, and which render the real iOS system control |
| `get_component` | Props, types, defaults and value domains for one component |
| `find_component` | Ranked components for a UI need described in plain language |
| `get_rules` | The runtime rules: the mistakes that make a component render blank |
| `get_provider_tree` | The app-root provider nesting, in the order that works |
| `get_theme_tokens` | Theme hooks and the spacing, radius and typography scales |
| `check_snippet` | Finds blank-render bugs in TSX that uses these components |
| `get_step` | Expands one step of an app recipe |

**With a subscription:** the tools that write and verify your app.

| Tool | What it does |
|---|---|
| `emit_app` | Turns your opointo design into a working Expo app: navigation, providers, tab bar, screens |
| `emit_screen` | Turns one designed screen into a file for an app that already exists |
| `add_screen` | Adds a new screen to an exported app |
| `install_component` | Adds one component to an existing project |
| `update_components` | Updates the opointo-supplied files as iOS and Android move |
| `verify_app` | Checks the emitted app was applied correctly, before it is built |

Plans and the licence key: [opointo.com/pricing](https://opointo.com/pricing).

## Setup

Each snippet below adds the free tools. For the paid tools, add your licence key as a bearer token;
[opointo.com/mcp](https://opointo.com/mcp) has the exact variant for each agent.

**Claude Code**

```
claude mcp add --transport http --scope user opointo https://opointo.com/api/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{
  "mcpServers": {
    "opointo": { "url": "https://opointo.com/api/mcp" }
  }
}
```

**VS Code** (`.vscode/mcp.json`)

```json
{
  "servers": {
    "opointo": { "type": "http", "url": "https://opointo.com/api/mcp" }
  }
}
```

**Codex**

```
codex mcp add opointo --url https://opointo.com/api/mcp
```

**Gemini CLI**

```
gemini mcp add --scope user --transport http opointo https://opointo.com/api/mcp
```

## Requirements

Exported apps are Expo projects. Building them for iOS needs a Mac with Xcode 26; see
[opointo.com/compatibility](https://opointo.com/compatibility) for what is verified on which
platform.

## Links

- App Builder: [opointo.com](https://opointo.com)
- Docs: [opointo.com/docs](https://opointo.com/docs)
- Privacy: [opointo.com/privacy](https://opointo.com/privacy)
- Terms: [opointo.com/terms](https://opointo.com/terms)
- Contact: contact@opointo.com
