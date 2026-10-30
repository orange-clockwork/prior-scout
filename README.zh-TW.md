[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找出既有成果，查證後再下結論。**

Prior-Scout 是一個小型 Agent Skill，協助 AI agent 查找相似的軟體、函式庫、工具、
Agent Skills 與研究。它閱讀原始資料、確認重要功能，再簡短比較相似處、差異與尚未釐清的部分。

它由指示組成，使用 agent 既有的搜尋與來源讀取工具，並非獨立的搜尋引擎或研究服務。

## 何時使用

開發新功能前想找找現成的開源工具、尋找能處理特定任務的 Skill，或根據原始論文比較研究方法時，
都可以使用。一般修正及已有明確計畫的實作，不需要因此重新搜尋。

## 安裝

在要使用的專案目錄中執行以下 Codex 安裝命令，需要 Node.js 22.20 以上及 npm：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

這會將 `main` 的 Skill 複製到專案的 `.agents/skills/prior-scout/`。執行前先確認是否已有安裝。
若要讓各專案共用，加入 `--global`。

若要固定使用 v1.0.0，將 `orange-clockwork/prior-scout` 換成
`https://github.com/orange-clockwork/prior-scout/tree/v1.0.0`。
請檢查安裝後的檔案；可能需要開啟新的 agent 工作階段才能載入。

## 使用

在 Codex 中可以直接指定 Skill：

> 使用 $prior-scout，在我開發 Markdown 連結檢查工具前，先找找現有的開源工具。
> 根據文件比較它們對本地檔案與標題連結的支援，再為我的工具擬定實作計畫。

是否自動選用取決於執行環境與模型。

## 如何運作

Prior-Scout 找出相關候選，閱讀官方文件、儲存庫或論文等第一手資料，
比較有來源支持的功能並附上連結。已發布功能、規劃中的功能與未知項目會分開說明。
搜尋結果與摘要只作為線索，不算第一手查證。

預設最多使用六個搜尋查詢及八份不同的外部文件。這些是指示中的限制，沒有程式強制執行。

是否採用由你決定，它不會安裝候選工具。若你還要求了後續工作，agent 會接回原本的任務範圍。

## 限制

執行環境必須提供搜尋與來源讀取工具。搜尋範圍取決於工具及可存取的資料，
無法保證找齊所有成果，也可能漏掉更相近的方案。讀過文件不代表已確認工具的實際運作。

已測試的設定為 macOS 26.4.1 arm64 上的 Codex CLI 0.164.0 搭配 gpt-6.1-sol/high。
其他執行環境的原生支援尚未驗證，詳見[相容性紀錄](docs/compatibility.md)。

## 文件與授權

[Skill 指示](skills/prior-scout/SKILL.md) · [安全說明](SECURITY.md) ·
[v1.0 評估](evals/releases/v1.0.0.md) · [評估方法](evals/README.md) ·
[歷史案例](docs/examples.md) · [發布說明](docs/release-notes-v1.0.0.md) ·
[變更紀錄](CHANGELOG.md)

英文為主要維護版本。採用 [MIT 授權](LICENSE)。
