[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找一样的，先查证再下结论。**

Prior-Scout（先例探索）是一个仅包含指令的小型 Agent Skill，帮助你在开始开发前查找现有方案。
提供需求、网址或可读文档，它会搜索公开来源、核实相关功能，简要比较工具、服务、Skill、
库或研究实现的相似点和关键差异。

**`0.3.0-experimental` · 本地发布候选版 · MIT**

## 看实际案例

以下 Demo 早于 V03，保留为历史使用示例，不是本版本的验证。

以下整理自**用户报告的 Prior-Scout 执行观察**；当时整理案例时另外核对了原始来源。
这些场次的确切输入与原始执行记录尚未保存在此仓库，因此不是逐字重现或独立性能测试。

### Demo 01 — Prior-Scout 能找到自己的同类方案吗？

开发完成后，作者用 Prior-Scout 回头调查相似工作流。三个代表性候选：

- **[search-first](https://github.com/affaan-m/ECC/blob/main/skills/search-first/SKILL.md)：** 与“开发前先查现有成果”高度重叠，接着会做采用／扩展／自行开发判断并进入实现。
- **[priorart](https://github.com/duthaho/skillhub/blob/main/.claude/skills/priorart/SKILL.md)：** 与现有构想查找高度重叠，要求可定位的证据、有限搜索预算，以及自行开发／Fork／采用等结论。
- **[find-skills](https://github.com/vercel-labs/skills/blob/main/skills/find-skills/SKILL.md)：** 部分重叠；重点是寻找可安装的 Skill 并提供安装选项，范围不同于更广的相关成果比较。

**承认真实重叠，不制造原创性。** Prior-Scout 在简短、有证据的比较后停止调查，继续已授权
任务；这是范围选择，不是已证明的优势。这次回顾发生在开发之后，不能证明当初开发前做过
同样检查。[完整五个候选、报告预算与来源核实](docs/examples.md#demo-01-agent-skill-discovery)。

### Demo 02 — 为行人导航研究查找相关文献

作者计划中的硕士研究比较完整路线引导、方向与距离引导、仅显示目的地三种条件。
报告中的三篇研究，说明为什么不能只比较题目：

- **[Robinson 等人（2012）](https://cronfa.swansea.ac.uk/Record/cronfa17385/Download/0017385-18012016145442.pdf) — 全文：** 触觉方向提示与自主选路；并未比较上述三种研究条件。
- **[Sugimoto 等人（2022）](https://ist.ksc.kwansei.ac.jp/~nagata/data/sugimoto_2021_spat_cogn_comput.pdf) — 全文：** 手机／纸质地图与空间记忆；媒介差异不能单独归因于信息量。
- **[Heller 等人（2020）](https://www.krisluyten.net/publications/dblp_conf_mhci_helleral20/) — 仅摘要：** 声音导航、效率与工作负荷；此处未核实详细测量方式。

**主题相近，不等于实验条件或测量指标相同。** 硕士研究仍是提案，不是已发表结果，也未据此
判断新颖性。[详细比较](docs/examples.md#demo-02-pedestrian-navigation-research)将原始观察与本轮额外
核实的 Ishikawa & Takahashi（2014）分开呈现。

先前的 [Markdown 链接检查器 T2 案例](docs/examples.md#t2-markdown-link-checker)及其已保存的
审查记录仍完整保留。

## 安装与使用

此 checkout 基于冻结的 V03 准备 `0.3.0-experimental`，尚未发布。
GitHub 公开 `main` 仍提供 `0.2.0-experimental`（V01）。以下命令安装可能变动的
公开分支，不是此本地候选版；候选版请使用后面的本地安装命令。
历史安装和使用观察只适用于各记录标明的版本。

[Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 要求 Node.js 22.20 或更高版本；
宿主须支持 Agent Skills 加载、搜索和来源读取。请在目标项目中执行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

先确认没有同名 Skill；若出现范围选择，请选项目级，不要添加 `-g`。
安装位置为 `.agents/skills/prior-scout/`，包含 SKILL.md 和 MIT LICENSE。

在该项目中打开新的 Codex 会话，明确指定使用 Skill。
以下是调用示例，不是上方两个 Demo 的原始输入：

> 使用 $prior-scout，查找现有的开源 Markdown 链接检查器。
> 阅读可靠来源，简要说明已核实的相似点和关键差异。

<details>
<summary>先查看列表，以及明确指定复制安装</summary>

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

复制命令是主安装命令的另一种选择；执行前同样须确认目标项目中没有同名安装。

</details>

本地候选版请在另一个目标项目中安装，先确认没有同名 Skill。
将 `/path/to/release-checkout` 替换为位于 `codex/release-v0.3.0-experimental`
分支的 checkout 路径：

```sh
npx skills@1.7.4 add /path/to/release-checkout --skill prior-scout -a codex --copy -y
```

本次 smoke test 直接复用已有 Skills CLI 1.7.4，没有通过 npx 新下载工具。
验证范围是项目安装及文件可读；全新 Codex 原生加载、自动选用，以及此版本的在线安装
均为 **NOT RUN**。[验证记录](evals/releases/v0.3.0-experimental.md)。

## 工作流程

1. 确认需求、要比较的相似维度和必要条件。
2. 在有限预算内搜索：通常最多 **6 条查询、8 份外部证据文档**。
3. 逐项区分搜索线索、实际取得的一手来源内容，以及内容支持的结论，确认交付物、版本和服务套餐。
4. 简要说明有依据的相似点、关键差异和未知项，再继续其他已授权任务。

URL 或工具成功状态本身不代表已取得来源内容。“未报告”只表示已读材料未提及；
“未测量”须有来源明确说明。结果未知时仍保留有依据的方法上的部分相关性，不推定其效果。
读取失败时，在预算内尝试同作者可读版本或其他一手来源；仍无法取得时，只保留已有支持的
结论，其他线索标为未验证或省略。

搜索摘要只作为线索。API、计划中的功能和部分相似，不等于完整的内置功能。
预算是指令约束，不是程序强制保证。搜索和来源读取由宿主提供；Prior-Scout
不增加运行时依赖或遥测。无法取得证据时应说明限制，并优先遵守仅使用所提供资料的要求。

适合明确查找替代方案、相关成果，以及需要外部比较的新计划。普通修复、翻译和方案已定的
实现不需要因此开启新搜索。它不判断采用方案、创新性、法律地位或商业价值，不运行候选，
也不主动展开未要求的后续研究。详见[范围说明](docs/scope.md)。

## 证据与限制

- **V03 Evidence-Gated Workflow：** 区分线索、取得的内容和有支持的结论。已有的小规模 supplied-instruction 比较中，Codex Sol High：V01 **4/4 PASS**、V03 **4/4 PASS**；Gemini Flash Low：V01 **2/6 PASS**、V03 **4/6 PASS**。Gemini 的两个实时来源验证案例，两版均失败。案例已曝光、每条件只运行一次，且由协调者人工非盲评分，不能证明统计优越性、普遍兼容或生产级可靠性。[证据与验证](evals/releases/v0.3.0-experimental.md)。
- **本地封装验证：** 项目发现、复制安装及安装内容一致，与原生加载、行为表现分开记录。来源访问、能否确实依据证据限制结论，以及宿主工具支持仍有限制。[发布说明草稿](docs/release-notes-v0.3.0-experimental.md)。

- **历史 V01 / M1 安全基线：** 新增来源 URL 出处指引，证据包括有限安全基线、8 次原版／候选比较及 4 个最终正向控制。普通格式整理案例没有工具调用，原生选用仍为 INCONCLUSIVE。这不代表完全防止 Prompt Injection，也未测量错误率下降。Claude Code、Cursor 和 Gemini CLI 兼容性为 **NOT TESTED**。[候选审查](docs/release-checklist.md#m13-release-candidate-review--2026-10-23)

- **0.1.1 公开安装已验证：** 主安装和复制命令已在不同的全新项目中测试，核心与 LICENSE 均与公开来源逐字节一致。[发布检查](docs/release-checklist.md#public-release-verification-2026-10-22)
- **14 个案例的审查：** 包括 8 个质量任务和 6 个选用控制，使用新的子上下文，但仍共享宿主指令；不是完整独立盲测，也未取得完整初始提示和结构化加载器事件。[评测结果](evals/results.md)
- **分别记录宿主观察：** Mac 发布测试的新 Codex 会话仍为 NOT TESTED。后续 Windows 安装和使用是用户报告，这个仓库尚未保存 Windows 原始执行记录。[Windows 摘要和限制](docs/examples.md#windows-user-reported-observation)

这些观察不能证明准确率、找到所有相关成果、消除模型幻觉，或优于良好的普通 Codex 提示词
及其他 Skill。独立 A/B/C 比较、保留集评测、候选工具的实际运行、精确成本和跨宿主
可靠的自动选用仍未验证。直接安装成功也不保证 skills.sh 收录、`skills find` 搜索可见性
或 find-skills 推荐。

## 其他文档与许可

[发布说明草稿](docs/release-notes-v0.3.0-experimental.md) · [本地验证](evals/releases/v0.3.0-experimental.md)

[更多案例与原始记录](docs/examples.md) · [现有工作流比较](docs/comparison.md) ·
[评测方法](evals/README.md) · [M4 历史发布准备](docs/release-preparation.md)

英文为主要维护版本，翻译保留相同结论和限制。核心指令见 [SKILL.md](skills/prior-scout/SKILL.md)，
开发约束见 [AGENTS.md](AGENTS.md)。公开仓库不包含私有原始证据和原始开发 Git 历史。

MIT License。Copyright (c) 2026 orange-clockwork。[根目录 LICENSE](LICENSE) 和
[可安装副本](skills/prior-scout/LICENSE)条款一致。第三方名称与链接资料的权利仍归各权利人；
本项目不分发上游来源全文。
