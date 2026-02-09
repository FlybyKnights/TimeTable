# AI Agent Instructions

When an AI agent receives a user request that results in changes to this project, the agent MUST do the following:

1. Keep a complete copy of the original user request.
2. Create a short summary of the changes made (one paragraph, or a bulleted list if multiple items).
3. Append an entry to `ai-change-log.txt` in the project root. Each entry must be appended (not overwritten) and include the following fields, in plain text:

   - Timestamp (ISO 8601, e.g. 2026-02-08T15:04:05Z)
   - Agent identifier (name or tool id)
   - Short summary of changes
   - Full original request (verbatim)

Example log entry format:

```
2026-02-08T15:04:05Z | assistant-v1
Summary: Added timetable.html, README.md, AI_INSTRUCTIONS.md, ai-change-log.txt
Request:
<full original request text goes here>
---
```

Notes for implementers:

- If your environment cannot write directly to the repository, create the entry locally and provide it to the user to commit, or include it in the agent's response so a human can append it to `ai-change-log.txt`.
- Keep `ai-change-log.txt` append-only and do not remove prior entries.
