# create-single-page-application

Skill set for React Router + Prisma single-page applications that may also ship on Azure.

## Responsibility Split

### `enforce-react-spa-architecture`

- Owns app-code architecture, dependency direction, module placement, UI guardrails, and verification.
- Use it for React Router routes, Prisma-backed app code, responsive UI, charts, and Playwright validation.

### `azure-spa-clean-architecture-bootstrap`

- Owns Azure platform and delivery concerns that stay tightly coupled in practice:
  - Azure Container Apps
  - Azure SQL Database
  - App Configuration and Key Vault
  - workload identity and secretless config
  - `azure.yaml`, `Dockerfile`, Bicep, and shared runtime templates
  - GitHub `production` Environment, GitHub Actions OIDC, GHCR, release workflow design, and smoke tests
- This skill intentionally keeps hosting and release delivery together because the template assets, bootstrap flow, and permission model cross-link too much to split cleanly.

### `azure-spa-entra-auth`

- Owns end-user `Microsoft Entra ID` auth contract and app registration work.
- Use it for `web` vs `spa` auth choice, callback URLs, local sign-in path, test users, and `az` or `az rest` app-registration changes.
- Add it only when the app actually needs end-user authentication.

### `github-copilot-azure-access`

- Owns GitHub Copilot coding agent cloud-side Azure access.
- Use it for the `copilot` Environment, OIDC or federated credentials, User Assigned Managed Identity, Azure MCP, and least-privilege Azure read scopes.
- Keep it separate from the production deploy identity.

### `spec-driven-workflow`

- Owns spec-first planning and execution tracking under `/docs/spec` and `/docs/plans/plan.md`.

## Recommended Combinations

- App-code only:
  - `enforce-react-spa-architecture`
- App-code plus Azure hosting and release:
  - `spec-driven-workflow`
  - `enforce-react-spa-architecture`
  - `azure-spa-clean-architecture-bootstrap`
- App-code plus Azure hosting and end-user auth:
  - `spec-driven-workflow`
  - `enforce-react-spa-architecture`
  - `azure-spa-clean-architecture-bootstrap`
  - `azure-spa-entra-auth`
- GitHub Copilot coding agent Azure access:
  - `github-copilot-azure-access`
  - add `azure-spa-clean-architecture-bootstrap` only when the same task also changes production hosting or release delivery

## Bootstrap Prompt

```text
Install this skill set, and when the work is non-trivial use it in the following order:

1. spec-driven-workflow for non-trivial work
2. enforce-react-spa-architecture
3. azure-spa-clean-architecture-bootstrap
4. azure-spa-entra-auth only when the app needs end-user Microsoft Entra ID auth
5. github-copilot-azure-access only when GitHub Copilot coding agent needs Azure access from the cloud

Use the skills with these boundaries:
- enforce-react-spa-architecture for app-code architecture, UI boundaries, and verification
- azure-spa-clean-architecture-bootstrap for Azure hosting, secretless config, Azure SQL, IaC, and GitHub release delivery
- azure-spa-entra-auth only for end-user auth contract and app-registration updates
- github-copilot-azure-access only for the copilot Environment, OIDC, Azure MCP, and least-privilege Azure read access
- spec-driven-workflow first whenever the work is non-trivial and should update /docs/spec or /docs/plans/plan.md
```
