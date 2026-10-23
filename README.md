# grill-me

grill-me 是一个 Agent Skill。它引导 Agent 主动质疑方案的前提、必要性、合理性与可行性，按决策之间的依赖关系分轮提问，并为每个问题提供有理由的推荐答案。最终决策由你做出，方案在你确认后才进入实施。

## 主要改进

本项目基于 [Matt Pocock 的 grill-me](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) 进行改进，重点优化以下行为：

- **主动质疑方案**：不仅澄清需求，还会主动审视前提假设、潜在风险、不必要的复杂性及替代方案。
- **优先使用内置提问工具**：工具可用且合适时，通过交互式提问卡片展示问题；否则使用统一的纯文本格式。
- **按需调用子 Agent**：简单事实直接通过上下文或工具查明，复杂调查才在适当情况下委派子 Agent，减少不必要的调用。调查期间继续讨论不受影响的问题。

## 安装

### 使用 Skills CLI

使用 [Skills CLI](https://github.com/vercel-labs/skills) 安装，需要 Node.js 22.20 或更高版本。在目标项目目录中运行：

```sh
npx skills add shixhen/grill-me --skill grill-me
```

### 一句话安装

将下面这句话发送给你的 Agent：

```text
请帮我安装 GitHub 仓库 https://github.com/shixhen/grill-me 中的 `grill-me` Agent Skill。按照当前 Agent 环境的规范完成安装。安装完成后，验证技能是否能够被正确识别和加载。
```

## 文件说明

- [SKILL.md](./SKILL.md)：英文技能定义，供 Agent 加载。
- [SKILL-zh.md](./SKILL-zh.md)：仅供阅读与维护的中文译文，安装时使用 `SKILL.md`。