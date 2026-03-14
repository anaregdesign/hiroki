# create-single-page-application

Skill set for React Router + Prisma single-page applications that may also ship on Azure.

## Responsibility Split

### `react-router-prisma-app-architecture`

- Owns app-code architecture, dependency direction, route boundaries, UI guardrails, and verification.
- Use it for React Router routes, Prisma-backed app code, responsive UI, charts, and Playwright validation.

### `azure-app-platform-delivery`

- Owns Azure platform and delivery concerns that stay tightly coupled in practice:
  - Azure Container Apps
  - Azure SQL Database
  - App Configuration and Key Vault
  - workload identity and secretless config
  - `azure.yaml`, `Dockerfile`, Bicep, and shared runtime templates
  - GitHub `production` Environment, GitHub Actions OIDC, GHCR, release workflow design, and smoke tests
- This skill intentionally keeps hosting and release delivery together because the template assets, bootstrap flow, and permission model cross-link too much to split cleanly.

### `entra-user-auth-registration`

- Owns end-user `Microsoft Entra ID` auth contract and app registration work.
- Use it for `web` vs `spa` auth choice, callback URLs, local sign-in path, test users, and `az` or `az rest` app-registration changes.
- Add it only when the app actually needs end-user authentication.

### `copilot-azure-cloud-access`

- Owns GitHub Copilot coding agent cloud-side Azure access.
- Use it for the `copilot` Environment, OIDC or federated credentials, User Assigned Managed Identity, Azure MCP, and least-privilege Azure read scopes.
- Keep it separate from the production deploy identity.

### `spec-driven-workflow`

- Owns spec-first planning and execution tracking under `/docs/spec` and `/docs/plans/plan.md`.

## Boundary Notes

- `react-router-prisma-app-architecture` owns callback-route implementation and app-code placement, while `entra-user-auth-registration` owns the login contract, redirect URIs, and app-registration changes.
- `azure-app-platform-delivery` owns the production deploy identity and release workflow, while `copilot-azure-cloud-access` owns the separate Copilot cloud identity and Azure read access.

## Recommended Combinations

- App-code only:
  - `react-router-prisma-app-architecture`
- App-code plus Azure hosting and release:
  - `spec-driven-workflow`
  - `react-router-prisma-app-architecture`
  - `azure-app-platform-delivery`
- App-code plus Azure hosting and end-user auth:
  - `spec-driven-workflow`
  - `react-router-prisma-app-architecture`
  - `azure-app-platform-delivery`
  - `entra-user-auth-registration`
- GitHub Copilot coding agent Azure access:
  - `copilot-azure-cloud-access`
  - add `azure-app-platform-delivery` only when the same task also changes production hosting or release delivery

## Bootstrap Prompt

```text
Install this skill set, and when the work is non-trivial use it in the following order:

1. spec-driven-workflow for non-trivial work
2. react-router-prisma-app-architecture
3. azure-app-platform-delivery
4. entra-user-auth-registration only when the app needs end-user Microsoft Entra ID auth
5. copilot-azure-cloud-access only when GitHub Copilot coding agent needs Azure access from the cloud

Use the skills with these boundaries:
- react-router-prisma-app-architecture for app-code architecture, route boundaries, UI structure, and verification
- azure-app-platform-delivery for Azure hosting, secretless config, Azure SQL, IaC, and GitHub release delivery
- entra-user-auth-registration only for end-user auth contract and app-registration updates
- copilot-azure-cloud-access only for the copilot Environment, OIDC, Azure MCP, and least-privilege Azure read access
- spec-driven-workflow first whenever the work is non-trivial and should update /docs/spec or /docs/plans/plan.md
```
