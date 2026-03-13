# Execution Plan

## Links

- Spec: `/docs/spec/spec-driven-workflow-plan-archiving.md`

## Section 1 - Update the workflow path and archive location

- [x] Update `spec-driven-workflow` to use `/docs/plans/plan.md` as the active execution tracker
- [x] Update plan archiving to use `/docs/plans/plan.YYYYMMDD-HHMMSS.md`
- [x] Update related references, prompts, and companion skill mentions to use the new path

## Section 2 - Sync repository-facing documentation and verify

- [x] Update repository specs and summaries that describe the plan path
- [x] Validate the updated skill
- [x] Review the final diff for only the intended files

## Section 3 - Close out the current delivery unit

- [x] Archive `/docs/plans/plan.md` as `/docs/plans/plan.YYYYMMDD-HHMMSS.md` after the tracked work is complete
