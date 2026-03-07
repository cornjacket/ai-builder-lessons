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
| [012](lessons/012-use-chat-for-architecture-discussions.md) | Use Claude Chat for Architecture Discussions, Reserve Claude Code for Implementation |
| [013](lessons/013-concise-output-reduces-token-waste.md) | Concise Output Reduces Token Waste |
| [014](lessons/014-separate-task-tracking-by-scope.md) | Separate Task Tracking by Scope, Not by Repo Count |
| [015](lessons/015-bootstrap-scripts-for-multi-repo-workspaces.md) | Bootstrap Scripts for Multi-Repo Workspaces |
| [016](lessons/016-commit-task-doc-before-implementation.md) | Commit the Task Doc Before Implementation |
| [017](lessons/017-git-worktrees-for-parallel-ai-work.md) | Git Worktrees for Parallel AI Work |
| [018](lessons/018-review-ai-diffs-before-committing.md) | Review AI Diffs Before Committing |
| [019](lessons/019-instruction-file-design.md) | Instruction File Design (Ground Rules) |
| [020](lessons/020-proactive-knowledge-capture.md) | Proactive Knowledge Capture During AI Sessions |
| [021](lessons/021-specialist-agents-vs-single-generalist.md) | Specialist Agents vs Single Generalist |
| [022](lessons/022-selective-reference-doc-loading.md) | Selective Reference Doc Loading |
| [023](lessons/023-big-doc-threshold.md) | Define a Big Doc Threshold |
| [024](lessons/024-perfect-recall-fallacy.md) | The Perfect Recall Fallacy |
| [025](lessons/025-sandbox-for-experiments.md) | Use a Sandbox for Throwaway Experiments |
| [026](lessons/026-verify-assumptions-before-implementing.md) | Verify Assumptions Before Implementing |
| [027](lessons/027-chain-of-small-steps.md) | Chain of Small Verifiable Steps |
| [028](lessons/028-predictive-tdd.md) | Predictive TDD: Predict Before Running Tests |
| [029](lessons/029-git-hooks-for-ai-compliance.md) | Git Hooks for AI Compliance |
| [030](lessons/030-instruction-sandwich.md) | Instruction Sandwich: Reinforce Critical Rules |
| [031](lessons/031-silent-misalignment.md) | Silent Misalignment: When the AI Agrees But Is Wrong |
| [032](lessons/032-active-partner.md) | Give AI Permission to Push Back |
| [033](lessons/033-context-markers-for-rot-detection.md) | Context Markers for Rot Detection |
| [034](lessons/034-human-prompting-best-practices.md) | Human Prompting Best Practices |
| [035](lessons/035-organize-documents-for-ai-readability.md) | Organize Documents for AI Readability |
| [036](lessons/036-directory-structure-as-status-indicator.md) | Use Directory Structure as Status Indicator |
| [037](lessons/037-context-hygiene-dentist-pattern.md) | Context Hygiene: The Dentist Pattern |
