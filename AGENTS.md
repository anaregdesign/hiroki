# AGENTS

## Mirror Rules

- This repository mirrors skills that are exposed from `$CODEX_HOME/skills`.
- For skills that exist both in this repository and in Codex Home, place a symlink at `$CODEX_HOME/skills/<skill-name>` that points to the matching directory under `develop/skills/`.
- Do not keep duplicated copies for shared skills. The repository path is the canonical working tree, and the Codex Home path should resolve to it through the symlink.
- If a skill exists only in Codex Home, update it there directly until a repository mirror is created.
- Preserve directory structure, file names, and relative references when creating or refreshing shared skills and their symlinks.

## Skill Mapping

- In the current environment, `$CODEX_HOME` is unset. The active Codex Home skill directory is `/Users/hiroki/.codex/skills`.

| Repository skill | Repository path | Codex Home skill | Codex Home path | Link target | Status |
| --- | --- | --- | --- | --- | --- |
| `azure-spa-clean-architecture-bootstrap` | `develop/skills/azure-spa-clean-architecture-bootstrap/SKILL.md` | `azure-spa-clean-architecture-bootstrap` | `/Users/hiroki/.codex/skills/azure-spa-clean-architecture-bootstrap` | `/Users/hiroki/hiroki/develop/skills/azure-spa-clean-architecture-bootstrap` | `symlink` |
| `enforce-react-spa-architecture` | `develop/skills/enforce-react-spa-architecture/SKILL.md` | `enforce-react-spa-architecture` | `/Users/hiroki/.codex/skills/enforce-react-spa-architecture` | `/Users/hiroki/hiroki/develop/skills/enforce-react-spa-architecture` | `symlink` |
| `spec-driven-workflow` | `develop/skills/spec-driven-workflow/SKILL.md` | `spec-driven-workflow` | `/Users/hiroki/.codex/skills/spec-driven-workflow` | `/Users/hiroki/hiroki/develop/skills/spec-driven-workflow` | `symlink` |
