# skills/engineer/development

Skills for the `engineer` persona's `development` workstream.

## Hierarchy

- Persona: `engineer`
- Workstream: `development`
- Task group: `create-single-page-application`
- Skills:
  - `create-single-page-application/react-router-prisma-app-architecture`
  - `create-single-page-application/azure-app-platform-delivery`
  - `create-single-page-application/entra-user-auth-registration`
  - `create-single-page-application/copilot-azure-cloud-access`
- Related planning skill:
  - `skills/engineer/planning/spec-driven-workflow`

For the detailed responsibility split inside the SPA task group, read [create-single-page-application/README.md](/Users/hiroki/projects/hiroki/skills/engineer/development/create-single-page-application/README.md).

## Bootstrap

Bootstrap these skills when the repository needs the full React Router + Prisma + Azure stack plus spec-first planning.

### GitHub Copilot CLI

```text
Use GitHub's official /create-skill command to create these project skills under .github/skills/ for this repository:

- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/react-router-prisma-app-architecture
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/azure-app-platform-delivery
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/entra-user-auth-registration
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/copilot-azure-cloud-access
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/planning/spec-driven-workflow

Requirements:
- Use /create-skill for each skill instead of manually recreating the files.
- Create .github/skills/react-router-prisma-app-architecture/
- Create .github/skills/azure-app-platform-delivery/
- Create .github/skills/entra-user-auth-registration/
- Create .github/skills/copilot-azure-cloud-access/
- Create .github/skills/spec-driven-workflow/
- Use the repository source directories as the canonical content for each generated skill.
- Install react-router-prisma-app-architecture first.
- Install azure-app-platform-delivery next for Azure hosting, secretless config, IaC, Azure SQL, and GitHub release delivery.
- Install entra-user-auth-registration only when the app needs end-user Microsoft Entra ID auth or app-registration changes.
- Install copilot-azure-cloud-access only when the repository wants GitHub Copilot coding agent to access Azure from the cloud.
- Install spec-driven-workflow for non-trivial product work.
- Create or update .github/copilot-instructions.md.
- In .github/copilot-instructions.md, instruct Copilot to:
  - use spec-driven-workflow first for non-trivial application-development work
  - use react-router-prisma-app-architecture for app-code architecture, route boundaries, UI structure, and verification
  - use azure-app-platform-delivery for Azure hosting, Azure SQL, secretless config, IaC, and GitHub release delivery
  - add entra-user-auth-registration only when the task changes end-user auth contract or app registration
  - add copilot-azure-cloud-access only when the task changes the copilot Environment, Azure MCP, or Copilot OIDC access
- Preserve relative links between sibling skills.
- If destination folders already exist, replace or sync them to the repository version.
- When finished, list the installed files under .github/skills/ and show the final .github/copilot-instructions.md.
```

### Codex

```text
Use $skill-installer to install these skills into my personal Codex skills directory ($CODEX_HOME/skills or ~/.codex/skills) from this repository:

- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/react-router-prisma-app-architecture
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/azure-app-platform-delivery
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/entra-user-auth-registration
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/copilot-azure-cloud-access
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/planning/spec-driven-workflow

Requirements:
- Install react-router-prisma-app-architecture first.
- Install azure-app-platform-delivery next for Azure platform and release-delivery work.
- Install entra-user-auth-registration only when the app needs end-user auth or app-registration changes.
- Install copilot-azure-cloud-access only when GitHub Copilot coding agent needs Azure access.
- Install spec-driven-workflow for non-trivial work that should maintain /docs/spec and /docs/plans/plan.md.
- Use the full set deliberately:
  - spec-driven-workflow for spec-first planning
  - react-router-prisma-app-architecture for app-code architecture
  - azure-app-platform-delivery for Azure hosting, secretless config, SQL, IaC, and release delivery
  - entra-user-auth-registration for end-user Entra auth contract and app registration
  - copilot-azure-cloud-access for the copilot Environment, OIDC, Azure MCP, and least-privilege Azure read access
- Preserve the original folder names.
- Install from the GitHub repo paths rather than manually retyping the skill contents.
- If any destination skill already exists, stop and report that instead of overwriting it implicitly.
- When finished, list the installed paths, confirm the skills are available, summarize the above usage mapping, and remind me to restart Codex to pick up new skills.
```

### Claude Code

```text
Copy these skills into the current project's .claude/skills/ directory:

- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/react-router-prisma-app-architecture
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/azure-app-platform-delivery
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/entra-user-auth-registration
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/development/create-single-page-application/copilot-azure-cloud-access
- https://github.com/anaregdesign/hiroki/tree/main/skills/engineer/planning/spec-driven-workflow

Requirements:
- Create .claude/skills/react-router-prisma-app-architecture/
- Create .claude/skills/azure-app-platform-delivery/
- Create .claude/skills/entra-user-auth-registration/
- Create .claude/skills/copilot-azure-cloud-access/
- Create .claude/skills/spec-driven-workflow/
- Preserve every file and subdirectory exactly.
- Install react-router-prisma-app-architecture first, then azure-app-platform-delivery.
- Add entra-user-auth-registration only for end-user auth work.
- Add copilot-azure-cloud-access only for GitHub Copilot coding agent Azure access.
- Treat spec-driven-workflow as the independent planning skill.
- Create or update CLAUDE.md at the repository root.
- In CLAUDE.md, instruct Claude Code to use:
  - spec-driven-workflow for spec-first planning
  - react-router-prisma-app-architecture for app-code architecture, route boundaries, UI structure, and verification
  - azure-app-platform-delivery for Azure hosting, secretless config, SQL, IaC, and release delivery
  - entra-user-auth-registration only for end-user auth contract or app-registration changes
  - copilot-azure-cloud-access only for the copilot Environment, Azure MCP, or Copilot OIDC access
- When a task spans multiple concerns, use react-router-prisma-app-architecture as the base coding skill, add azure-app-platform-delivery for Azure platform or delivery concerns, add entra-user-auth-registration only for end-user auth, and add copilot-azure-cloud-access only for Copilot cloud-access work.
- If destination folders already exist, replace or sync them to the repository version.
- When finished, show the resulting .claude/skills/ tree and the final CLAUDE.md.
```

## Responsibility Summary

- `react-router-prisma-app-architecture`
  - Owns React Router + Prisma app-code architecture, route boundaries, UI structure, and verification.
- `azure-app-platform-delivery`
  - Owns Azure hosting, secretless config, Azure SQL, IaC, and GitHub release delivery.
  - This stays as one skill because the shared templates, bootstrap flow, and permission model cross-link too much to split cleanly.
- `entra-user-auth-registration`
  - Owns end-user Microsoft Entra ID auth contract and app registration flow.
- `copilot-azure-cloud-access`
  - Owns GitHub Copilot coding agent Azure access through the `copilot` Environment, OIDC, and Azure MCP.
- `spec-driven-workflow`
  - Owns spec-first planning and `/docs/spec` plus `/docs/plans/plan.md` maintenance.
