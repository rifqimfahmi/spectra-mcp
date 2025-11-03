# 🎨 Spectra MCP Server

A powerful [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server for converting colors between different color spaces and formats. Built with FastMCP and powered by the coloraide library.

## 🌐 Hosted Deployment

**Spectra is now available as a hosted service!** No installation required - integrate directly with any MCP client that supports remote HTTP servers.

**Server URL:** `https://spectra-mcp.fastmcp.app/mcp`

Simply add the URL to your MCP client configuration and start using color conversion tools immediately.

## Overview

Spectra provides seamless color conversion capabilities through MCP tools, enabling AI assistants and applications to convert colors between various formats including RGB, HEX, HSL, and OKLCH color spaces. This server is ideal for design tools, theme generators, and any application requiring robust color manipulation.

### Why Spectra?

Large Language Models (LLMs) struggle with converting colors between different formats in a deterministic way. Even seemingly simple conversions like `#ff8080` to RGB or OKLCH to HEX can produce inconsistent or incorrect results when attempted through pure reasoning. Spectra solves this problem by providing reliable, deterministic color conversion tools that AI assistants can call, ensuring accurate and consistent color transformations every time.

## Features

- **🌐 Hosted Service**: Available remotely at `https://spectra-mcp.fastmcp.app/mcp` - no installation needed
- **Multiple Color Space Support**: Convert between RGB, HEX, HSL, and OKLCH color spaces
- **Bidirectional Conversions**: Convert colors in any direction between supported formats
- **High-Quality Conversions**: Powered by the coloraide library for accurate color science
- **MCP Protocol**: Standardized interface for integration with AI assistants and tools
- **HTTP Transport**: Supports remote HTTP MCP servers for seamless integration

## Supported Conversions

The following table shows all supported color format conversions:

| From \ To | RGB | HEX | HSL | OKLCH |
| --------- | --- | --- | --- | ----- |
| **RGB**   | —   | ✅  | ✅  | ✅    |
| **HEX**   | ✅  | —   | ✅  | ✅    |
| **HSL**   | ✅  | ✅  | —   | ✅    |
| **OKLCH** | ✅  | ✅  | ✅  | —     |

All conversions are bidirectional—you can convert between any two formats in either direction.

## 🛠️ Installation

### Requirements

- Cursor, Claude Code, VSCode, Windsurf or another MCP Client

<details>
<summary><b>Install in Cursor</b></summary>

Go to: `Settings` -> `Cursor Settings` -> `MCP` -> `Add new global MCP server`

Pasting the following configuration into your Cursor `~/.cursor/mcp.json` file is the recommended approach. You may also install in a specific project by creating `.cursor/mcp.json` in your project folder. See [Cursor MCP docs](https://docs.cursor.com/context/model-context-protocol) for more info.

> Since Cursor 1.0, you can click the install button at the top of this README for instant one-click installation.

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=spectra&config=eyJ1cmwiOiJodHRwczovL3NwZWN0cmEtbWNwLmZhc3RtY3AuYXBwL21jcCJ9)

```json
{
  "mcpServers": {
    "spectra": {
      "url": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in Claude Code</b></summary>

Run this command. See [Claude Code MCP docs](https://docs.anthropic.com/en/docs/claude-code/mcp) for more info.

```sh
claude mcp add --transport http spectra https://spectra-mcp.fastmcp.app/mcp
```

</details>

<details>
<summary><b>Install in Amp</b></summary>

Run this command in your terminal. See [Amp MCP docs](https://ampcode.com/manual#mcp) for more info.

```sh
amp mcp add spectra https://spectra-mcp.fastmcp.app/mcp
```

</details>

<details>
<summary><b>Install in Windsurf</b></summary>

Add this to your Windsurf MCP config file. See [Windsurf MCP docs](https://docs.windsurf.com/windsurf/cascade/mcp) for more info.

```json
{
  "mcpServers": {
    "spectra": {
      "serverUrl": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in VS Code</b></summary>

Add this to your VS Code MCP config file. See [VS Code MCP docs](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) for more info.

```json
"mcp": {
  "servers": {
    "spectra": {
      "type": "http",
      "url": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in Cline</b></summary>

You can easily install Spectra through the [Cline MCP Server Marketplace](https://cline.bot/mcp-marketplace) by following these instructions:

1. Open **Cline**.
2. Click the hamburger menu icon (☰) to enter the **MCP Servers** section.
3. Use the search bar within the **Marketplace** tab to find _Spectra_.
4. Click the **Install** button.

Or you can directly edit MCP servers configuration:

1. Open **Cline**.
2. Click the hamburger menu icon (☰) to enter the **MCP Servers** section.
3. Choose **Remote Servers** tab.
4. Click the **Edit Configuration** button.
5. Add spectra to `mcpServers`:

```json
{
  "mcpServers": {
    "spectra": {
      "url": "https://spectra-mcp.fastmcp.app/mcp",
      "type": "streamableHttp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in Zed</b></summary>

Add this to your Zed `settings.json`. See [Zed Context Server docs](https://zed.dev/docs/assistant/context-servers) for more info.

Note: Zed currently supports local MCP servers only. For remote server support, please check Zed's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Augment Code</b></summary>

Note: Augment Code currently supports local MCP servers only. For remote server support, please check Augment Code's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Roo Code</b></summary>

Add this to your Roo Code MCP configuration file. See [Roo Code MCP docs](https://docs.roocode.com/features/mcp/using-mcp-in-roo) for more info.

```json
{
  "mcpServers": {
    "spectra": {
      "type": "streamable-http",
      "url": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in Claude Desktop</b></summary>

Open Claude Desktop and navigate to Settings > Connectors > Add Custom Connector. Enter the name as `Spectra` and the remote MCP server URL as `https://spectra-mcp.fastmcp.app/mcp`.

</details>

<details>
<summary><b>Install in Opencode</b></summary>

Add this to your Opencode configuration file. See [Opencode MCP docs](https://opencode.ai/docs/mcp-servers) for more info.

```json
"mcp": {
  "spectra": {
    "type": "remote",
    "url": "https://spectra-mcp.fastmcp.app/mcp",
    "enabled": true
  }
}
```

</details>

<details>
<summary><b>Install in OpenAI Codex</b></summary>

See [OpenAI Codex](https://github.com/openai/codex) for more information.

Add the following configuration to your OpenAI Codex MCP server settings:

```toml
[mcp_servers.spectra]
url = "https://spectra-mcp.fastmcp.app/mcp"
```

</details>

<details>
<summary><b>Install in JetBrains AI Assistant</b></summary>

Note: JetBrains AI Assistant currently supports local MCP servers only. For remote server support, please check JetBrains' documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Kiro</b></summary>

Note: Kiro currently supports local MCP servers only. For remote server support, please check Kiro's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Trae</b></summary>

Use the Add manually feature and fill in the JSON configuration information for that MCP server.

For more details, visit the [Trae documentation](https://docs.trae.ai/ide/model-context-protocol?_lang=en).

```json
{
  "mcpServers": {
    "spectra": {
      "url": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in LM Studio</b></summary>

Note: LM Studio currently supports local MCP servers only. For remote server support, please check LM Studio's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Visual Studio 2022</b></summary>

You can configure Spectra MCP in Visual Studio 2022 by following the [Visual Studio MCP Servers documentation](https://learn.microsoft.com/visualstudio/ide/mcp-servers?view=vs-2022).

Add this to your Visual Studio MCP config file (see the [Visual Studio docs](https://learn.microsoft.com/visualstudio/ide/mcp-servers?view=vs-2022) for details):

```json
{
  "inputs": [],
  "servers": {
    "spectra": {
      "type": "http",
      "url": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

For more information and troubleshooting, refer to the [Visual Studio MCP Servers documentation](https://learn.microsoft.com/visualstudio/ide/mcp-servers?view=vs-2022).

</details>

<details>
<summary><b>Install in Crush</b></summary>

Add this to your Crush configuration file. See [Crush MCP docs](https://github.com/charmbracelet/crush#mcps) for more info.

```json
{
  "$schema": "https://charm.land/crush.json",
  "mcp": {
    "spectra": {
      "type": "http",
      "url": "https://spectra-mcp.fastmcp.app/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>Install in BoltAI</b></summary>

Note: BoltAI currently supports local MCP servers only. For remote server support, please check BoltAI's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Warp</b></summary>

Note: Warp currently supports local MCP servers only. For remote server support, please check Warp's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

<details>
<summary><b>Install in Perplexity Desktop</b></summary>

Note: Perplexity Desktop currently supports local MCP servers only. For remote server support, please check Perplexity's documentation for updates or use another MCP client that supports remote HTTP servers.

</details>

---

### 💻 Development Setup (For Contributors)

If you want to contribute to Spectra or run it locally:

#### Prerequisites

- Python 3.14 or higher
- [uv](https://github.com/astral-sh/uv) package manager (recommended)

#### Setup

1. Clone the repository:

```bash
git clone <repository-url>
cd spectra-mcp
```

2. Install dependencies using uv:

```bash
uv sync
```

3. Start the server:

```bash
uv run python main.py
```

The server will start on `http://127.0.0.1:8000` by default.

## API Reference

### Tools

#### `oklch_to_rgb`

Convert an OKLCH color to an RGB color.

**Parameters:**

- `oklch` (string): OKLCH color string (e.g., `"oklch(0.7 0.2 180)"`)

**Returns:**

- RGB color string (e.g., `"rgb(255, 128, 128)"`)

#### `rgb_to_oklch`

Convert an RGB color to an OKLCH color.

**Parameters:**

- `rgb` (string): RGB color string (e.g., `"rgb(255, 128, 128)"` or `"255, 128, 128"`)

**Returns:**

- OKLCH color string (e.g., `"oklch(0.7 0.2 180)"`)

#### `hex_to_rgb`

Convert a hex color to an RGB color.

**Parameters:**

- `hex` (string): Hex color string (e.g., `"#ff8080"` or `"ff8080"`)

**Returns:**

- RGB color string (e.g., `"rgb(255, 128, 128)"`)

#### `rgb_to_hex`

Convert an RGB color to a hex color.

**Parameters:**

- `rgb` (string): RGB color string (e.g., `"rgb(255, 128, 128)"` or `"255, 128, 128"`)

**Returns:**

- Hex color string (e.g., `"#ff8080"`)

#### `oklch_to_hex`

Convert an OKLCH color to a hex color.

**Parameters:**

- `oklch` (string): OKLCH color string (e.g., `"oklch(0.7 0.2 180)"`)

**Returns:**

- Hex color string (e.g., `"#ff8080"`)

#### `hex_to_oklch`

Convert a hex color to an OKLCH color.

**Parameters:**

- `hex` (string): Hex color string (e.g., `"#ff8080"` or `"ff8080"`)

**Returns:**

- OKLCH color string (e.g., `"oklch(0.7 0.2 180)"`)

#### `rgb_to_hsl`

Convert an RGB color to an HSL color.

**Parameters:**

- `rgb` (string): RGB color string (e.g., `"rgb(255, 128, 128)"` or `"255, 128, 128"`)

**Returns:**

- HSL color string (e.g., `"hsl(0 100% 75%)"`)

#### `hsl_to_rgb`

Convert an HSL color to an RGB color.

**Parameters:**

- `hsl` (string): HSL color string (e.g., `"hsl(0 100% 75%)"`)

**Returns:**

- RGB color string (e.g., `"rgb(255, 128, 128)"`)

#### `oklch_to_hsl`

Convert an OKLCH color to an HSL color.

**Parameters:**

- `oklch` (string): OKLCH color string (e.g., `"oklch(0.7 0.2 180)"`)

**Returns:**

- HSL color string (e.g., `"hsl(0 100% 75%)"`)

#### `hsl_to_oklch`

Convert an HSL color to an OKLCH color.

**Parameters:**

- `hsl` (string): HSL color string (e.g., `"hsl(0 100% 75%)"`)

**Returns:**

- OKLCH color string (e.g., `"oklch(0.7 0.2 180)"`)

#### `hex_to_hsl`

Convert a hex color to an HSL color.

**Parameters:**

- `hex` (string): Hex color string (e.g., `"#ff8080"` or `"ff8080"`)

**Returns:**

- HSL color string (e.g., `"hsl(0 100% 75%)"`)

#### `hsl_to_hex`

Convert an HSL color to a hex color.

**Parameters:**

- `hsl` (string): HSL color string (e.g., `"hsl(0 100% 75%)"`)

**Returns:**

- Hex color string (e.g., `"#ff8080"`)

## Examples

### Converting OKLCH to RGB

```
Input: oklch(0.7 0.2 180)
Output: rgb(255, 128, 128)
```

### Converting RGB to OKLCH

```
Input: rgb(255, 128, 128)
Output: oklch(0.7 0.2 180)
```

### Converting HEX to RGB

```
Input: #ff8080
Output: rgb(255, 128, 128)
```

### Converting RGB to HEX

```
Input: rgb(255, 128, 128)
Output: #ff8080
```

### Converting OKLCH to HEX

```
Input: oklch(0.7 0.2 180)
Output: #ff8080
```

### Converting HEX to OKLCH

```
Input: #ff8080
Output: oklch(0.7 0.2 180)
```

### Converting RGB to HSL

```
Input: rgb(255, 128, 128)
Output: hsl(0 100% 75%)
```

### Converting HSL to RGB

```
Input: hsl(0 100% 75%)
Output: rgb(255, 128, 128)
```

### Converting OKLCH to HSL

```
Input: oklch(0.7 0.2 180)
Output: hsl(0 100% 75%)
```

### Converting HSL to OKLCH

```
Input: hsl(0 100% 75%)
Output: oklch(0.7 0.2 180)
```

### Converting HEX to HSL

```
Input: #ff8080
Output: hsl(0 100% 75%)
```

### Converting HSL to HEX

```
Input: hsl(0 100% 75%)
Output: #ff8080
```

## Configuration

### Remote/Hosted Server

No configuration needed! The hosted service at `https://spectra-mcp.fastmcp.app/mcp` is ready to use.

### Local Development Server

For local development, server configuration can be modified in `fastmcp.json`:

- **Port**: Change the `port` value (default: 8000)
- **Host**: Change the `host` value (default: 127.0.0.1)
- **Log Level**: Adjust `log_level` (default: DEBUG)
- **Environment**: Modify environment variables as needed

## Dependencies

- [coloraide](https://github.com/Facelessuser/coloraide) (>=5.1): Advanced color manipulation library
- [fastmcp](https://github.com/jlowin/fastmcp) (>=2.13.0.2): Fast MCP server framework

## Acknowledgments

- Built with [FastMCP](https://github.com/jlowin/fastmcp)
- Color conversions powered by [coloraide](https://github.com/Facelessuser/coloraide)
