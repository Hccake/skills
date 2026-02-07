# AI Coding Assistant Skills

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> [🇨🇳 中文文档](README.zh-CN.md)

A collection of reusable skills for AI coding assistants. Each skill is a structured workflow defined in a `SKILL.md` file that tells your AI assistant how to approach a specific type of task.

## Skills

| Skill | Description |
|-------|-------------|
| [quick-brainstorm](quick-brainstorm/SKILL.md) | Lightweight brainstorming for bug fixes, small features, and code improvements. Asks targeted questions before jumping into implementation. |

## Quick Start

Install via the [skills CLI](https://www.npmjs.com/package/skills):

```bash
npx skills add hccake/skills
```

Or install a specific skill:

```bash
npx skills add hccake/skills --skill quick-brainstorm
```

Then tell your AI assistant to use it:

```
Fix the login timeout bug. Use quick-brainstorm skill.
```

## Skill Format

Each skill lives in its own directory with a `SKILL.md` file:

```
<skill-name>/
└── SKILL.md
```

`SKILL.md` uses YAML frontmatter + skill content:

````markdown
```skill
---
name: my-skill-name
description: When and why to use this skill.
---

# Skill Title

## Overview
What this skill does.

## Process
Step-by-step workflow.
```
````

Conventions:

- Directory name matches the `name` field
- Use kebab-case for names
- Wrap content in ` ```skill ``` ` fenced code blocks
- One skill, one workflow

## Contributing

1. Fork this repository
2. Create a branch: `git checkout -b skill/your-skill-name`
3. Add your skill directory with a `SKILL.md`
4. Update the Skills table in both `README.md` and `README.zh-CN.md`
5. Submit a Pull Request

## License

MIT
