# Finance Ledger

這是給 Obsidian 財務保險庫使用的 Codex skill，用來記錄每日支出與每月財務總結。

English: [README.md](README.md)

## 這個 skill 做什麼

- 把每日花費記到 `Finance/支出紀錄/YYYY-MM/` 底下的日期筆記
- 維持適合 Dataview 和月報圖表的結構
- 同步更新月頁，讓總覽、圖表與統計保持一致
- 保留 `daily_budget`、`remaining_today` 和月度固定項目的規則

## 倉庫結構

- `SKILL.md`：Codex 讀取的主要技能說明
- `agents/openai.yaml`：Codex skill 清單與 chip 的 UI metadata
- `references/finance-workflow.md`：較完整的工作流程參考

## 使用時機

當你需要 Codex：

- 記錄一筆新的每日支出
- 更新既有的日記頁
- 刷新當月總結頁
- 讓月報圖表與每日記錄對齊

## 備註

- 這個 skill 依照 `Finance/AGENTS.md` 的規則設計
- `daily_budget` 只代表飲食預算，交通與其他支出要留在正文表格
- 月結預設把 `訂閱費`、`基金`、`美股` 視為已完成的固定項目
