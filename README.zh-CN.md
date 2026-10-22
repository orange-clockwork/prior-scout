[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找一样的，先查证再下结论。**

Prior-Scout（先例探索）是一个仅包含指令的小型 Agent Skill，帮助你在开始开发前查找现有方案。
提供需求、网址或可读文档，它会搜索公开来源、核实相关功能，简要比较工具、服务、Skill、
库或研究实现的相似点和关键差异。

**`0.1.1-experimental` · 已在 GitHub 公开 · MIT**

## 看实际案例

以下取自 2026-10-22 使用 `0.1.1-experimental` 的真实审查案例；输入已译为简体中文。

> 在实现 Markdown 链接检查器前，先查找现有开源方案并说明相关差异。
> 接着为我原本的检查器写一份简短实现大纲。不要修改文件。

**结果摘要** — 根据当时记录的回答删节、翻译：

| 候选 | 来源支持的功能 | 影响使用的关键差异 |
| --- | --- | --- |
| [Lychee](https://github.com/lycheeverse/lychee) — CLI／库 | 检查 Markdown、HTML 和网站链接。 | 锚点检查须启用 `--include-fragments`；不能检查 JavaScript 动态生成的锚点。[文档](https://lychee.cli.rs/recipes/anchors/) |
| [markdown-link-check](https://github.com/tcort/markdown-link-check) — Node.js CLI／库 | 检查链接可用性，提供 HTTP 设置和重试。 | 当次阅读的 README **尚未证实**跨文件标题验证能力。 |
| [remark-validate-links](https://github.com/remarkjs/remark-validate-links) — remark 插件 | 离线检查本地文件、图片和标题。 | **跨文件标题检查须通过 remark CLI，Node API 不提供这项能力。** 外部网址不在范围内。 |

重点是确认功能有没有文档支持、属于哪种使用方式，以及哪些能力仍未证实。
比较完成后，回答继续处理原本要求的实现大纲。

这次历史子代理任务使用 **2 条搜索查询、4 份外部证据文档**，没有安装或运行候选工具。
这是文档核实结果，不是准确率测量或原生自动选用的证明。
[完整案例、来源和限制](docs/examples.md#t2-markdown-link-checker)。

## 安装与使用

[Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 要求 Node.js 22.20 或更高版本；
宿主须支持 Agent Skills 加载、搜索和来源读取。请在目标项目中执行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

先确认没有同名 Skill；若出现范围选择，请选项目级，不要添加 `-g`。
安装位置为 `.agents/skills/prior-scout/`，包含 SKILL.md 和 MIT LICENSE。

在该项目中打开新的 Codex 会话，明确指定使用 Skill。
以下是调用示例，与上方历史 Demo 的原始输入不同：

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

## 工作流程

1. 确认需求、要比较的相似维度和必要条件。
2. 在有限预算内搜索：通常最多 **6 条查询、8 份外部证据文档**。
3. 阅读可靠来源，确认结论适用的交付物、版本、服务套餐或使用方式。
4. 简要说明有依据的相似点、关键差异和未知项，再继续其他已授权任务。

搜索摘要只作为线索。API、计划中的功能和部分相似，不等于完整的内置功能。
预算是指令约束，不是程序强制保证。搜索和来源读取由宿主提供；Prior-Scout
不增加运行时依赖或遥测。无法取得证据时应说明限制，并优先遵守仅使用所提供资料的要求。

适合明确查找替代方案、相关成果，以及需要外部比较的新计划。普通修复、翻译和方案已定的
实现不需要因此开启新搜索。它不判断采用方案、创新性、法律地位或商业价值，不运行候选，
也不主动展开未要求的后续研究。详见[范围说明](docs/scope.md)。

## 证据与限制

- **公开安装已验证：** 主安装和复制命令已在不同的全新项目中测试，核心与 LICENSE 均与公开来源逐字节一致。[发布检查](docs/release-checklist.md#public-release-verification-2026-10-22)
- **14 个案例的审查：** 包括 8 个质量任务和 6 个选用控制，使用新的子上下文，但仍共享宿主指令；不是完整独立盲测，也未取得完整初始提示和结构化加载器事件。[评测结果](evals/results.md)
- **分别记录宿主观察：** Mac 发布测试的新 Codex 会话仍为 NOT TESTED。后续 Windows 安装和使用是用户报告，这个仓库尚未保存 Windows 原始执行记录。[Windows 摘要和限制](docs/examples.md#windows-user-reported-observation)

这些观察不能证明准确率、找到所有相关成果、消除模型幻觉，或优于良好的普通 Codex 提示词
及其他 Skill。独立 A/B/C 比较、保留集评测、候选工具的实际运行、精确成本和跨宿主
可靠的自动选用仍未验证。直接安装成功也不保证 skills.sh 收录、`skills find` 搜索可见性
或 find-skills 推荐。

## 其他文档与许可

[更多案例与原始记录](docs/examples.md) · [现有工作流比较](docs/comparison.md) ·
[评测方法](evals/README.md) · [M4 历史发布准备](docs/release-preparation.md)

英文为主要维护版本，翻译保留相同结论和限制。核心指令见 [SKILL.md](skills/prior-scout/SKILL.md)，
开发约束见 [AGENTS.md](AGENTS.md)。公开仓库不包含私有原始证据和原始开发 Git 历史。

MIT License。Copyright (c) 2026 orange-clockwork。[根目录 LICENSE](LICENSE) 和
[可安装副本](skills/prior-scout/LICENSE)条款一致。第三方名称与链接资料的权利仍归各权利人；
本项目不分发上游来源全文。
