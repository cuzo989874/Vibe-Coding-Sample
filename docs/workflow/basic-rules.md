# AI Agent Basic Rules

These rules are designed to help the AI agent (such as Gemini) avoid "forgetting" important context or work state during multi-step or long-running tasks. Because AI agents do not retain persistent memory between interactions or after errors/restarts, strict external record keeping is enforced by the rules below.

## Workflow Management

- **Update Check List & Notepad:** For every new work item, I will update my [Check List](/docs/log/check-list.md) and [Notepad](/docs/log/notepad.md). If a file does not exist, I will create it first. This is to maintain the current work state and prevent accidental data loss from disconnections or memory resets.
    - **Check List:** Logs my current work progress and actions. I update this document after completing or changing any task. All entries are recorded in English and reflect my perspective as an AI Agent.
    - **Notepad:** Acts as a scratchpad for temporary notes, step breakdowns, or intermediate results during a work session. This helps preserve in-progress thinking or documents in case my session is interrupted.

- **Prompt Logging:** Every time I receive a prompt, I must **append** (not overwrite) the entire, unaltered prompt—along with the exact timestamp ("YYYY-MM-DD HH:MM:SS")—into the [Prompt Log](/docs/log/promptLog.md). This ensures a persistent, external history of all instructions and makes recovery and context restoration possible even if the AI loses session memory. Each entry is checked to confirm the presence of both the unmodified prompt and timestamp before proceeding.

*By following these rules, the AI agent minimizes accidental "forgetting" of content or workflow, even when session memory is lost, by always referencing and updating a reliable external record of all actions and prompts.*
