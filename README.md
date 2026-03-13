


# Agent Skills

Agent skills are modular capabilities that extend what an AI assistant can do — such as running tools, calling APIs, automating workflows, or performing structured tasks. They fall into two categories based on where they live. Skill formats are not universally compatible; a skill written for one agent usually requires adaptation before it works with another.

**In-repository skills** are only active for that repository and cloned with it. Each agent has its own folder:

- [GitHub Copilot](https://docs.github.com/en/copilot/concepts/agents/about-agent-skills): `.github/skills`
- [Claude Code](https://code.claude.com/docs/en/skills): `.claude/skills`

**Personal (device-specific) skills** are stored in your home directory and are available across all your projects:

- GitHub Copilot: `~/.copilot/skills`
    - Windows: `C:\Users\<username>\.copilot\skills`
    - Linux/macOS: `/home/<username>/.copilot/skills`
- Claude Code: `~/.claude/skills`
    - Windows: `C:\Users\<username>\.claude\skills`
    - Linux/macOS: `/home/<username>/.claude/skills`

> **Note:** Folders starting with `.` are hidden by default. On Windows, enable **Show hidden items** in File Explorer. On Linux/macOS, list hidden files with `ls -a`.

**Claude AI (chat)** does not read skills from local folders. Add and enable personal skills from the app via **Settings → Capabilities → Skills**.




## Other Libraries

| **Repository**                                                                                             | **Description**                                                                                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Agent GTM (Go To Market) Skills](https://github.com/chadboyda/agent-gtm-skills)                           | 18 skills to help price your product, build a cold outreach sequence, or plan a 16-channel launch.                                                                                                                                                                |
| [Awesome Agent Skills](https://github.com/heilcheng/awesome-agent-skills)                                  | A curated list of skills, tools, and capabilities for AI coding agents.                                                                                                                                                                                           |
| [Awesome Claude Code](https://github.com/jqueryscript/awesome-claude-code)                                 | A curated list of awesome tools, skills, plugins, integrations, extensions, frameworks, and other resources for developers working with **Anthropic's Claude Code**.                                                                                              |
| [Awesome Claude Skills](https://github.com/ComposioHQ/awesome-claude-skills)                               | A curated list of practical Claude Skills for enhancing productivity across Claude.ai, Claude Code, and the Claude API. Includes automation for Email, Messaging, Calendar, and Project Management SaaS platforms.                                                |
| [Awesome Claude Skills](https://github.com/travisvn/awesome-claude-skills)                                 | A curated list of awesome Claude Skills, resources, and tools for customizing Claude AI workflows                                                                                                                                                                 |
| [Build More Architect Dreams (BMAD) Method](https://github.com/bmad-code-org/BMAD-METHOD)                  | An AI-driven agile development module for the BMad Method Module Ecosystem, the best and most comprehensive Agile AI Driven Development framework that has true scale-adaptive intelligence that adjusts from bug fixes to enterprise systems.                    |
| [Claude Code PM](https://github.com/automazeio/ccpm)                                                       | Claude Code workflow to ship ~~faster~~ _better_ using spec-driven development, GitHub issues, Git worktrees, and multiple AI agents running in parallel.                                                                                                         |
| [Claude Scientific Skills](https://github.com/K-Dense-AI/claude-scientific-skills)                         | A comprehensive collection of **170+ ready-to-use scientific and research skills** (now including cancer genomics, drug-target binding, molecular dynamics, RNA velocity, geospatial science, time series forecasting, FRED economic data, and more).             |
| [Context Engineering Kit Plugins](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins) | Hand-crafted collection of advanced context engineering techniques and patterns with minimal token footprint, focused on improving agent result quality and predictability.                                                                                       |
| [Solo Founder Superpowers](https://github.com/whawkinsiv/solo-founder-superpowers)                         | Expert skills for non-technical founders building SaaS with AI tools (Claude Code, Lovable, Replit, Cursor). Covers the full lifecycle of planning, building, launching, and growing a software business — actionable guides, checklists, and copy-paste prompts. |
| [Superpowers](https://github.com/obra/superpowers)                                                         | Superpowers is a complete software development workflow for your coding agents, built on top of a set of composable "skills" and some initial instructions that make sure your agent uses them.                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |
|                                                                                                            |                                                                                                                                                                                                                                                                   |


### Individual Skills


|                                                                    |                                                                                                                                |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| [Frontend Slides](https://github.com/zarazhangrui/frontend-slides) | A Claude Code skill for creating stunning, animation-rich HTML presentations — from scratch or by converting PowerPoint files. |
|                                                                    |                                                                                                                                |
|                                                                    |                                                                                                                                |
|                                                                    |                                                                                                                                |
|                                                                    |                                                                                                                                |
|                                                                    |                                                                                                                                |






