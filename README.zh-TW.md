[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找出既有成果，查證後再下結論。**

輕量、只含指示的 Agent Skill，協助查找既有軟體、函式庫、Agent Skills 與研究。
閱讀第一手來源，區分有依據的主張與未驗證線索，簡短說明重要差異，然後繼續原本已授權的工作。

**1.0.0 · MIT · 已驗證範圍：Codex**

## 安裝

Skills CLI 1.7.4 需要 Node.js 22.20 以上及 npm；host 需提供檔案／來源閱讀與即時研究所需的搜尋工具。
在沒有同名 Skill 的專案中執行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

如需固定版本，將來源改成
`https://github.com/orange-clockwork/prior-scout/tree/v1.0.0`。
檢查安裝內容後開啟新的 agent session。
`npx skills@1.7.4 remove prior-scout -a codex -y` 移除該專案安裝；只有需要全域安裝才加 `--global`。

## 使用與觸發

> 使用 $prior-scout 查找既有開源 Markdown 連結檢查工具，閱讀第一手文件，
> 比較已支持的功能與限制，再為我的功能草擬三步實作計畫。

也適用於明確的替代方案、先例、相關研究，以及需要外部比較的新設計。
例如：「設計離線圖片功能前先比較既有函式庫」、「比較研究方法並區分實際測量結果與未知」、
「比較後繼續已授權的有限實作」、「只比較，不提供採用建議」。自動選擇仍取決於 host 與模型。
一般除錯、排版、重構、翻譯、文件清理與已定案的直接實作應直接處理。

## 工作方式與界線

1. 釐清需求、限制及剩餘已授權工作。
2. 預設最多六個搜尋字串、八份不同外部證據文件；失敗及批次內每個 query 都計數。
3. 實際取得第一手內容後，才提出其能支持的具體主張。網址、snippet、空頁或成功狀態碼都不足。
4. 簡短列出來源、交付形式、版本條件及未知，然後返回原本已授權工作。

已發布功能、計畫與整合可能性分開；hosted 服務不等於函式庫，API 不等於完整內建流程。
「未報告」不等於「未測量」或「不存在」。方法部分相關不代表證實未報告的研究效果。
讀取失敗時可在預算內找同作者或其他第一手來源，無法取得的部分保持未驗證。

Skill 沒有 runtime、依賴、遙測、搜尋服務或 API key；工具與權限由 host 提供。
預算與信任界線是指示，沒有程式強制保證。它不授權安裝、私人檔案讀取、上傳、
全域設定修改、發布或未要求的採用、商業及法律新穎性判斷。

## 支援與證據限制

[v1.0 評估紀錄](evals/releases/v1.0.0.md) 分開記錄版本、案例、原生發現、完整載入、
實際來源取得、行為與 baseline 比較；正式 Stable 須通過所有發布閘門。
Codex 是主要驗證 host；其他 agent 的支援只限於[相容性表](docs/compatibility.md)中的實測。
不宣稱通用準確率、安全性、完整檢索或相對 baseline 的統計優勢。

外部來源可能包含惡意指令；Skill 將其視為資料並保留使用者授權界線，仍需 host 沙箱與有限權限。
見[安全限制](SECURITY.md)。歷史 V03 的 Snyk 只回報 Low 第三方內容曝露指標 100/1000，
不是 v1.0 認證或抗注入保證。
GitHub 發布與 CLI 安裝不保證 [skills.sh](https://skills.sh/orange-clockwork/prior-scout/prior-scout)
立即更新索引；重裝或遙測不是保證強制更新的方法。

[核心指示](skills/prior-scout/SKILL.md) · [變更紀錄](CHANGELOG.md) ·
[歷史案例](docs/examples.md) · [發布說明](docs/release-notes-v1.0.0.md)

英文為主要維護版本；翻譯保留相同主張與限制。不散布私有 traces 或第三方來源快照。
MIT，Copyright (c) 2026 orange-clockwork；[根目錄](LICENSE)與[安裝包授權](skills/prior-scout/LICENSE)相同。
第三方名稱及材料權利屬原持有人。
