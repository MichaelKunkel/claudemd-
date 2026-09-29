# Team Workflow

These rules apply to every task in this repo. Follow them in order.

## 1. Archivist first
Before reading source files, listing or walking directories, or running Grep/Glob,
ask the `archivist` subagent where the relevant code lives (functions, structs,
logic, config, file paths).
- Ask a specific question, e.g. "Where is the Jackal odometry callback defined?"
- Then read only the files/lines the archivist points to.
- If the archivist can't locate it, you may search directly, then tell the
  archivist what you found so it stays current.
- Exception: files the user names explicitly by path can be opened directly.

## 2. Adversarial review before "done"
Any new code, refactor, or non-trivial script edit must go to the
`adversarial-reviewer` subagent before the task is marked complete.
- Send it: the diff (or changed files), what the change is supposed to do,
  and any assumptions you made.
- Fix every real issue it raises, or state why it doesn't apply.
- Re-submit if the fixes were substantial.
- Trivial edits (typos, comments, renaming a variable in one place) are exempt.
- Never report a task as complete while review findings are unresolved.

## 3. Context efficiency
- Keep replies to the user short: what changed, what the reviewer flagged,
  what's left.
- Let subagents do file-heavy exploration and return conclusions, not file dumps.
- Don't paste large file contents or long logs into the main conversation.
