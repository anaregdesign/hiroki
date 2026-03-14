---
name: azure-spa-entra-auth
description: "Own Microsoft Entra ID end-user auth contracts and app registration guidance for React Router + Prisma v7 web apps that already follow enforce-react-spa-architecture. Use when the work is primarily `web` vs `spa` auth choice, redirect URIs, cookie vs PKCE boundary, local sign-in path, test users, or Azure CLI or `az rest` app-registration updates. Do not use this skill for general Azure hosting topology, GitHub release delivery, or GitHub Copilot coding agent cloud access."
---

# Azure Spa Entra Auth

## Overview

Use this skill when the app needs end-user authentication.
This skill owns:

- `web` vs `spa` auth contract decisions
- redirect URI and callback URL design
- local sign-in path, dev or test registration hygiene, and test identities
- Azure CLI or `az rest` based app-registration changes for this app

This skill does not own Azure hosting topology, secretless runtime config, or GitHub release delivery. Combine it with [`../azure-spa-clean-architecture-bootstrap/SKILL.md`](../azure-spa-clean-architecture-bootstrap/SKILL.md) when auth work also changes hosted runtime or deployment setup.

## Companion Skill Requirement

- Install `enforce-react-spa-architecture` together with this skill.
- Add [`../azure-spa-clean-architecture-bootstrap/SKILL.md`](../azure-spa-clean-architecture-bootstrap/SKILL.md) when auth changes also affect Azure hosting, runtime identity, or release flow.

## Quick Start

1. Confirm the app actually needs end-user authentication.
2. Decide whether the runtime contract should be `web` or `spa`.
3. Read:
   - auth runtime contract guidance: [`references/entra-user-auth-and-runtime-contracts.md`](references/entra-user-auth-and-runtime-contracts.md)
   - reproducible app-registration flow: [`references/entra-app-registration-cli.md`](references/entra-app-registration-cli.md)
4. Keep redirect URIs, audience, tenant assumptions, and local sign-in expectations documented in checked-in notes.

## Use This Skill For

- `Microsoft Entra ID` login requirements in app features
- redirect URI changes and callback path design
- cookie-session vs browser PKCE decisions
- local sign-in with dev or test tenants, users, or groups
- `az` or `az rest` app registration updates

## Non-Negotiable Rules

- Treat requests for "Microsoft auth" as `Microsoft Entra ID` only when the app actually needs user auth.
- Prefer `web` redirect URIs and server-owned cookie sessions when the app already has a React Router server runtime.
- Use `spa` redirect URIs only for true browser-only PKCE flows.
- Prefer scripted `az` or `az rest` changes over portal-only edits.
- Do not use this skill for GitHub release delivery or GitHub Copilot coding agent Azure access.

## References

- base architecture skill: [`../enforce-react-spa-architecture/SKILL.md`](../enforce-react-spa-architecture/SKILL.md)
- Azure platform and delivery sibling: [`../azure-spa-clean-architecture-bootstrap/SKILL.md`](../azure-spa-clean-architecture-bootstrap/SKILL.md)
- auth runtime contracts: [`references/entra-user-auth-and-runtime-contracts.md`](references/entra-user-auth-and-runtime-contracts.md)
- Azure CLI app-registration flow: [`references/entra-app-registration-cli.md`](references/entra-app-registration-cli.md)
