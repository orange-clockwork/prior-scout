[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**找出已有成果，查证后再下结论。**

轻量、仅含指示的 Agent Skill，帮助查找已有软件、库、Agent Skills 和研究。
阅读第一手来源，区分有依据的主张与未验证线索，简短说明重要差异，然后继续原本已授权的工作。

**1.0.0 · MIT · 已验证范围：Codex**

## 安装

Skills CLI 1.7.4 需要 Node.js 22.20 及以上版本和 npm；host 需提供文件／来源阅读及实时研究所需的搜索工具。
在没有同名 Skill 的项目中执行：

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

如需固定版本，将来源改成
`https://github.com/orange-clockwork/prior-scout/tree/v1.0.0`。
检查安装内容后开启新的 agent session。
`npx skills@1.7.4 remove prior-scout -a codex -y` 移除该项目安装；只有需要全局安装才加 `--global`。

## 使用与触发

> 使用 $prior-scout 查找已有开源 Markdown 链接检查工具，阅读第一手文档，
> 比较有依据的功能与限制，再为我的功能起草三步实现计划。

也适用于明确的替代方案、先例、相关研究，以及需要外部比较的新设计。
例如：“设计离线图片功能前先比较已有库”、“比较研究方法并区分实际测量结果与未知”、
“比较后继续已授权的有限实现”、“只比较，不提供采用建议”。自动选择仍取决于 host 和模型。
普通调试、排版、重构、翻译、文档清理和已定案的直接实现应直接处理。

## 工作方式与边界

1. 明确需求、限制和剩余已授权工作。
2. 默认最多六个搜索字符串、八份不同外部证据文档；失败及批次内每个 query 都计数。
3. 实际获取第一手内容后，才提出其能支持的具体主张。网址、snippet、空页或成功状态码都不足。
4. 简短列出来源、交付形式、版本条件和未知，然后返回原本已授权工作。

已发布功能、计划和集成可能性分开；hosted 服务不等于库，API 不等于完整内置流程。
“未报告”不等于“未测量”或“不存在”。方法部分相关不代表证实未报告的研究效果。
读取失败时可在预算内寻找同作者或其他第一手来源，无法获取的部分保持未验证。

Skill 没有 runtime、依赖、遥测、搜索服务或 API key；工具和权限由 host 提供。
预算和信任边界是指示，没有程序强制保证。它不授权安装、私人文件读取、上传、
全局配置修改、发布或未要求的采用、商业和法律新颖性判断。

## 支持与证据限制

[v1.0 评估记录](evals/releases/v1.0.0.md)分别记录版本、案例、原生发现、完整加载、
实际来源获取、行为和 baseline 比较；正式 Stable 须通过所有发布门槛。
Codex 是主要验证 host；其他 agent 的支持仅限于[兼容性表](docs/compatibility.md)中的实测。
不宣称通用准确率、安全性、完整检索或相对 baseline 的统计优势。

外部来源可能包含恶意指示；Skill 将其视为数据并保留用户授权边界，仍需 host 沙箱和有限权限。
见[安全限制](SECURITY.md)。历史 V03 的 Snyk 只报告 Low 第三方内容暴露指标 100/1000，
不是 v1.0 认证或抗注入保证。
GitHub 发布和 CLI 安装不保证 [skills.sh](https://skills.sh/orange-clockwork/prior-scout/prior-scout)
立即更新索引；重装或遥测不是保证强制更新的方法。

[核心指示](skills/prior-scout/SKILL.md) · [变更记录](CHANGELOG.md) ·
[历史案例](docs/examples.md) · [发布说明](docs/release-notes-v1.0.0.md)

英文为主要维护版本；翻译保留相同主张和限制。不分发私有 traces 或第三方来源快照。
MIT，Copyright (c) 2026 orange-clockwork；[根目录](LICENSE)和[安装包许可](skills/prior-scout/LICENSE)相同。
第三方名称及材料权利属于原持有人。
