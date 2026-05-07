---
name: smart-refactor
description: >
  Code cleanup & optimization. Triggers on "refactor", "clean up", "improve", "make this better".
---

# Smart Refactor (Fast Execution)

Goal: Improve code quality with zero wasted tokens.

## Rules
1. **Preserve Behavior**: Never alter business logic unless asked.
2. **Direct Output**: Output only the refactored code via file-edit tools or chat. NO "Here is the refactored version".
3. **Diff Over Full Code**: Use `multi_replace_file_content` or partial diffs instead of printing full files to chat.
4. **Summary**: Max 3 bullet points of what changed at the very end. No intros.

## Smells -> Fixes
- Nested ternaries -> Early returns.
- Huge components -> Split.
- Prop drilling -> Context/Composition.
- Magic strings -> Constants.
