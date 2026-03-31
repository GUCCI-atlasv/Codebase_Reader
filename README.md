# Codebase Reader

A Claude Code skill that reads any GitHub repository and produces a plain-language briefing for non-technical people.

Drop a GitHub link. Get back a clear, honest Markdown document that tells you what the project does, whether you should care, and how to use it — without requiring you to read a single line of code.

## Who is this for?

**Non-technical people who encounter code repos regularly** — product managers, founders, designers, marketers, operators, curious learners. You keep running into GitHub links in Slack threads, blog posts, or Hacker News, and you want to quickly understand: is this relevant to me?

You don't want a technical README rehash. You want someone to translate it into human.

## What the output looks like

A Markdown file structured around **value first**:

1. **One-liner** — what it does, one sentence
2. **Who should care** — are you the target audience?
3. **The problem it solves** — the "before" world, so you feel the pain
4. **How it works** — no jargon, with analogies
5. **How to get started** — honest about difficulty level
6. **When to use / when not to** — fit vs. wrong tool
7. **Verdict** — an honest take on maturity, activity, and red flags

Want more? Say "go deeper" and get architecture overview, design decisions, community health, similar projects, and best practices.

## Example

Input:
> 看下这个 https://github.com/astral-sh/uv 我想知道它解决了什么问题

Output (excerpt):

> **一句话总结**
> 一个极快的 Python 项目管理工具——把原本需要七八个不同工具才能完成的事情，合并成一个工具搞定。
>
> **它解决了什么问题**
> Python 的工具生态是出了名的混乱。想象一下这个场景：你要做一个 Python 项目。你需要安装 Python 本身（用 pyenv），需要创建隔离环境（用 virtualenv），需要安装依赖包（用 pip）……每个工具有自己的安装方式、配置文件、命令语法。光是搞清楚"我该用哪个工具"就能耗掉一下午。
>
> 这就像你要做一顿饭，但刀、砧板、锅、铲、灶台分别在五个不同的商店，而且每个商店的营业时间和付款方式都不一样。

## How to use

### As a Claude Code skill

1. Copy the `codebase-reader` folder into `~/.claude/skills/`
2. Open Claude Code
3. Paste a GitHub link, or say something like:
   - "帮我看看这个仓库"
   - "这个项目是干嘛的？"
   - "Explain this repo to me"
   - "Is this project worth using?"

### Trigger phrases

The skill activates when you share a GitHub URL, or ask things like:

- "What is this repo?"
- "Help me understand this codebase"
- "Is this worth using?"
- "这个项目解决了什么问题？"

## Design philosophy

**Value before description.** Don't start with "this is a Python library that..." — start with why anyone should care.

**Smart friend, not professor.** The reader is intelligent but not technical. Explain, don't lecture.

**Honest, not salesy.** If a project is abandoned, say so. If setup is hard, say so. Trust comes from not overselling.

**Brevity is respect.** Quick overview stays under 800 words. Deep dive is opt-in.

## Skill structure

```
codebase-reader/
├── SKILL.md       # Skill instructions
└── README.md      # This file
```

---

Inspired by [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course). Built with Claude.
