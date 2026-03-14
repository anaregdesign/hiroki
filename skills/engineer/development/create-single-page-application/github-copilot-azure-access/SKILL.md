---
name: github-copilot-azure-access
description: "Own GitHub Copilot coding agent cloud-side Azure access through the `copilot` Environment, OIDC, Azure MCP integration, and least-privilege Azure role design. Use when the work is primarily `copilot-setup-steps.yml`, `azd coding-agent config`, federated credentials, User Assigned Managed Identity, Azure MCP, or Azure read access for GitHub Copilot coding agent. Do not use this skill for production release delivery or app runtime hosting."
---

# GitHub Copilot Azure Access

## Overview

Use this skill when GitHub Copilot coding agent needs Azure access from the cloud.
This skill owns:

- the GitHub `copilot` Environment
- OIDC subject design for Copilot coding agent
- User Assigned Managed Identity or equivalent least-privilege identity for Copilot
- Azure MCP and `azd coding-agent config`
- read-scoped Azure role design for cloud-side development tasks

This skill does not own production deploy workflows or app hosting topology. Keep the Copilot identity separate from the production deploy identity.

## Quick Start

1. Create or review the GitHub `copilot` Environment.
2. Prefer `azd coding-agent config` for the bootstrap path.
3. Keep the Azure role scope read-only by default, usually `Reader` on the target resource group.
4. Read:
   - Copilot Azure access guidance: [`references/github-copilot-coding-agent-azure-access.md`](references/github-copilot-coding-agent-azure-access.md)
5. Start from:
   - `assets/templates/.github/workflows/copilot-setup-steps.yml`

## Use This Skill For

- GitHub Copilot coding agent OIDC setup
- `copilot` Environment variables and federated credential design
- Azure MCP Server integration
- `azd coding-agent config`
- read-only Azure access for `az` and Azure resource inspection

## Non-Negotiable Rules

- Do not reuse the production deploy identity for GitHub Copilot coding agent.
- Keep Copilot cloud access read-mostly by default.
- Do not grant production Key Vault or App Configuration data-plane reads by default.
- Do not use this skill for production release delivery; use [`../azure-spa-clean-architecture-bootstrap/SKILL.md`](../azure-spa-clean-architecture-bootstrap/SKILL.md) instead.

## References

- Copilot Azure access guidance: [`references/github-copilot-coding-agent-azure-access.md`](references/github-copilot-coding-agent-azure-access.md)
- production delivery sibling: [`../azure-spa-clean-architecture-bootstrap/SKILL.md`](../azure-spa-clean-architecture-bootstrap/SKILL.md)
