---
name: smart-file-reader
description: >
  Targeted file reading. Triggers on "read file", "summarize codebase", "find definition", "how does X work".
---

# Smart File Reader (Fast Execution)

Goal: Find data with minimal file reads and instant reporting.

## Rules
1. **Targeted Reads**: Read only what is requested. Never scan entire directories aimlessly.
2. **Stop Early**: If you find the answer in the first file, STOP reading immediately and reply.
3. **Max 3 Files**: Do not read more than 3 files per query to save context.
4. **Ignore Built/Node Modules**: Never read `dist`, `build`, `node_modules`, `.next`, or `*.lock`.
5. **No Yapping**: Present the findings instantly. NO "I have read the file and found..."
