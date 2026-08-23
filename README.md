# MCP Guardian 🔒

&gt; The security and governance layer for Model Context Protocol (MCP) ecosystems.

## The Problem

When enterprises deploy multiple AI agents using diverse MCP servers, they lose control of:
- **What data is exposed** to external tools
- **Who has permissions** (RBAC) to invoke which tools
- **How much each query costs** and who is responsible
- **Whether sensitive data** (PII) is leaking through tool calls

## The Solution

MCP Guardian is an intermediate gateway that sits between AI clients and MCP servers.

## Why MCP Guardian vs. Alternatives

| Competitor | Their Focus | Why We Win |
|---|---|---|
| **LLM Gateways** (Portkey, Helicone) | Monitor tokens & models | We monitor **tool calls and data payloads** |
| **API Gateways** (Kong, Apigee) | REST API management | We understand **MCP tool schemas & agent lifecycle** |
| **Closed Ecosystems** (Copilot Studio) | Lock-in to their stack | We are **multi-agent, multi-model, multi-server** |

## Features

| Feature | Status |
|---------|--------|
| Schema validation & tool poisoning protection | 🚧 MVP |
| OAuth 2.0 + OBO token exchange | 🚧 MVP |
| Rate limiting & quota management | 🚧 MVP |
| Audit logging (who, what, when) | 🚧 MVP |
| **Human-in-the-loop approval** | 🚧 **MVP (Critical Operations)** |
| PII redaction (context-aware) | 📅 Roadmap |
| Multi-agent orchestration | 📅 Roadmap |
| Blast radius visualization | 📅 Roadmap |

## ⚡ Ultra-Low Latency
Target overhead: **&lt; 10ms per tool call**.

## 🔌 Dual Transport Support

```bash
# Local mode (stdio interception)
mcp-guardian local --server ./mcp-server --config guardian.yaml
🛑 Human-in-the-Loop (HITL)
When an agent tries to modify production data, MCP Guardian pauses the request and sends an approval notification. The operation only proceeds after human confirmation.
🎯 Blast Radius Visualization
See exactly which tables, repositories, or SharePoint lists each agent can access.
🛡️ Context-Aware PII Redaction
Mask sensitive data intelligently. Example: mask credit cards but keep last 4 digits for payment confirmation.
Architecture
AI Client (Claude, GPT, etc.)
    ↓
[MCP Guardian Gateway]
    ↓
MCP Server (GitHub, Slack, PostgreSQL, etc.)

Quick Start

# Coming soon
npm install -g @mcpguardian/gateway
mcp-guardian --config mcp-guardian.yaml

Roadmap
[ ] Q3 2026: Security Gateway MVP (schema validation, OAuth, rate limiting, audit logging, HITL)
[ ] Q4 2026: Governance Platform (RBAC, policies, blast radius visualization)
[ ] Q1 2027: Enterprise Marketplace & Monetization
Contributing
We welcome contributions! See CONTRIBUTING.md.
License
MIT


---

## ✅ Tu Única Tarea Ahora

- [ ] Editar README.md en GitHub
- [ ] Pegar el texto de arriba
- [ ] Hacer commit
- [ ] **Responderme**: "Listo, README actualizado"

**No avanzo más hasta que me confirmes esto.** Cuando lo hagas, hablamos del siguiente paso.

# Remote mode (SSE/HTTP proxy)
mcp-guardian remote --port 8080 --config guardian.yaml
