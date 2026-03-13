# Repository Documentation Foundation

## Summary

Define this repository as the canonical documentation hub for hiroki's characteristics, technical strengths, technologies, and reusable skills. Establish the initial scope, audience, information domains, and acceptance criteria for documenting that knowledge in a structured way.

## User Problem

The repository already contains skills and related materials, but the overall documentation goal is still abstract. Without a repository-level specification, it is hard to judge what knowledge should be documented, how complete the documentation should become, and how future documents should be organized.

## Users and Scenarios

- hiroki, who wants a repository that reflects his characteristics, technical strengths, technologies, and skills in a durable and reviewable form
- collaborators who need to understand what hiroki knows, what he has standardized, and where to find the relevant documentation
- AI agents or tooling that need a reliable repository-level source of truth for hiroki's documented capabilities and guidance

## Scope

- Define the repository's role as a documentation hub
- Define the primary documentation domains the repository should eventually cover
- Define the expected structure and discoverability of those documents at a high level
- Define what "sufficiently documented" means for future repository growth
- Provide a foundation that later specs can refine into domain-specific documents

## Non-Goals

- Writing every detailed document for every technology or skill in this request
- Freezing the final folder layout for every future document before the domains are refined
- Replacing the source skill files themselves with only summary documentation
- Deciding unrelated application architecture or cloud deployment behavior

## User-Visible Behavior

- The repository has a durable specification that states its documentation mission clearly
- Future documentation work can be evaluated against explicit domains instead of an informal idea
- Reviewers can tell whether a new document belongs in the repository and whether an important domain is still missing
- The repository can expand from a high-level foundation into more detailed specifications and content without losing coherence

## Acceptance Criteria

- The repository-level spec states that the repository aims to document hiroki's characteristics, technologies, and skills comprehensively over time
- The spec identifies the main audiences and why they use the repository
- The spec defines the major knowledge domains that future documents should cover
- The spec defines repository-level expectations for structure, discoverability, and maintenance
- The spec is written at a level that allows later detailed specs to branch from it without rewriting the mission

## Edge Cases

- Some knowledge may overlap across domains, such as a skill that also represents a technology preference or working style
- Some areas may remain intentionally incomplete for a time, so the documentation system must support phased expansion
- New technologies or skills may appear later, so the repository must support adding new documentation domains without invalidating earlier documents
- Certain knowledge may live partly in source skill files and partly in higher-level summary documents, so the repository should describe the relationship between canonical source files and overview documents clearly

## Constraints and Dependencies

- The repository should treat actual skill content and mirrored source material as authoritative where they already exist
- High-level documentation should summarize and organize the knowledge without drifting away from the underlying source files
- Future documents should prefer stable terminology already used in the repository's skills and instructions
- This initial spec is intentionally high level and should serve as a foundation for later, narrower specs

## Documentation Domains

- Characteristics and working style:
  Document hiroki's recurring preferences, decision-making patterns, communication expectations, and standards that affect how work should be performed.
- Technical strengths and technology areas:
  Document the technologies, platforms, frameworks, and problem areas that hiroki actively uses or standardizes.
- Skills and reusable workflows:
  Document each reusable skill, what it is for, when to use it, what it depends on, and how it relates to other skills.
- Repository conventions and source-of-truth rules:
  Document how mirrored files, source files, generated guidance, and maintenance workflows relate to each other.
- Navigation and discovery:
  Document how a person or agent should find the right document, skill, or reference quickly.

## Structure Expectations

- The repository should keep durable documentation under `docs/` with clear separation between high-level specification, temporary execution tracking, and source skill content.
- Repository-level overview documents should point to narrower domain documents rather than trying to hold every detail in one file.
- Documentation should make the relationship between overview documents, skill files, references, and mirrored sources explicit.
- The repository should support incremental expansion: it must be possible to add one domain at a time without restructuring everything.

## Maintenance Expectations

- When a skill, technology preference, or repository rule changes materially, the relevant documentation should be updated so the repository remains trustworthy.
- Documentation should prefer a small number of clear canonical documents over duplicated summaries spread across many files.
- High-level overview documents should be kept aligned with the detailed documents and source files they summarize.

## Links

- Temporary execution tracking for this delivery unit lives in `/docs/plans/plan.md` while the work is active.
