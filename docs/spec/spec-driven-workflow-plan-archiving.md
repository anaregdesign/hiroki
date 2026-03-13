# Spec Driven Workflow Plan Storage And Archiving

## Summary

Update the `spec-driven-workflow` skill so active plans live at `/docs/plans/plan.md` and completed plans are archived as `/docs/plans/plan.YYYYMMDD-HHMMSS.md` instead of being deleted.

## User Problem

The current skill uses the root `docs/` directory for plan storage. That mixes active execution tracking with higher-level documents and makes it harder to keep active and archived plans together under one predictable hierarchy.

## Users and Scenarios

- Repository maintainers updating the shared `spec-driven-workflow` skill
- AI agents that use `spec-driven-workflow` to manage execution
- Collaborators who want to inspect completed execution plans after the current delivery unit is closed

## Scope

- Update the `spec-driven-workflow` skill instructions to archive completed plans
- Update the skill references so completion behavior matches the new archiving rule
- Update the skill's `agents/openai.yaml` metadata so the UI prompt matches the new behavior
- Update repository-level documentation that summarizes the skill's plan lifecycle

## Non-Goals

- Changing how specs under `/docs/spec/` are written
- Changing the hierarchy format inside the plan file itself
- Introducing a plan location outside `docs/plans/`
- Changing unrelated skills or repository workflows

## User-Visible Behavior

- The active execution tracker lives at `/docs/plans/plan.md` while work is in progress
- When tracked work completes, the plan is archived as `/docs/plans/plan.YYYYMMDD-HHMMSS.md`
- Future work starts from a fresh `/docs/plans/plan.md` rather than reusing a completed archived plan
- Documentation and prompts that describe the skill all reflect the archive behavior consistently

## Acceptance Criteria

- `spec-driven-workflow/SKILL.md` says active plans live at `/docs/plans/plan.md`
- `spec-driven-workflow/SKILL.md` says completed plans are archived as `/docs/plans/plan.YYYYMMDD-HHMMSS.md`
- `plan-documentation.md` and `plan-execution-workflow.md` describe archiving rather than deletion
- `agents/openai.yaml` no longer says the completed plan is deleted
- The repository documentation that summarizes `spec-driven-workflow` no longer says completed plans are deleted
- The archive naming rule uses the filesystem-safe sortable timestamp format `YYYYMMDD-HHMMSS`

## Edge Cases

- The active `/docs/plans/plan.md` should still remain temporary and should not become a long-lived combined history file
- Archived plans should preserve past execution state without blocking the creation of a new active `/docs/plans/plan.md`
- Future documents may need to reference both a durable spec and one or more archived plans for completed delivery units

## Constraints and Dependencies

- Update the source skill at `~/.codex/skills/spec-driven-workflow` first; the repository copy is a symlinked mirror
- Keep the skill body concise and consistent with the existing terminology
- Preserve the distinction between durable specs and temporary active execution tracking
- Use a filesystem-safe timestamp pattern such as `YYYYMMDD-HHMMSS`

## Links

- Active execution tracking for this change lives in `/docs/plans/plan.md` while the work is in progress.
