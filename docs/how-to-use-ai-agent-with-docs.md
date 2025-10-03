## How to Build an Application with an AI Agent Using `/docs/` Files

To effectively build an application with an AI agent, leveraging the project's documentation is crucial. The `/docs/` directory serves as the central knowledge base that guides the AI agent's understanding, planning, and implementation processes. Here's a walkthrough:

### 1. Understand the Role of Documentation

The documents within the `/docs/` directory provide the AI agent with the necessary context, requirements, architectural decisions, and operational rules for the project. These documents are not just for human consumption; they are directly interpretable by the AI agent to ensure adherence to project standards and goals.

### 2. Referencing Documents in Your Prompts

When you provide a prompt to the AI agent, you can explicitly reference specific documents using the `@` symbol followed by the relative path to the document. This tells the AI agent to load and consider the content of that document for the current task.

**Example:**
`implement @docs/architectural-analysis.md @docs/product-requirements-document.md, follow @docs/workflow/engineer-workflow-rules.md as rule`

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
