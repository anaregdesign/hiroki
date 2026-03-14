# AGENTS

## Mirror Rules

- This repository mirrors skills that are exposed from `$CODEX_HOME/skills`.
- The canonical repository hierarchy for mirrored skills is `skills/<persona>/<workstream>/<task>/<skill-name>/`.
- For skills that exist both in this repository and in Codex Home, place a symlink at `$CODEX_HOME/skills/<skill-name>` that points to the matching canonical directory under `skills/`.
- Do not keep duplicated copies for shared skills. The repository path is the canonical working tree, and the Codex Home path should resolve to it through the symlink.
- If a skill exists only in Codex Home, update it there directly until a repository mirror is created.
- Preserve directory structure, file names, and relative references when creating or refreshing shared skills and their symlinks.

## Skill Mapping

- In the current environment, `$CODEX_HOME` is unset. The active Codex Home skill directory is `/Users/hiroki/.codex/skills`.

| Repository skill | Repository path | Codex Home skill | Codex Home path | Link target | Status |
| --- | --- | --- | --- | --- | --- |
| `azure-app-platform-delivery` | `skills/engineer/development/create-single-page-application/azure-app-platform-delivery/SKILL.md` | `azure-app-platform-delivery` | `/Users/hiroki/.codex/skills/azure-app-platform-delivery` | `/Users/hiroki/projects/hiroki/skills/engineer/development/create-single-page-application/azure-app-platform-delivery` | `symlink` |
| `copilot-azure-cloud-access` | `skills/engineer/development/create-single-page-application/copilot-azure-cloud-access/SKILL.md` | `copilot-azure-cloud-access` | `/Users/hiroki/.codex/skills/copilot-azure-cloud-access` | `/Users/hiroki/projects/hiroki/skills/engineer/development/create-single-page-application/copilot-azure-cloud-access` | `symlink` |
| `entra-user-auth-registration` | `skills/engineer/development/create-single-page-application/entra-user-auth-registration/SKILL.md` | `entra-user-auth-registration` | `/Users/hiroki/.codex/skills/entra-user-auth-registration` | `/Users/hiroki/projects/hiroki/skills/engineer/development/create-single-page-application/entra-user-auth-registration` | `symlink` |
| `react-router-prisma-app-architecture` | `skills/engineer/development/create-single-page-application/react-router-prisma-app-architecture/SKILL.md` | `react-router-prisma-app-architecture` | `/Users/hiroki/.codex/skills/react-router-prisma-app-architecture` | `/Users/hiroki/projects/hiroki/skills/engineer/development/create-single-page-application/react-router-prisma-app-architecture` | `symlink` |
| `spec-driven-workflow` | `skills/engineer/planning/spec-driven-workflow/SKILL.md` | `spec-driven-workflow` | `/Users/hiroki/.codex/skills/spec-driven-workflow` | `/Users/hiroki/projects/hiroki/skills/engineer/planning/spec-driven-workflow` | `symlink` |

## Specification Rules

- The canonical spec document is `/docs/spec/specification.md`.
- Write `specification.md` in Japanese.
- `specification.md` must preserve the repository persona `hiroki`.
- Preserve directory structure and canonical paths explicitly, but avoid concrete personal references beyond what is needed to define the persona rule.
- Do not add or reference other spec files under `/docs/spec/`; consolidate spec content into `specification.md`.
