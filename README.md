
# MCP Guardian 🔒

> The security and governance layer for Model Context Protocol (MCP) ecosystems.

## The Problem

When enterprises deploy multiple AI agents using diverse MCP servers, they lose control of:
- **What data is exposed** to external tools
- **Who has permissions** (RBAC) to invoke which tools
- **How much each query costs** and who is responsible
- **Whether sensitive data** (PII) is leaking through tool calls

## The Solution

MCP Guardian is an intermediate gateway that sits between AI clients and MCP servers. It provides:

| Feature | Status |
|---------|--------|
| Schema validation & tool poisoning protection | 🚧 MVP |
| OAuth 2.0 + OBO token exchange | 🚧 MVP |
| Rate limiting & quota management | 🚧 MVP |
| Audit logging (who, what, when) | 🚧 MVP |
| PII redaction | 📅 Roadmap |
| Multi-agent orchestration | 📅 Roadmap |
| Human-in-the-loop approval | 📅 Roadmap |

## Quick Start

```bash
# Coming soon
npm install -g @mcpguardian/gateway
mcp-guardian --config mcp-guardian.yaml
