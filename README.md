# AI Builder Lessons

Project-agnostic lessons learned from building software with AI agents. Intended as a reusable reference and evolving decision tree for future AI-assisted projects.

## Structure

Lessons are organized in the `lessons/` directory, numbered sequentially:

```
lessons/
  001-title.md
  002-title.md
```

Each lesson follows a consistent template (see below) to enable future aggregation into a decision tree.

## Lesson Template

```markdown
# Lesson NNN — Title

**Category:** [repo-structure | process | ai-collaboration | architecture | tooling]
**Source project:** (optional) The project where this was discovered
**Date:** YYYY-MM-DD

## Context
What situation or decision prompted this insight?

## Lesson
The core takeaway.

## Decision Guidance
When facing [situation], consider [approach] because [reason].

## Related Lessons
Links to other lessons that connect to this one.
```

## Index

| # | Title |
|---|-------|
| [001](lessons/001-separate-meta-learning-from-project-repos.md) | Separate Meta-Learning from Project Repos |
| [002](lessons/002-project-insights-folder-complements-adrs.md) | Project Insights Folder Complements ADRs |
| [003](lessons/003-every-change-needs-a-task-document.md) | Every Change Needs a Task Document |
| [004](lessons/004-retroactive-documentation-when-adopting-task-doc-rule.md) | Retroactive Documentation: When Adopting a Task-Doc Rule Mid-Project |
| [005](lessons/005-abstract-test-infrastructure-for-local-vs-ci.md) | Abstract Test Infrastructure to Support Local Dev and CI Independently |
| [006](lessons/006-explicit-milestone-tags-in-checklists.md) | Make Milestone Tags Explicit Checklist Items |
| [007](lessons/007-structured-backlog-for-ai.md) | Structured Backlog Management for AI Agents |
| [008](lessons/008-optimize-ai-model-usage.md) | Optimize AI Model Usage - Gemini for Workflow, Claude for Deep Work |
| [009](lessons/009-single-source-of-truth-for-tasks.md) | Single Source of Truth for Task Numbering |
| [010](lessons/010-organize-project-insights-by-category.md) | Organizing Project Insights into Logical Categories |
| [011](lessons/011-need-for-component-guidelines.md) | The Need for Component-Specific Guidelines |
