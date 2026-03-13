# GitHub Copilot Bootstrap Skill Order

## Summary

Update the GitHub Copilot bootstrap instructions so generated `.github/copilot-instructions.md` files tell Copilot to start with `spec-driven-workflow` for non-trivial work, then add the other mirrored skills only when the task needs them.

## User Problem

The current bootstrap text describes the three skills, but it does not state strongly enough that `spec-driven-workflow` should be the first skill used by default before the architecture or Azure skills are added.

## Users and Scenarios

- Repository maintainers updating the shared bootstrap prompt for GitHub Copilot
- Developers using the bootstrap prompt to create `.github/copilot-instructions.md`
- GitHub Copilot sessions that need a clear default order for combining the three skills

## Scope

- Update the GitHub Copilot bootstrap section in `develop/skills/README.md`
- Make the generated `copilot-instructions` guidance explicitly start with `spec-driven-workflow`
- Keep the existing role boundaries for the architecture and Azure skills

## Non-Goals

- Changing the Codex bootstrap text
- Changing the Claude Code bootstrap text
- Changing the content of the three mirrored skills themselves

## User-Visible Behavior

- The GitHub Copilot bootstrap prompt now tells Copilot to use `spec-driven-workflow` first for non-trivial application-development work
- The prompt then tells Copilot to add `enforce-react-spa-architecture` for app-code architecture work and `azure-spa-clean-architecture-bootstrap` only for Azure-specific concerns
- The generated instruction order is clearer and more consistent with the intended workflow

## Acceptance Criteria

- `develop/skills/README.md` explicitly says `.github/copilot-instructions.md` should tell Copilot to start with `spec-driven-workflow` first
- The text still explains when to add `enforce-react-spa-architecture`
- The text still explains when to add `azure-spa-clean-architecture-bootstrap`
- The bootstrap prompt remains coherent and copy-pastable

## Edge Cases

- The wording should not imply that the Azure skill can be used without the architecture skill
- The wording should not restrict trivial maintenance tasks that do not need the full spec-first workflow

## Constraints and Dependencies

- Follow the repository's mirrored-skill terminology exactly
- Keep the change focused on GitHub Copilot bootstrap instructions
- Temporary execution tracking lives in `/docs/plan.md` while the work is active

## Links

- Plan: `/docs/plan.md`
