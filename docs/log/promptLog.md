# AI Agent Prompt Log

This document records all prompts received from the user, along with a timestamp, to maintain a complete history of interactions.

---
## Log Entries:

### 2025-10-01 14:40:27
```
接下來我們要來設計我們 co-work 的 workflow，請你在 /docs/ 建立 index.md，並且撰寫時以 AI Agent 的角度書寫。
```

### 2025-10-01 14:45:27
```
- 在接收到任何工作事項時，身為 AI Agent 你需要 update [Check List](/docs/log/check-list.md) & [notepad](/docs/log/notepad.md) 用來避免非預期的中斷連線或是非預期錯誤
    - Check List: 用來記錄 AI Agent 目前的工作進度，每次執行完工作時，AI Agent 都會回來這份 Check list 新增/修改 目前的工作事項。以英文撰寫，編輯時以 AI Agent 的角度編輯。
    - notepad: 用來作為 AI Agent 的工作記事本，這裡可以記錄任何暫存文檔或工作細節，用來避免在工作階段遺失資料。以英文撰寫，編輯時以 AI Agent 的角度編輯。
  - 在收到任何 Prompt 的時候將 User 的 Prompt 完整不做修改的書寫到 [Prompt Log](/docs/log/promptLog.md)，並留下 時間日期
  - 將這份設定作為 Basic Rule 存進去 /docs/workflow/ 中，並且撰寫時以 AI Agent 的角度書寫。
  - update 到 [index](/docs/index.md)
```

### 2025-10-01 14:45:27
```
接下來我們來準備其他 workflow 文件
---
你是一個具有高度 ai agent 使用經驗的軟體工程師，你熟知 vibe coding 的使用，我希望你能協助我以 vibe coding 來完成一個專案。
我希望你先協助我設計一套 workflow 讓 gemini cli 可以穩定的輸出程式碼。他能會負責下列的角色，這些 workflow 文檔位以英文輸出並且閱讀者以 AI Agent 為主。

- BA: 負責針對專案的可行性以及專案細節進行校正
- PM: 負責專案的規劃與管理
- 前後端架構設計師: 負責前後端架構的設計
- 前後端工程師: 負責前後端工程的實作

預期上他會 follow 以下步驟，若可以更細緻的切割請盡量切割:

1. 從 BA 端針對 User 需求進行分析及細節確認，強化並完整使用者對於需求的描述，避免詞彙模糊
2. 以 PM 的角色分析需求做出 PRD 文件
3. 以 前後端架構設計師的角色設計前後端架構
4. 以 前後端工程師的角色實作前後端工程
5. 以 PM 的角色驗收前後端工程

我需要你分別對每個角色的運作提供 workflow 的設計並產出屬於角色的 workflow rule 的 md 文件，並另外設計 index.md 文件來整合所有角色的 workflow rule。
workflow rule 這代表這些角色在作動之前必須要 follow 這些規則，若違背規則則停止作動。最後將這些檔案都存在 ./docs/workflow/ 資料夾下。
```

### 2025-10-01 14:56:56
```
設計一個 git commit 的 rule，並且 commit 現在的改動
```
