[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找一樣的，先查證再下結論。**

Prior-Scout（先例探索）是一個只含指示的小型 Agent Skill。提供需求、網址或可讀文件，
它會從公開資料尋找用途相近的工具、服務、Skill、函式庫或研究實作，簡短說明有證據
支持的相似處與重要差異。它將既有成果查找整理成可重複、範圍有限的流程，完成後
接回你原本的工作。

**狀態：`0.1.1-experimental`，已在 GitHub 公開。** 2026-10-22 已驗證匿名存取，
以及從公開來源進行專案層級安裝。
現有證據包含實際讀取來源的 smoke test，以及 14 題使用新子上下文的子代理審查，
限制如下。這是聚焦流程的打包，尚未證明比良好的普通 Codex Prompt 或其他 Skill 更準確。

英文 README 是主要維護版本；各語言翻譯應維持相同的技術主張與限制。

## 從 GitHub 安裝

使用公開儲存庫 [orange-clockwork/prior-scout](https://github.com/orange-clockwork/prior-scout)。
[Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 需要 Node.js 22.20 以上版本。
請在目標專案中執行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

若要明確指定複製模式並略過互動提示：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

安裝前先確認目標專案沒有同名 Skill。若出現範圍選擇，請選專案層級，不要加上 `-g`。
安裝位置為 `.agents/skills/prior-scout/`；只安裝 `skills/prior-scout/`，包含 MIT LICENSE。

**PASS — 公開來源安裝：** 已透過 npx 與 Skills CLI 1.7.4，在兩個各自全新的臨時專案
實測上述兩種安裝命令。只發現一個 Skill，安裝後的 SKILL.md 與 LICENSE 均與公開版本
逐位元組一致。CLI 偵測到 Codex 環境，採用專案範圍與複製模式；其他環境的互動提示
沒有另行測試。詳見[發布驗證紀錄](docs/release-checklist.md#public-release-verification-2026-10-22)。
[M4 安裝紀錄](evals/runs/install-m4-20261022.md)保留為當時的本機來源測試紀錄。

**NOT TESTED — 使用此次公開安裝版本的新 Codex 原生會話。**
目前尚未確立能保護既有系統 Skill 快取的安全啟動條件。人工驗證時，請在安裝後的專案
開啟新的 Codex 對話，選取專案層級的 `prior-scout`，送出下方明確指定的使用範例。
確認所選路徑、實際指示取得、搜尋與來源讀取；僅手動讀取檔案不算結構化原生載入證據。

發布驗證當下，skills.sh 頁面顯示無法使用／404，`skills find prior-scout` 沒有結果。
find-skills 推薦及跨執行環境自動選用仍未驗證；索引收錄與 GitHub 直接安裝是不同項目，
不保證立即收錄。

## 使用方式

明確指定使用（此實驗版建議採用）：

> 使用 $prior-scout，尋找能檢查 Markdown 知識庫中失效連結、缺少附件與重複檔名的
> 現有開源工具。閱讀可靠來源，說明已核實的相似處與重要限制。

由執行環境選用 Skill 的自然請求範例：

> 有沒有和這個構想相似的既有工具或研究實作？請找幾個有來源支持的候選，
> 簡短說明重要差異。

需要外部對照的新規劃也可能適用。一般 Bug 修正、排版、摘要、翻譯、重構與已定案的
實作，不應因此啟動研究；使用者限定只用提供資料時，須優先遵守。回答語言跟隨使用者。
這些是示意輸入，不是自動觸發成功的測試紀錄。

## Evidence-First 核實原則與限制

預設上限為 6 個搜尋 query、8 份不同的外部證據文件，通常列出 3～5 個候選。
這是指示限制，不是程式強制保證。搜尋摘要只當線索；重要主張必須實際讀取來源成功，
並有直接證據支持。規劃中的功能與可整合 API 不等於已完成的工作流程。
部分相似不代表完全替代；一次搜尋沒找到，也不代表不存在。

回答前會核對主張與證據，修正、標為未核實或移除無依據的內容；不強制每個候選都有
兩份來源、數值分數或冗長檢查表。它無法保證找齊所有成果或完全消除模型幻覺。

## 主要功能

- 依目的、功能、方法與合適的同義詞搜尋。
- 閱讀可靠來源，區分「來源存在」與「來源支持這項主張」。
- 區分託管服務、可安裝應用程式、Skill、SDK、論文與 Demo。
- 確認功能屬於哪個交付物、版本或服務方案。
- 保留有依據的事實、標明未知，並在有限搜尋預算內停止。
- 比較完成後，接回使用者已授權的其他工作。

它不判定創新性、法律地位、研究價值、商業可行性或應該採用哪個方案，也不會自動
提出改善方向、執行候選工具或展開另一輪研究。反向搜圖、歌曲辨識、檔案去重與
完整文獻回顧不在支援範圍內。

## 執行環境需求

執行環境須能載入 Agent Skills，並提供搜尋與來源讀取工具；輸入文件也須能由該環境讀取。
Prior-Scout 本身不包含搜尋引擎、解析器、執行時相依套件、帳號、付費 API 整合或遙測。
來源或工具不可用時，應揭露限制，而非捏造已完成的查證。

## 實際範例與證據

- [軟體功能歸屬](evals/runs/evidence-regression-ef02-r1-20261022.md)：固定版本的
  套件 FAQ 不支持內建協作，但提供 API 讓應用程式自行實作；先前的讀取失敗紀錄仍保留。
- [研究系統](evals/runs/release-audit-20261022.md#q3)：區分行人導航方法、原研究
  實際評估的內容，以及應用程式的可取得性。
- [消費者工作流程](evals/runs/release-audit-20261022.md#q6)：區分貼上完整食譜後解析，
  與僅接受已整理好的食材欄位。

這些是實際記錄的輸出，不是潤飾後替換的答案，也不是候選工具的執行測試。
完整輸入、輸出、來源與限制見[範例](docs/examples.md)及[評測結果](evals/results.md)。

## 測試與結果

發布審查完成 14 題有範圍限制的案例：8 題品質任務與 6 題選用控制。
審查在這個樣本中未發現重要的無依據或虛構主張，但這不是正確率。
測試使用新的子上下文，仍共享執行環境指示，也沒有完整記錄模型最初看到的全部提示。
觀察到指示檔案被使用，不代表已證明頂層原生自動選用；結構化載入仍未確定。
獨立 A/B/C 比較、保留集評測、跨執行環境可靠性、搜尋候選工具的實際運作、精確成本，
以及相對於普通 Prompt 的品質優勢，都尚未驗證。

## 既有替代方案與專案定位

現成工作流程也會搜尋與核實來源。Prior-Scout 的取捨是聚焦於簡短比較與明確停止點，
不增加採用裁決或商業分析。請參閱[現成工作流程的文件比較](docs/comparison.md)。

## 授權與開發

採用 MIT License。Copyright (c) 2026 orange-clockwork。完整英文條款見 [LICENSE](LICENSE)，
[可安裝目錄中的副本](skills/prior-scout/LICENSE)具有相同聲明。第三方名稱與連結來源的
權利仍屬各權利人；本專案不散布上游來源全文。

核心為 [SKILL.md](skills/prior-scout/SKILL.md)。開發限制見 [AGENTS.md](AGENTS.md)，
評測方法限制見[評測說明](evals/README.md)。公開儲存庫不包含原始開發 Git 歷史或私人原始紀錄。
[發布準備報告](docs/release-preparation.md)保留 M4 當時的狀態；
目前發布驗證結果見[發布清單](docs/release-checklist.md)。
