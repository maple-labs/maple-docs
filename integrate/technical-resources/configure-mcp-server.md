# Configure MCP Server

Use the Maple Docs MCP server to access the full protocol & integration context in a simple and secure way. [MCP is an open protocol](https://modelcontextprotocol.io/specification/2025-03-26) that enables AI models to securely interact with local and remote resources through standardized server implementations.

## What does the Maple Docs MCP Server do?

It connects Maple Docs to tools like Cursor, Claude Code, and any other MCP-enabled software, enabling your AI agents to help with the syrupUSD integration and protocol questions. If you have problems, questions or feedback, please reach out to us via the Intercom chat on the bottom right hand side of the screen.

## Setup Instructions

MCP Server URL: [https://docs.maple.finance/\~gitbook/mcp](https://docs.maple.finance/~gitbook/mcp)

### **Claude Code**

1\. Open your `~/.claude.json` config file\
2\. Add:

{% code overflow="wrap" %}
```json
{
  "mcpServers": {
    "maple-docs": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-gitbook",
        "https://docs.maple.finance"
      ],
      "env": {},
      "description": "Maple Finance documentation - Onchain Asset Manager docs including syrupUSD integration and API references"
    }
  }
}
```
{% endcode %}

### **Cursor**

1. Open (or create) `~/.cursor/mcp.json`
2. Add:

{% code overflow="wrap" %}
```json
{
  "mcpServers": {
    "maple-docs": {
      "command": "npx",
      "env": {},
      "args": [
        "-y",
        "@modelcontextprotocol/server-gitbook",
        "https://docs.maple.finance"
      ],
      "description": "Maple Finance documentation - Onchain Asset Manager docs including syrupUSD integration and API references"
    }
  }
}
```
{% endcode %}

## VS Code

1. Open (or create) `~/.vscode/mcp.json` on Mac/Linux or `%USERPROFILE%\.vscode\mcp.json` on Windows
2. Add:

{% code overflow="wrap" %}
```json
{
  "mcpServers": {
    "maple-docs": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-gitbook",
        "https://docs.maple.finance"
      ],
      "env": {},
      "description": "Maple Finance documentation - Onchain Asset Manager docs including syrupUSD integration and API references"
    }
  }
}
```
{% endcode %}
