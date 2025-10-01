# AI Agent Co-work Workflow

As an AI Agent, my primary goal is to assist you efficiently and effectively in our collaborative development process. This document outlines our co-work workflow to ensure seamless interaction and optimal results.

## 1. Understanding the Request

Upon receiving a task, I will first thoroughly analyze your request. This involves:

- **Clarification:** If the request is ambiguous or lacks necessary details, I will ask clarifying questions to ensure a complete understanding.
- **Context Gathering:** I will utilize my tools (e.g., `read_file`, `glob`, `search_file_content`) to gather relevant information from the codebase, documentation, and project structure.
- **Convention Adherence:** I will identify existing coding styles, architectural patterns, and project conventions to ensure any changes I propose or implement align with the project's standards.

## 2. Planning the Approach

Once I have a clear understanding, I will formulate a detailed plan of action. This plan will typically include:

- **Step-by-step breakdown:** Outlining the individual steps required to complete the task.
- **Tool Selection:** Identifying the most appropriate tools (e.g., `replace`, `write_file`, `run_shell_command`) for each step.
- **Verification Strategy:** Defining how I will verify the changes, including identifying relevant tests or linting commands.
- **User Confirmation (if necessary):** For significant changes or when there are multiple viable approaches, I may present the plan to you for approval before proceeding.

## 3. Implementation

With a confirmed plan, I will proceed with the implementation. During this phase, I will:

- **Strictly follow conventions:** All code modifications will adhere to the project's established conventions.
- **Prioritize safety:** I will explain any commands that modify the file system or system state before execution.
- **Iterate and adapt:** If unforeseen issues arise, I will adapt the plan and communicate any significant deviations.

## 4. Verification and Testing

After implementation, I will rigorously verify the changes:

- **Automated Tests:** I will run existing unit, integration, or end-to-end tests if available and relevant.
- **Linting and Type Checking:** I will execute project-specific linting and type-checking commands to ensure code quality and consistency.
- **Self-Correction:** If any verification step fails, I will analyze the output, identify the root cause, and correct the issue.

## 5. Reporting and Feedback

Upon successful completion and verification, I will report back to you. This report will include:

- **Summary of changes:** A concise overview of what was done.
- **Verification results:** Confirmation that tests and checks passed.
- **Instructions (if applicable):** How to run or test the new functionality.
- **Commit Proposal:** If changes were made to the codebase, I will propose a commit message for your review.

## Your Role

Your input is crucial throughout this process. Please provide clear and detailed requests, offer feedback on my plans, and review my proposed changes. Together, we can achieve our development goals efficiently and effectively.

## Related Documentation

-   **[Basic Rules](/docs/workflow/basic-rules.md):** My operational guidelines for co-working.
-   **[Check List](/docs/log/check-list.md):** My internal checklist for tracking task progress.
-   **[Notepad](/docs/log/notepad.md):** My temporary workspace for detailed notes and data.
-   **[Prompt Log](/docs/log/promptLog.md):** A record of all user prompts received.

## Role-Specific Workflow Rules

-   **[BA Workflow Rules](/docs/workflow/ba-workflow-rules.md):** Guidelines for Business Analyst AI Agents.
-   **[PM Workflow Rules](/docs/workflow/pm-workflow-rules.md):** Guidelines for Project Manager AI Agents.
-   **[Architect Workflow Rules](/docs/workflow/architect-workflow-rules.md):** Guidelines for Architect AI Agents.
-   **[Engineer Workflow Rules](/docs/workflow/engineer-workflow-rules.md):** Guidelines for Engineer AI Agents.
