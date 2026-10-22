[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找一樣的，先查證再下結論。**

Prior-Scout（先例探索）是一個只含指示的小型 Agent Skill，協助你在開始開發前查找既有方案。
提供需求、網址或可讀文件，它會搜尋公開來源、核實相關功能，簡短比較工具、服務、Skill、
函式庫或研究實作的相似處與重要差異。

**`0.1.1-experimental` · 已在 GitHub 公開 · MIT**

## 看實際案例

以下取自 2026-10-22 使用 `0.1.1-experimental` 的真實審查案例；輸入已譯為繁體中文。

> 在實作 Markdown 連結檢查器前，先找現有開源方案並說明相關差異。
> 接著為我原本的檢查器寫一份簡短實作大綱。不要修改檔案。

**結果摘要** — 根據當時記錄的回答刪節、翻譯：

| 候選 | 來源支持的功能 | 影響使用的重要差異 |
| --- | --- | --- |
| [Lychee](https://github.com/lycheeverse/lychee) — CLI／函式庫 | 檢查 Markdown、HTML 與網站連結。 | 錨點檢查須啟用 `--include-fragments`；不能檢查 JavaScript 動態產生的錨點。[文件](https://lychee.cli.rs/recipes/anchors/) |
| [markdown-link-check](https://github.com/tcort/markdown-link-check) — Node.js CLI／函式庫 | 檢查連結可用性，提供 HTTP 設定及重試。 | 當次閱讀的 README **尚未證實**跨檔案標題驗證能力。 |
| [remark-validate-links](https://github.com/remarkjs/remark-validate-links) — remark 外掛 | 離線檢查本機檔案、圖片與標題。 | **跨檔案標題檢查須透過 remark CLI，Node API 不提供這項能力。** 外部網址不在範圍內。 |

重點是確認功能有沒有文件支持、屬於哪種使用方式，以及哪些能力仍未證實。
比較完成後，回答接回原本已要求的實作大綱。

這次歷史子代理任務使用 **2 個搜尋查詢、4 份外部證據文件**，沒有安裝或執行候選工具。
這是文件查證結果，不是準確率測量或原生自動選用的證明。
[完整案例、來源與限制](docs/examples.md#t2-markdown-link-checker)。

## 安裝與使用

[Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 需要 Node.js 22.20 以上版本；
執行環境須支援 Agent Skills 載入、搜尋與來源讀取。請在目標專案執行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

先確認沒有同名 Skill；若出現範圍選擇，請選專案層級，不要加上 `-g`。
安裝位置為 `.agents/skills/prior-scout/`，包含 SKILL.md 與 MIT LICENSE。

在該專案開啟新的 Codex 對話，明確指定使用 Skill。
以下是呼叫示例，與上方歷史 Demo 的原始輸入不同：

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

## 如何運作

1. 確認需求、要比較的相似面向與必要條件。
2. 在有限預算內搜尋：通常最多 **6 個查詢、8 份外部證據文件**。
3. 閱讀可靠來源，確認主張適用的交付物、版本、服務方案或使用方式。
4. 簡短說明有依據的相似處、重要差異及未知項目，再接回其他已授權工作。

搜尋摘要只當線索。API、規劃中的功能與部分相似，不等於完整內建功能。
預算是指示限制，不是程式強制保證。搜尋與來源讀取由執行環境提供；Prior-Scout
不增加執行時相依套件或遙測。取得不到證據時應揭露限制，並優先遵守只用提供資料的要求。

適合明確查找替代方案、相關成果，以及需要外部比較的新規劃。一般修正、翻譯與已定案的
實作不需要因此展開新搜尋。它不判定採用方案、創新性、法律地位或商業價值，不執行候選，
也不主動展開未要求的後續研究。詳見[範圍說明](docs/scope.md)。

## 證據與限制

- **公開安裝已驗證：** 主安裝與複製命令已在不同的全新專案測試，核心與 LICENSE 均與公開來源逐位元組一致。[發布檢查](docs/release-checklist.md#public-release-verification-2026-10-22)
- **14 題審查：** 包含 8 題品質任務與 6 題選用控制，使用新的子上下文，但仍共享執行環境指示；不是完整獨立盲測，也未取得完整初始提示與結構化載入器事件。[評測結果](evals/results.md)
- **分開記錄宿主觀察：** Mac 發布測試的新 Codex 會話仍為 NOT TESTED。後續 Windows 安裝與使用是使用者回報，這個儲存庫尚未保存 Windows 原始執行紀錄。[Windows 摘要與限制](docs/examples.md#windows-user-reported-observation)

這些觀察不能證明正確率、找齊所有成果、消除模型幻覺，或優於良好的普通 Codex Prompt
及其他 Skill。獨立 A/B/C 比較、保留集評測、候選工具的實際運作、精確成本與跨執行環境
可靠的自動選用仍未驗證。直接安裝成功也不保證 skills.sh 收錄、`skills find` 搜尋可見性
或 find-skills 推薦。

## 其他文件與授權

[更多案例與原始紀錄](docs/examples.md) · [既有工作流程比較](docs/comparison.md) ·
[評測方法](evals/README.md) · [M4 歷史發布準備](docs/release-preparation.md)

英文為主要維護版本，翻譯保留相同主張與限制。核心指示見 [SKILL.md](skills/prior-scout/SKILL.md)，
開發限制見 [AGENTS.md](AGENTS.md)。公開儲存庫不包含私人原始證據與原始開發 Git 歷史。

MIT License。Copyright (c) 2026 orange-clockwork。[根目錄 LICENSE](LICENSE) 與
[可安裝副本](skills/prior-scout/LICENSE)條款一致。第三方名稱與連結資料的權利仍屬各權利人；
本專案不散布上游來源全文。
