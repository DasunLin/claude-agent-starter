# Claude Code 新手 Starter（git 版 — 連檔案都不用管）

給一個只用過網頁版 AI 的人，**最少動作**得到一個已經調好、認識他、有人格、有記憶的私人 AI 夥伴。

## 怎麼用（四個動作，不用懂程式、不用碰終端機、不用選資料夾）

1. 去 <https://claude.ai> 下載 **Claude 桌面 App**，裝好登入（需 Pro/Max 訂閱）。
2. 打開 App → 點上方 **Code** 分頁。
3. 點 **New session（新對話）**。
4. 把下面這段話貼進對話框，按 Enter：

> 請用 curl 取得 `https://raw.githubusercontent.com/DasunLin/claude-agent-starter/main/SETUP.md` 的原始內容（不要用會摘要的方式），然後完全照著它幫我設定。我是新手，請一步步帶我。

接下來 AI 會自己 clone 這個 repo、把 agent 裝到 `~/.claude/`、再用 `/agent-setup` skill 跟你對話完成個人化。放輕鬆回答就好。

## 設定好之後
- 開新對話覺得它忘了你 → `/relay`
- 做完一段事想存起來 → `/retro`
- 想再調人設 / 加新指令 → `/agent-setup`
- 想用得更順不被打斷 → 點畫面**左下角**切到 Auto-accept
- 想改任何東西 → 直接用講的叫它改

## 這個 repo 裝了什麼
- `home-claude/` → 會被複製到使用者的 `~/.claude/`（user 層，每個對話自動載入，與工作資料夾無關）
  - `CLAUDE.md` — agent 的靈魂/身分/使用者/鐵則（含待填空格）
  - `skills/agent-setup/` — 安裝 + 之後隨時 tune/extend 這個 agent
  - `skills/{relay,retro}/` — 開工接力 / 收尾覆盤兩個指令
  - `agent-memory/INDEX.md` — 記憶索引（會隨使用長出來）
- `SETUP.md` — 給 AI 讀的安裝腳本（裝完交棒給 /agent-setup）

## 維護
改 `home-claude/` 或 `SETUP.md` → commit & push。使用者端下次重跑貼上句即拿到最新；已安裝者打 `/agent-setup` 不會自動更新檔案（更新機制為 backlog）。
