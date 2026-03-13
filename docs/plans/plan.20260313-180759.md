# Execution Plan

## Links

- Spec: `/docs/spec/spec-driven-workflow-plan-archiving.md`

## Section 1 - Update the source skill

- [x] Update `spec-driven-workflow/SKILL.md` to archive completed plans instead of deleting them
- [x] Update the skill references and `agents/openai.yaml` to match the new archive behavior

## Section 2 - Sync repository-facing documentation and verify

- [x] Update repository documentation that summarizes the skill's plan lifecycle
- [x] Validate the updated skill
- [x] Review the final diff for only the intended files

## Section 3 - Close out the current delivery unit

- [x] Archive `/docs/plans/plan.md` as `/docs/plans/plan.YYYYMMDD-HHMMSS.md` after the tracked work is complete
