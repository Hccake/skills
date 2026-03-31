# AI 编程助手 Skills

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> [🇬🇧 English](README.md)

一份可复用的 AI 编程助手 skill 集合。每个 skill 是一个结构化的工作流，通过 `SKILL.md` 文件定义，告诉 AI 助手如何处理特定类型的任务。

## Skills 列表

| Skill | 描述 |
|-------|------|
| [quick-brainstorm](quick-brainstorm/SKILL.md) | 小任务实施前的针对性 Q&A——bug 修复、小功能、重构。确保动手前思路清晰。 |
| [tech-writing](tech-writing/skill.md) | 规划、撰写和修订中文专业技术内容，强调证据支撑和教学结构。 |

## 快速开始

### 方式一：Skill Deck（图形界面）

使用 [Skill Deck](https://github.com/Hccake/skill-deck) 可视化管理 skill——一个用于浏览、安装和组织 AI 编程助手 skill 的桌面应用。

### 方式二：CLI

通过 [skills CLI](https://www.npmjs.com/package/skills) 安装：

```bash
npx skills add hccake/skills
```

或安装指定的 skill：

```bash
npx skills add hccake/skills
```

### 使用

然后在对话中使用：

```
修复登录超时的 bug。使用 quick-brainstorm skill。
```

## Skill 格式

每个 skill 放在独立目录中，包含一个 `SKILL.md` 文件：

```
<skill-name>/
└── SKILL.md
```

`SKILL.md` 使用 YAML frontmatter + skill 内容：

````markdown
```skill
---
name: my-skill-name
description: 何时以及为何使用此 skill。
---

# Skill 标题

## Overview
此 skill 的功能。

## Process
分步工作流程。
```
````

约定：

- 目录名称与 `name` 字段保持一致
- 使用 kebab-case 命名
- 内容用 ` ```skill ``` ` 围栏代码块包裹
- 一个 skill 对应一个工作流

## 贡献

1. Fork 本仓库
2. 创建分支：`git checkout -b skill/your-skill-name`
3. 添加 skill 目录，包含 `SKILL.md`
4. 更新 `README.md` 和 `README.zh-CN.md` 中的 Skills 表格
5. 提交 Pull Request

## 许可证

MIT
