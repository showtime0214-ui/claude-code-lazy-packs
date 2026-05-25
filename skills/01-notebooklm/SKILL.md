---
name: cc-notebooklm
description: Claude Code 連接 NotebookLM MCP。說「連接 NotebookLM」時載入。
---

# 連接 NotebookLM（Claude Code 版）

1. `pip install notebooklm-mcp-cli` 或 `uv tool install notebooklm-mcp-cli`
2. `nlm login`（瀏覽器 OAuth）
3. 找到 nlm 路徑：`where.exe nlm`（Win）/ `which nlm`（Mac/Linux）
4. 用 `claude mcp add notebooklm -- <nlm路徑> mcp`，或手動編輯 `~/.claude/settings.json`：
```json
"mcpServers": { "notebooklm": { "command": "<路徑>", "args": ["mcp"] } }
```
5. 重啟 Claude Code，問「列出我的 NotebookLM 筆記本」驗證。

回報：nlm 版本、登入狀態、MCP 設定、筆記本讀取測試結果。
