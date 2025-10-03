## 如何使用 `/docs/` 文件與 AI Agent 一同建構應用程式

要有效地使用 AI Agent 建構應用程式，善用專案的文件至關重要。`/docs/` 目錄是核心的知識庫，它引導 AI Agent 的理解、規劃和實作過程。這是一份演練指南：

### 1. 了解文件的角色

`/docs/` 目錄中的文件為 AI Agent 提供了專案所需的上下文、需求、架構決策和操作規則。這些文件不僅供人類閱讀，AI Agent 也可以直接解釋它們，以確保遵循專案的標準和目標。

### 2. 在提示中引用文件

當您向 AI Agent 提供提示時，可以使用 `@` 符號後接文件的相對路徑來明確引用特定文件。這會告訴 AI Agent 為當前任務載入並考慮該文件的內容。

**範例：**
`implement @docs/architectural-analysis.md @docs/product-requirements-document.md, follow @docs/workflow/basic-rules.md @docs/workflow/engineer-workflow-rules.md as rule`

在此範例中，AI Agent 將會：
- 閱讀並理解 `architectural-analysis.md` 中的架構決策。
- 掌握 `product-requirements-document.md` 中的功能性和非功能性需求。
- 在實作過程中遵守 `engineer-workflow-rules.md` 中指定的操作指南。

### 3. 遵循工作流程規則

工作流程規則（例如 `basic-rules.md`、`engineer-workflow-rules.md`）對於定義 AI Agent 的操作行為至關重要。當被引用時，AI Agent 會將這些規則整合到其工作流程中，確保執行提示記錄、清單更新和遵守編碼標準等操作。

### 4. 迭代開發過程

使用 AI Agent 和文件建構應用程式通常遵循一個迭代循環：

1.  **提供附有上下文的初始提示：** 首先清晰地陳述您的目標，並引用所有相關文件。您提供的上下文越多，AI Agent 就越能理解任務。
2.  **AI Agent 的分析與規劃：** AI Agent 會首先閱讀並綜合來自引用文件的資訊。然後它會制定一個計劃，通常會概述它打算採取的步驟、將使用的技術（基於架構文件）以及如何滿足需求。
3.  **使用者批准（可選但建議）：** 對於重大任務，AI Agent 可能會提交其計劃供您批准，讓您在實作開始前引導方向。
4.  **實作：** AI Agent 將執行其計劃，撰寫程式碼、配置檔案並執行必要的 shell 命令。它將嚴格遵守所引用的架構設計、產品需求和工作流程規則。
5.  **驗證：** 進行變更後，AI Agent 會嘗試驗證其工作。這可能包括運行 linting 檢查、建構命令，甚至單元測試（如果已設定測試框架且未被明確取消）。
6.  **回饋循環：** 您審查 AI Agent 的產出並提供進一步的指示或修正。然後，Agent 會根據您的回饋迭代執行任務。

### 5. 關鍵文件及其用途

-   **架構分析 (`architectural-analysis.md`):** 定義高層結構、技術堆疊和資料模型。指導 AI Agent *如何* 建構系統。
-   **產品需求文件 (`product-requirements-document.md`):** 詳細說明功能性和非功能性需求。告知 AI Agent *要建構什麼*。
-   **專案需求 (`project-requirements.md`):** 概述最終確定的需求和具體限制。為 AI Agent 的實作提供精細的細節。
-   **工作流程規則 (`workflow/*.md`):** 規定 AI Agent 的操作行為，例如如何記錄提示、更新清單和確保程式碼品質。指導 AI Agent *如何操作*。

### 6. 使用者最佳實踐

-   **明確指示：** 始終引用您希望 AI Agent 考慮的文件。
-   **目標清晰：** 簡潔明瞭地陳述您的任務。
-   **迭代進行：** 將複雜的任務分解為更小、可管理的步驟。
-   **定期審查：** 定期審查 AI Agent 的產出並提供建設性的回饋。

遵循這些指南，您可以有效地與 AI Agent 協作，建構穩健的應用程式，確保所有專案規格和最佳實踐都得到一致的滿足。

### 演練：從生成開發文件到程式碼修改

在 AI Agent 成功創建初始專案後，下一步通常是修改或添加新功能。一個強大的工作流程是從生成新的設計或規格文件開始，然後指示 Agent 實作它們。這確保了開發過程與清晰、文件化的目標保持一致。

操作方法如下：

#### 步驟 1：啟動新開發文件的生成流程

在修改程式碼之前，先指示 Agent 創建一份新的設計或規格文件。這會啟動一個協作流程來定義功能，確保在實作前達成共識。為了讓生成過程更穩定，建議總是加入 `@docs/workflow/basic-rules.md`。

**範例提示：**
`As a Project Manager, please create a detailed development document for a new "Pomodoro Timer" feature. The output should be a new file located at 'docs/features/pomodoro-timer-spec.md'. Base the content on @docs/product-requirements-document.md. Follow the processes in @docs/workflow/pm-workflow-rules.md and @docs/workflow/basic-rules.md.`

根據其工作流程，Agent 接著會分析需求，可能會詢問更多細節，提出新文件的綱要，並在起草完整內容前等待您的批准。這確保最終產出的規格文件完全符合您的願景。

#### (可選) 步驟 1.5：針對重大變更引入架構師

架構師的角色不僅限於初始設定。如果新功能規模龐大、複雜，或需要變更核心應用程式結構（例如，添加新的微服務、引入狀態管理庫），您應該在初始規格文件創建後引入架構師。

**給架構師的範例提示：**
`As an Architect, based on the new feature spec @docs/features/pomodoro-timer-spec.md, please update the project's architectural design and create the necessary technical specifications as a new file at 'docs/features/pomodoro-timer-tech-spec.md'. The existing architecture is defined in @docs/architectural-analysis.md. Follow the rules in @docs/workflow/architect-workflow-rules.md and @docs/workflow/basic-rules.md.`

架構師接著會產出更新後的設計文件，工程師將在下一步中使用這些文件。對於能夠融入現有架構的較簡單功能，則可以跳過此步驟。

#### 步驟 2：根據新文件請求程式碼修改

一旦新的規格文件（以及任何架構更新）準備好，您就可以指示工程師實作這些變更。根據是否有架構師參與，提示會略有不同。

**範例提示（若跳過步驟 1.5）：**
*此情況適用於可融入現有架構的功能。*
`As an Engineer, implement the "Pomodoro Timer" feature according to @docs/features/pomodoro-timer-spec.md. Follow the existing architecture defined in @docs/architectural-analysis.md and adhere to the workflows in @docs/workflow/engineer-workflow-rules.md and @docs/workflow/basic-rules.md.`

**範例提示（若架構師參與了步驟 1.5）：**
*請注意此提示如何引用由架構師創建的**新**技術規格文件。*
`As an Engineer, implement the "Pomodoro Timer" feature according to the new technical specification @docs/features/pomodoro-timer-tech-spec.md. Adhere to the workflows in @docs/workflow/engineer-workflow-rules.md and @docs/workflow/basic-rules.md.`

#### 步驟 3：審查與迭代

AI Agent 現在將讀取新的規格文件以及現有的架構和工作流程文件來修改程式碼庫。它將：
1.  識別要變更的相關檔案。
2.  為組件、服務和 UI 元素撰寫新程式碼。
3.  更新任何相關檔案以整合該功能。

您的角色是審查已實作的變更、運行測試並提供回饋。這延續了迭代開發週期，確保即使是複雜的修改也能建立在清晰、預先定義的規格之上。