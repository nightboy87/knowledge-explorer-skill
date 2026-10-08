# Knowledge Explorer Skill · 知识探索者

![Knowledge Explorer 中文介绍](assets/readme-hero-zh.png)

> 像和导师讨论一样学习知识，也能让 Agent 在需要时生成可视化、可交互的学习工具。

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) ![Version](https://img.shields.io/badge/version-0.1.1-blue) ![Agent Skills](https://img.shields.io/badge/Agent-Skills-blueviolet) ![Status](https://img.shields.io/badge/status-early%20release-orange)

**Knowledge Explorer Skill** 是面向普通 Agent 用户的开源学习技能包。你可以直接提问、提供文章或文档，让 Agent 用适合你的方式解释知识。当文字难以讲清复杂机制时，Agent 还可以按需创建图解、分步演示或交互式 HTML 学习页面。

它把**对话式知识导师**和**交互式知识探索器**结合起来：可以先讲清楚，再通过操作、观察和追问进一步理解。

🌐 语言：[English](README.en.md) · **简体中文**

## 你能用它做什么？

- **通过对话学习：** 理解新概念、技术原理、实验方法或论文中的关键观点。
- **把抽象知识变直观：** 根据内容选择关系图、步骤图、对比表、动画或交互实验。
- **主动探索：** 在适合的场景下调整参数、逐步查看变化，而不只是阅读解释。
- **接着问下去：** 针对刚才的解释或演示继续提问，必要时修改已有学习页面。
- **检查理解：** 用具体例子、反例或简短测验确认是否理解关键知识。

> Skill 不会为每个问题都生成网页。简单问题优先直接回答，只有可视化或交互能带来帮助时才使用。

## 使用示例

**学一个概念**

```text
用 Knowledge Explorer 给我讲明白什么是 RAG，最好用生活中的例子。
```

**看懂复杂机制**

```text
我想学懂反向传播。请用交互式演示说明误差如何传递，
并让我调整学习率观察变化。
```

**阅读文献**

```text
用 Knowledge Explorer 帮我读懂这篇论文。
先讲研究问题和关键结论，再解释我没理解的实验方法。
```

**连续追问**

```text
刚才第二步我还不明白，换个例子讲一遍。
如果可以，请修改那个演示，让我更容易看出区别。
```

## 如何工作

1. **理解你想学什么。** 结合当前问题和你提供的材料，找到最重要的理解目标。
2. **先用容易理解的语言解释。** 必要时通过例子和逐层深入的讲解建立基础。
3. **选择最合适的学习形式。** 根据知识特点决定是否需要关系图、过程演示、交互页面或对比视图。
4. **支持继续探索。** 通过追问、调整演示或简单的理解问题，把学习推进下去。

当宿主 Agent 支持文件创建和代码执行时，可以生成**可离线打开的单文件 HTML**。实际可用的文件读取、网页生成和测试功能取决于 Agent 的运行环境。

## 安装

本项目遵循 [Agent Skills 开放规范](https://agentskills.io/specification)。请安装**整个项目目录**，保持 `SKILL.md`、`references/` 和 `assets/` 的相对位置不变。

### Codex

```bash
git clone https://github.com/nightboy87/knowledge-explorer-skill.git ~/.codex/skills/knowledge-explorer
```

### Claude Code

```bash
git clone https://github.com/nightboy87/knowledge-explorer-skill.git ~/.claude/skills/knowledge-explorer
```

### 其他兼容 Agent

将仓库放入宿主支持的 Skills 目录，并确认宿主可以读取 `SKILL.md` 及其引用的文件。具体路径、Skill 发现方式以及运行权限以宿主的官方文档为准。

Windows 用户可以使用 Git for Windows 或手动下载仓库 ZIP，解压到相应的 Skills 目录。

## 项目结构

```text
knowledge-explorer-skill/
├── SKILL.md
├── README.md
├── README.en.md
├── LICENSE
├── references/
│   ├── teaching-guidelines.md
│   └── visualization-guidelines.md
└── assets/
    ├── html-template.html
    ├── readme-hero-zh.png
    └── readme-hero-en.png
```

- `SKILL.md`：Skill 入口、触发条件和核心教学行为。
- `references/teaching-guidelines.md`：讲解深度、教学示例、持续追问和反馈。
- `references/visualization-guidelines.md`：图解与交互形式选择、真实性和可用性要求。
- `assets/html-template.html`：可离线运行的学习页面基础模板，包含**示例内容**；Agent 交付具体学习页面时必须替换与主题无关的示例。

## 使用边界

- **不是独立软件。** 它通过你使用的 Agent 运行，不自带聊天服务、账户系统或长期学习档案。
- **不强制生成 HTML。** 对话讲解、普通图表往往足以解决简单问题。
- **不会伪造仿真。** 只有拥有明确计算规则的主题才应生成真实可调参数的计算演示；概念示意会清楚注明。
- **尊重原始资料。** 论文、数据和文档中的重要数字及观点应保留条件与来源；看不到的内容不会被臆测。
- **能力取决于宿主。** 是否能读取 PDF、写文件或运行浏览器测试，取决于 Agent 的工具和权限。

## 当前版本

**v0.1.1 — 早期版本**。已包含 Skill 行为规范、教学与可视化指南，以及带示例内容的独立 HTML 模板。尚未宣称完成跨 Agent 端到端兼容性验证。

欢迎通过 [Issues](https://github.com/nightboy87/knowledge-explorer-skill/issues) 反馈使用问题、教学示例和功能建议。

## 许可证

基于 [MIT License](LICENSE) 开源。
