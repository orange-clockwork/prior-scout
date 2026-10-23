[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找一樣的，先查證再下結論。**

Prior-Scout（先例探索）是一個只含指示的小型 Agent Skill，協助你在開始開發前查找既有方案。
提供需求、網址或可讀文件，它會搜尋公開來源、核實相關功能，簡短比較工具、服務、Skill、
函式庫或研究實作的相似處與重要差異。

**`0.3.0-experimental` · 實驗版 · MIT**

## 看實際案例

以下 Demo 早於 V03，保留為歷史使用例，不是本版本的驗證。

以下整理自**使用者回報的 Prior-Scout 執行觀察**；當時整理案例時另行核對原始來源。
這些場次的確切輸入與原始執行紀錄尚未保存在此儲存庫，因此不是逐字重現或獨立效能測試。

### Demo 01 — Prior-Scout 能找到自己的同類方案嗎？

開發完成後，作者用 Prior-Scout 回頭調查相似工作流程。三個代表性候選：

- **[search-first](https://github.com/affaan-m/ECC/blob/main/skills/search-first/SKILL.md)：** 與「開發前先查既有成果」高度重疊，接著會做採用／擴充／自行開發判斷並進入實作。
- **[priorart](https://github.com/duthaho/skillhub/blob/main/.claude/skills/priorart/SKILL.md)：** 與既有構想查找高度重疊，要求可定位的證據、有限搜尋預算，以及自行開發／Fork／採用等結論。
- **[find-skills](https://github.com/vercel-labs/skills/blob/main/skills/find-skills/SKILL.md)：** 部分重疊；重點是尋找可安裝的 Skill 並提供安裝選項，範圍不同於較廣的相關成果比較。

**承認真實重疊，不製造原創性。** Prior-Scout 在簡短、有證據的比較後停止調查，接回已授權
工作；這是範圍選擇，不是已證明的優勢。這次回顧發生在開發之後，不能證明當初開發前做過
同樣檢查。[完整五個候選、回報預算與來源查證](docs/examples.md#demo-01-agent-skill-discovery)。

### Demo 02 — 為行人導航研究查找相關文獻

作者規劃中的碩士研究比較完整路線引導、方向與距離引導、僅顯示目的地三種條件。
回報中的三篇研究，說明為什麼不能只比較題目：

- **[Robinson 等人（2012）](https://cronfa.swansea.ac.uk/Record/cronfa17385/Download/0017385-18012016145442.pdf) — 全文：** 觸覺方向提示與自主選路；並未比較上述三種研究條件。
- **[Sugimoto 等人（2022）](https://ist.ksc.kwansei.ac.jp/~nagata/data/sugimoto_2021_spat_cogn_comput.pdf) — 全文：** 手機／紙本地圖與空間記憶；媒介差異不能單獨歸因於資訊量。
- **[Heller 等人（2020）](https://www.krisluyten.net/publications/dblp_conf_mhci_helleral20/) — 僅摘要：** 聲音導航、效率與工作負荷；此處未核實詳細測量方式。

**主題相近，不等於實驗條件或測量指標相同。** 碩士研究仍是提案，不是已發表結果，也未據此
判定新穎性。[詳細比較](docs/examples.md#demo-02-pedestrian-navigation-research)將原始觀察與本輪額外
查證的 Ishikawa & Takahashi（2014）分開呈現。

先前的 [Markdown 連結檢查器 T2 案例](docs/examples.md#t2-markdown-link-checker)及其已保存
審查紀錄仍完整保留。

## 安裝與使用

以下指令安裝 GitHub 公開 `main`，內容可能在發布後更新。
固定版本的發布為 [v0.3.0-experimental](https://github.com/orange-clockwork/prior-scout/releases/tag/v0.3.0-experimental)，
採用凍結的 V03 Evidence-Gated Workflow。安裝與使用證據只適用於各紀錄的版本及驗證範圍。

[Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 需要 Node.js 22.20 以上版本；
執行環境須支援 Agent Skills 載入、搜尋與來源讀取。請在目標專案執行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

先確認沒有同名 Skill；若出現範圍選擇，請選專案層級，不要加上 `-g`。
安裝位置為 `.agents/skills/prior-scout/`，包含 SKILL.md 與 MIT LICENSE。

在該專案開啟新的 Codex 對話，明確指定使用 Skill。
以下是呼叫示例，不是上方兩個 Demo 的原始輸入：

> 使用 $prior-scout，尋找現有的開源 Markdown 連結檢查器。
> 閱讀可靠來源，簡短說明已核實的相似處與重要差異。

<details>
<summary>先查看清單，以及明確指定複製安裝</summary>

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

複製命令是主安裝命令的另一種選擇；執行前同樣須確認目標專案沒有同名安裝。

</details>

從本地發布 checkout 安裝時，也請在另一個目標專案操作，先確認沒有同名 Skill。
將 `/path/to/release-checkout` 換成位於 `codex/release-v0.3.0-experimental`
分支的 checkout 路徑：

```sh
npx skills@1.7.4 add /path/to/release-checkout --skill prior-scout -a codex --copy -y
```

準備階段的 smoke test 直接沿用既有 Skills CLI 1.7.4，沒有透過 npx 新下載工具，
驗證了專案安裝及檔案可讀。該檢查點的全新 Codex 原生載入、自動選用及此版本線上安裝
皆為 **NOT RUN**。發布時另行驗證公開檔案及全新專案安裝；兩者均不代表原生使用通過。
[準備階段紀錄](evals/releases/v0.3.0-experimental.md)。

## 如何運作

1. 確認需求、要比較的相似面向與必要條件。
2. 在有限預算內搜尋：通常最多 **6 個查詢、8 份外部證據文件**。
3. 逐項區分搜尋線索、實際取得的一手來源內容，以及內容支持的主張，確認交付物、版本與服務方案。
4. 簡短說明有依據的相似處、重要差異及未知項目，再接回其他已授權工作。

URL 或工具成功狀態本身不代表已取得來源內容。「未報告」只表示已讀資料未提及；
「未測量」須有來源明確說明。結果未知時仍保留有依據的方法上部分相關性，不推定其成效。
讀取失敗時，在預算內嘗試同作者可讀版本或其他一手來源；仍無法取得時，只保留已有支持的
主張，其他線索標成未驗證或省略。

搜尋摘要只當線索。API、規劃中的功能與部分相似，不等於完整內建功能。
預算是指示限制，不是程式強制保證。搜尋與來源讀取由執行環境提供；Prior-Scout
不增加執行時相依套件或遙測。取得不到證據時應揭露限制，並優先遵守只用提供資料的要求。

適合明確查找替代方案、相關成果，以及需要外部比較的新規劃。一般修正、翻譯與已定案的
實作不需要因此展開新搜尋。它不判定採用方案、創新性、法律地位或商業價值，不執行候選，
也不主動展開未要求的後續研究。詳見[範圍說明](docs/scope.md)。

## 證據與限制

- **V03 Evidence-Gated Workflow：** 區分線索、取得的內容與有支持的主張。既有小規模 supplied-instruction 比較中，Codex Sol High：V01 **4/4 PASS**、V03 **4/4 PASS**；Gemini Flash Low：V01 **2/6 PASS**、V03 **4/6 PASS**。Gemini 的兩個即時來源驗證案例，兩版均失敗。案例已曝光、每條件只跑一次，且由協調者人工非盲評分，不能證明統計優越性、普遍相容或正式環境可靠度。[證據與驗證](evals/releases/v0.3.0-experimental.md)。
- **本地封裝驗證：** 專案探索、複製安裝及安裝內容一致，與原生載入、行為表現分開記錄。來源存取、能否確實依證據限制主張，以及宿主工具支援仍有限制。[發布說明](docs/release-notes-v0.3.0-experimental.md)。

- **歷史 V01 / M1 安全基線：** 新增來源 URL 出處指引，證據包含有限安全基線、8 次原版／候選比較及 4 個最終正向控制。一般格式整理案例沒有工具呼叫，原生選用仍為 INCONCLUSIVE。這不代表完全防止 Prompt Injection，也未量測錯誤率下降。Claude Code、Cursor 與 Gemini CLI 相容性為 **NOT TESTED**。[候選審查](docs/release-checklist.md#m13-release-candidate-review--2026-10-23)

- **0.1.1 公開安裝已驗證：** 主安裝與複製命令已在不同的全新專案測試，核心與 LICENSE 均與公開來源逐位元組一致。[發布檢查](docs/release-checklist.md#public-release-verification-2026-10-22)
- **14 題審查：** 包含 8 題品質任務與 6 題選用控制，使用新的子上下文，但仍共享執行環境指示；不是完整獨立盲測，也未取得完整初始提示與結構化載入器事件。[評測結果](evals/results.md)
- **分開記錄宿主觀察：** Mac 發布測試的新 Codex 會話仍為 NOT TESTED。後續 Windows 安裝與使用是使用者回報，這個儲存庫尚未保存 Windows 原始執行紀錄。[Windows 摘要與限制](docs/examples.md#windows-user-reported-observation)

這些觀察不能證明正確率、找齊所有成果、消除模型幻覺，或優於良好的普通 Codex Prompt
及其他 Skill。獨立 A/B/C 比較、保留集評測、候選工具的實際運作、精確成本與跨執行環境
可靠的自動選用仍未驗證。直接安裝成功也不保證 skills.sh 收錄、`skills find` 搜尋可見性
或 find-skills 推薦。

## 其他文件與授權

[發布說明](docs/release-notes-v0.3.0-experimental.md) · [本地驗證](evals/releases/v0.3.0-experimental.md)

[更多案例與原始紀錄](docs/examples.md) · [既有工作流程比較](docs/comparison.md) ·
[評測方法](evals/README.md) · [M4 歷史發布準備](docs/release-preparation.md)

英文為主要維護版本，翻譯保留相同主張與限制。核心指示見 [SKILL.md](skills/prior-scout/SKILL.md)，
開發限制見 [AGENTS.md](AGENTS.md)。公開儲存庫不包含私人原始證據與原始開發 Git 歷史。

MIT License。Copyright (c) 2026 orange-clockwork。[根目錄 LICENSE](LICENSE) 與
[可安裝副本](skills/prior-scout/LICENSE)條款一致。第三方名稱與連結資料的權利仍屬各權利人；
本專案不散布上游來源全文。
