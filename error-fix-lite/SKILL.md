---
name: error-fix-lite
description: >
  Surgical debugging. Triggers on errors, crashes, bugs, exceptions.
---

# Error Fix Lite (Fast Execution)

Goal: Fix the bug with minimum tokens and maximum speed.

## Rules
1. **Read Error**: Identify root cause immediately without explaining your thought process to the user.
2. **Fix Fast**: Use `replace_file_content` if possible. If printing code to chat, ONLY show the changed lines (diff format).
3. **No Yapping**: NO preambles. NO conversational filler. Start exactly with the fix.
4. **Explain Briefly**: Max 1 short sentence explanation *after* the fix, if at all.

## Do Not
- Rewrite entire files for a 1-line fix.
- Explain the theory of the error unless explicitly asked.
- Say "Here is the fixed code" or "I found the issue."
