[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找出已有成果，查证后再下结论。**

Prior-Scout 是一个小型 Agent Skill，帮助 AI agent 查找相似的软件、库、工具、
Agent Skills 和研究。它阅读原始资料、确认重要功能，再简要比较相似之处、差异和尚未明确的部分。

它由指令组成，使用 agent 已有的搜索和来源读取工具，并非独立的搜索引擎或研究服务。

## 何时使用

开发新功能前想找找现成的开源工具、寻找能处理特定任务的 Skill，或根据原始论文比较研究方法时，
都可以使用。日常修复和已有明确计划的实现，不需要因此重新搜索。

## 安装

在要使用的项目目录中执行以下 Codex 安装命令，需要 Node.js 22.20 及以上版本和 npm：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

这会将 `main` 的 Skill 复制到项目的 `.agents/skills/prior-scout/`。执行前先确认是否已经安装。
如需跨项目使用，添加 `--global`。

如需固定使用 v1.0.0，将 `orange-clockwork/prior-scout` 替换为
`https://github.com/orange-clockwork/prior-scout/tree/v1.0.0`。
请检查安装后的文件；可能需要开启新的 agent 会话才能加载。

## 使用

在 Codex 中可以直接指定 Skill：

> 使用 $prior-scout，在我开发 Markdown 链接检查工具前，先找找现有的开源工具。
> 根据文档比较它们对本地文件和标题链接的支持，再为我的工具拟定实现计划。

是否自动调用取决于运行环境和模型。

## 工作方式

Prior-Scout 找出相关候选，阅读官方文档、仓库或论文等第一手资料，
比较有来源支持的功能并附上链接。已发布功能、计划中的功能和未知项会分开说明。
搜索结果和摘要只作为线索，不算第一手查证。

默认最多使用六个搜索查询和八份不同的外部文档。这些是指令中的限制，没有代码强制执行。

是否采用由你决定，它不会安装候选工具。如果你还要求了后续工作，agent 会回到原本的任务范围。

## 限制

运行环境必须提供搜索和来源读取工具。搜索范围取决于工具和可访问的资料，
无法保证找到所有成果，也可能漏掉更相近的方案。读过文档不代表已确认工具的实际运行情况。

已测试的配置为 macOS 26.4.1 arm64 上的 Codex CLI 0.164.0 搭配 gpt-6.1-sol/high。
其他运行环境的原生支持尚未验证，详见[兼容性记录](docs/compatibility.md)。

## 文档和许可

[Skill 指令](skills/prior-scout/SKILL.md) · [安全说明](SECURITY.md) ·
[v1.0 评估](evals/releases/v1.0.0.md) · [评估方法](evals/README.md) ·
[历史案例](docs/examples.md) · [发布说明](docs/release-notes-v1.0.0.md) ·
[更新记录](CHANGELOG.md)

英文为主要维护版本。采用 [MIT 许可证](LICENSE)。
