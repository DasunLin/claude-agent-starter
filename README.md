# Claude Code 新手 Starter（git 版 — 連檔案都不用管）

給一個只用過網頁版 AI 的人，**最少動作**得到一個已經調好、認識他、有人格、有記憶的私人 AI 夥伴。流程刻意分兩段：**先安裝 → 重啟 → 再個人化**（重啟讓新指令正確載入，也順便學到「重啟才生效」這個常用概念）。

## 怎麼用

**① 安裝**
1. 到 <https://claude.ai> 下載 **Claude 桌面 App**，裝好登入（需 Pro/Max 訂閱）。
2. 打開 App → **Code** 分頁 → **New session（新對話）**。
3. 貼下面這段話、按 Enter，AI 會把 agent 裝到你的 `~/.claude/`：

> 請用 curl 取得 `https://raw.githubusercontent.com/DasunLin/claude-agent-starter/main/SETUP.md` 的原始內容（不要用會摘要的方式），然後完全照著它幫我設定。我是新手，請一步步帶我。

**② 重啟**
把整個桌面 App **完全關閉再重新打開**（不是只關視窗）。剛裝的指令要重開才會載入。

**③ 個人化**
重開後，Code 分頁開新對話，打 `/agent-setup` 按 Enter——它會訪談你（名字、你在忙什麼、想要什麼樣的夥伴），完成設定。

## 設定好之後
- 開新對話覺得它忘了你 → `/relay`
- 做完一段事想存起來 → `/retro`
- 想再調人設 / 加新指令 → `/agent-setup`
- 想用得更順不被打斷 → 點畫面**左下角**切到 Auto-accept
- 打 `/` 看所有可用指令

## 這個 repo 裝了什麼
- `home-claude/` → 複製到使用者 `~/.claude/`（user 層，每個對話自動載入，與工作資料夾無關）
  - `CLAUDE.md`（靈魂/身分/使用者/鐵則，含待填空格）、`skills/agent-setup/`（裝+調）、`skills/{relay,retro}/`、`agent-memory/INDEX.md`
- `SETUP.md` — 給 AI 讀的安裝腳本（只安裝，個人化交給重啟後的 /agent-setup）

## 維護
改 `home-claude/` 或 `SETUP.md` → commit & push；使用者下次重貼安裝句即拿到最新。已安裝者的檔案不會自動更新（backlog）。
