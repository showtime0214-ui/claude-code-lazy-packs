# 懶人包安裝狀態總表

> 更新日期：2026-06-01
> 環境：Windows / OpenCode
> GitHub Repo: [showtime0214-ui/claude-code-lazy-packs](https://github.com/showtime0214-ui/claude-code-lazy-packs)

---

| # | 懶人包 | 狀態 | 詳情 |
|---|--------|------|------|
| 00 | 環境建置 | ✅ | Git、GitHub CLI、uv 已安裝 |
| 01 | NotebookLM | ✅ | `nlm` v0.6.13、已登入 showtime0214@gmail.com、OpenCode MCP 已連線、8 輸出資料夾已建 |
| 02 | GitHub | ✅ | `gh` CLI 已登入、git config OK、可透過 OpenCode bash 操作 |
| 03 | Obsidian | ✅ | MCP 已設定 (`@bitbonsai/mcpvault`) |
| 04 | 第二大腦 | ✅ | 三層結構已建（Clippings/ → 知識庫/ → 創作庫/）、Templates + CLAUDE.md + 歡迎筆記 |
| 05 | Ollama | ⏳ | winget 下載中斷（1.98GB 逾時），待重試。記憶體 8GB 建議裝 `gemma4:e2b` |
| 06 | Gemini API | ⏳ | API Key 未申請。需手動到 [Google AI Studio](https://aistudio.google.com/apikey) 建立 |
| 07 | Firebase | ⏳ | MCP 已設定但未登入。需在本機跑 `firebase login:ci` 取得 auth code |
| 08 | 工作模式 | ✅ | 專案 `muzha-ptt-opencode` 已初始化（Git + GitHub + Obsidian） |
| 09 | Draw (gpt-image-2) | ✅ | `draw` skill 已可用 |

---

## 待完成項目

### 1. Ollama（本地 AI）
**步驟：**
```powershell
winget install --id Ollama.Ollama --accept-source-agreements --accept-package-agreements
```
**模型選擇（8GB RAM）：**
```bash
ollama pull gemma4:e2b
```

### 2. Gemini API Key
**步驟：**
1. 開啟 https://aistudio.google.com/apikey
2. 登入 Google 帳號 → Create API Key
3. 複製 Key → 貼給我設定環境變數

### 3. Firebase 登入
**步驟：**
1. 開啟 PowerShell
2. 執行 `npx -y firebase-tools@latest login:ci --no-localhost`
3. 瀏覽器會打開 → 登入 Google → 複製授權碼
4. 回到 PowerShell 貼上 → Enter
5. 跟我說完成

---

## 常用指令速查

| 功能 | 指令 |
|------|------|
| NotebookLM 狀態 | `nlm doctor` |
| GitHub 狀態 | `gh auth status` |
| Firebase 登入 | `npx firebase-tools login:ci` |
| 本地 AI 測試 | `ollama run gemma4:e2b "你好"` |
| Gemini API 測試 | `curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=$GEMINI_API_KEY" -H "Content-Type: application/json" -d '{"contents":[{"parts":[{"text":"你好"}]}]}'` |

---

*本文件由 OpenCode 自動產生，持續更新。*
