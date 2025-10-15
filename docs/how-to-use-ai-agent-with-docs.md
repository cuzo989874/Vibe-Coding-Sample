## How to Build an Application with an AI Agent Using `/docs/` Files

To effectively build an application with an AI agent, leveraging the project's documentation is crucial. The `/docs/` directory serves as the central knowledge base that guides the AI agent's understanding, planning, and implementation processes. Here's a walkthrough:

### 1. Understand the Role of Documentation

The documents within the `/docs/` directory provide the AI agent with the necessary context, requirements, architectural decisions, and operational rules for the project. These documents are not just for human consumption; they are directly interpretable by the AI agent to ensure adherence to project standards and goals.

### 2. Referencing Documents in Your Prompts

When you provide a prompt to the AI agent, you can explicitly reference specific documents using the `@` symbol followed by the relative path to the document. This tells the AI agent to load and consider the content of that document for the current task.

**Example:**
`implement @docs/architectural-analysis.md @docs/product-requirements-document.md, follow @docs/workflow/basic-rules.md @docs/workflow/engineer-workflow-rules.md as rule`

In this example, the AI agent will:
- Read and understand the architectural decisions from `architectural-analysis.md`.
- Grasp the functional and non-functional requirements from `product-requirements-document.md`.
- Adhere to the operational guidelines specified in `engineer-workflow-rules.md` during implementation.

### 3. Following Workflow Rules

Workflow rules (e.g., `basic-rules.md`, `engineer-workflow-rules.md`) are critical for defining the AI agent's operational behavior. When referenced, the AI agent will integrate these rules into its workflow, ensuring actions like prompt logging, checklist updates, and adherence to coding standards.

### 4. The Iterative Development Process

Building an application with an AI agent and documentation typically follows an iterative loop:

1.  **Initial Prompt with Context:** Start by clearly stating your goal and referencing all relevant documentation. The more context you provide, the better the AI agent can understand the task.
2.  **AI Agent's Analysis & Planning:** The AI agent will first read and synthesize the information from the referenced documents. It will then formulate a plan, often outlining the steps it intends to take, the technologies it will use (based on architectural docs), and how it will meet the requirements.
3.  **User Approval (Optional but Recommended):** For significant tasks, the AI agent might present its plan for your approval, allowing you to guide the direction before implementation begins.
4.  **Implementation:** The AI agent will execute its plan, writing code, configuring files, and performing necessary shell commands. It will strictly adhere to the referenced architectural designs, product requirements, and workflow rules.
5.  **Verification:** After making changes, the AI agent will attempt to verify its work. This might involve running linting checks, build commands, or even unit tests (if a testing framework is set up and not explicitly canceled).
6.  **Feedback Loop:** You review the AI agent's output and provide further instructions or corrections. The agent then iterates on the task, incorporating your feedback.

### 5. Key Documents and Their Purpose

-   **Architectural Analysis (`architectural-analysis.md`):** Defines the high-level structure, technology stack, and data model. Guides the AI agent on *how* to build the system.
-   **Product Requirements Document (`product-requirements-document.md`):** Details functional and non-functional requirements. Informs the AI agent *what* to build.
-   **Project Requirements (`project-requirements.md`):** Outlines finalized requirements and specific constraints. Provides granular details for the AI agent's implementation.
-   **Workflow Rules (`workflow/*.md`):** Dictate the AI agent's operational behavior, such as how to log prompts, update checklists, and ensure code quality. Guides the AI agent on *how to operate*.

### 6. Best Practices for Users

-   **Be Explicit:** Always reference the documents you want the AI agent to consider.
-   **Clear Goals:** State your task clearly and concisely.
-   **Iterate:** Break down complex tasks into smaller, manageable steps.
-   **Review:** Regularly review the AI agent's output and provide constructive feedback.

By following these guidelines, you can effectively collaborate with the AI agent to build robust applications, ensuring that all project specifications and best practices are consistently met.

### 7. Handling Disconnections and Recovering State

If you get disconnected while working with the AI agent, you can help it recover its progress by using the log files it maintains. The `check-list.md` and `notepad.md` files are particularly useful for this.

**Example Prompt to Recover:**
` Use @docs/log/check-list.md and @docs/log/notepad.md to restore your work state and continue the previous task.`

By providing these files, the agent can review its last-known state, including completed tasks and notes, allowing it to resume work more effectively.

### Walkthrough: From Generating Development Documents to Code Modification

After the AI agent has successfully created the initial project, the next step is often to modify or add new features. A powerful workflow is to start by generating new design or specification documents and then instructing the agent to implement them. This ensures that development remains aligned with clear, documented goals.

Here’s how to approach this:

#### Step 1: Initiate the Generation of a New Development Document

Before modifying code, instruct the agent to create a new design or specification document. This initiates a collaborative process to define the feature, ensuring clarity before implementation. For a more stable generation process, it's recommended to always include `@docs/workflow/basic-rules.md`.

**Example Prompt:**
`As a Project Manager, please create a detailed development document for a new "Pomodoro Timer" feature. The output should be a new file located at 'docs/features/pomodoro-timer-spec.md'. Base the content on @docs/product-requirements-document.md. Follow the processes in @docs/workflow/pm-workflow-rules.md and @docs/workflow/basic-rules.md.`

Following its workflow, the agent will then analyze the request, potentially ask for more details, propose an outline for the new document, and await your approval before drafting the full content. This ensures the resulting specification is fully aligned with your vision.

#### (Optional) Step 1.5: Involve an Architect for Major Changes

The Architect role isn't just for initial setup. If a new feature is large, complex, or requires changes to the core application structure (e.g., adding a new microservice, introducing a state management library), you should involve an Architect after the initial spec is created.

**Example Prompt for an Architect:**
`As an Architect, based on the new feature spec @docs/features/pomodoro-timer-spec.md, please update the project's architectural design and create the necessary technical specifications as a new file at 'docs/features/pomodoro-timer-tech-spec.md'. The existing architecture is defined in @docs/architectural-analysis.md. Follow the rules in @docs/workflow/architect-workflow-rules.md and @docs/workflow/basic-rules.md.`

The Architect would then produce updated design documents, which the Engineer would use in the next step. For simpler features that fit the existing architecture, this step can be skipped.

#### Step 2: Request Code Modification Based on the New Document

Once the new specification document (and any architectural updates) are ready, you can instruct the Engineer to implement the changes. The prompt will vary slightly depending on whether an Architect was involved.

**Example Prompt (if Step 1.5 was skipped):**
*This is for features that fit within the existing architecture.*
`As an Engineer, implement the "Pomodoro Timer" feature according to @docs/features/pomodoro-timer-spec.md. Follow the existing architecture defined in @docs/architectural-analysis.md and adhere to the workflows in @docs/workflow/engineer-workflow-rules.md and @docs/workflow/basic-rules.md.`

**Example Prompt (if Architect was involved in Step 1.5):**
*Note how this prompt refers to the **new** technical spec created by the Architect.*
`As an Engineer, implement the "Pomodoro Timer" feature according to the new technical specification @docs/features/pomodoro-timer-tech-spec.md. Adhere to the workflows in @docs/workflow/engineer-workflow-rules.md and @docs/workflow/basic-rules.md.`

#### Step 3: Review and Iterate

The AI agent will now read the new specification and the existing architectural and workflow documents to modify the codebase. It will:
1.  Identify the relevant files to change.
2.  Write the new code for components, services, and UI elements.
3.  Update any related files to integrate the feature.

Your role is to review the implemented changes, run tests, and provide feedback. This continues the iterative development cycle, ensuring that even complex modifications are built on clear, pre-defined specifications.
