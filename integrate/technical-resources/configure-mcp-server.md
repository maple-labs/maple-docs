# Configure MCP Server

Use the Maple Docs MCP server to access the full protocol & integration context in a simple and secure way. [MCP is an open protocol](https://modelcontextprotocol.io/specification/2025-03-26) that enables AI models to securely interact with local and remote resources through standardized server implementations.

## What does the Maple Docs MCP Server do?

It connects Maple Docs to tools like Cursor, Claude Code, and more. Access protocol and integration context and get your AI agents to help you with the syrupUSD integration.

Let us know how you and your agents use the Maple Docs MCP to power your workflows! If you have questions, feedback, reach out at [support@maple.finance](mailto:support@maple.finance)

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
      "description": "Onchain Asset Manager docs including syrupUSD integration and API references"
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
      "description": "Onchain Asset Manager docs including syrupUSD integration and API references"
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
      "description": "Onchain Asset Manager docs including syrupUSD integration and API references"
    }
  }
}
```
{% endcode %}
