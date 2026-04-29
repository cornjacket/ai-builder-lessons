# Lesson 038 — Running Work Log at Task Granularity, Indexed by Commit Hash

**Category:** process
**Date:** 2026-04-29

## Context

`git log` is too granular to skim — it records commits, not the questions or concepts they answered. Conversation transcripts capture intent but aren't searchable and decay over time. There is a gap between "what did we change" (the diff) and "what were we working on" (the task), and AI sessions amplify the gap because work moves faster and produces more commits than a human alone would generate.

## Lesson

Keep a `log.md` at the repo root as a date-ordered record of work at **task / question / concept** granularity — *not* per prompt. Multiple prompts inside the same task share one entry. Open a new entry only when the focus changes: a new task starts, the user asks a substantively different question, or a meaningfully new concept comes up. Each entry is one or two sentences of *what changed and why*; the diff and `git log` carry the rest. **Every entry ends with the short commit hash that delivered the work** (e.g. ``Commit `abc1234`.``), which is what lets the log act as a quick index back into git history.

Pair the log with a numbered rule in `CLAUDE.md` (or equivalent instruction file). Without an enforcing rule, the log either drifts to per-prompt noise or stops being maintained. The rule must call out both failure modes — entries-per-prompt *and* tasks-without-entries — and must require the commit hash.

Back-fill discipline matters: when an entry is written before its commit lands, add the hash directly in `log.md` after the commit and let it ride into the next task's commit. **Do not create a dedicated commit just to back-fill the hash.** Two commits per task is a smell and trains the wrong habit.

## Decision Guidance

Adopt this when an AI agent is producing more commits per session than a human reader can hold in their head, and when "what were we doing last Tuesday?" is a question that comes up. Skip it on solo, slow-moving repos where `git log --oneline` is already readable. When bootstrapping into an existing repo, create `log.md` and the `CLAUDE.md` rule together — one without the other is a half-measure that won't survive a few sessions.

If the agent isn't sure whether the latest message starts a new task or continues an existing one, it should ask before writing the entry — picking the wrong granularity is harder to undo than asking.

## Related Lessons

- [003](003-every-change-needs-a-task-document.md) — task docs are the per-task long form; `log.md` is the per-repo short index
- [016](016-commit-task-doc-before-implementation.md) — same family of commit-hygiene discipline
- [020](020-proactive-knowledge-capture.md) — capturing context as work happens, not after
- [029](029-git-hooks-for-ai-compliance.md) — alternate enforcement mechanism when an instruction-file rule isn't enough
