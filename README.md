# grill-me

grill-me 是一个 Agent Skill。它引导 Agent 主动质疑方案的前提、必要性、合理性与可行性，按决策之间的依赖关系分轮提问，并为每个问题提供有理由的推荐答案。最终决策由你做出，方案在你确认后才进入实施。

## 主要改进

本项目基于 [Matt Pocock 的 grill-me](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) 进行改进，重点优化以下行为：

- **优先使用内置提问工具**：工具可用时，通过交互式提问卡片展示问题；否则使用统一的纯文本格式。
- **按需调用子 Agent**：简单事实直接通过上下文或工具查明，复杂调查才在必要时委派子 Agent，减少不必要的调用。调查期间继续讨论不受影响的问题。

## 安装

本仓库的根目录 `SKILL.md` 结构符合 [Skills CLI 的技能发现规则](https://github.com/vercel-labs/skills/blob/main/docs/creating-skills.md#skill-discovery)。使用远程安装命令前，请先将 `SKILL.md` 提交并推送到仓库默认分支。

使用 [Skills CLI](https://github.com/vercel-labs/skills) 安装，需要 Node.js 22.20 或更高版本。在目标项目目录中运行：

```sh
npx skills add shixhen/grill-me --skill grill-me
```

按提示选择要安装到的 Agent。默认安装到当前项目；如需跨项目使用，可在命令末尾添加 `-g`：

```sh
npx skills add shixhen/grill-me --skill grill-me -g
```

## 文件说明

- [SKILL.md](./SKILL.md)：英文技能定义，供 Agent 加载。
- [SKILL-zh.md](./SKILL-zh.md)：中文版本，方便阅读与维护。
