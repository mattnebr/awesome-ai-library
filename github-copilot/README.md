
GitHub Copilot leverages `.github/` files to provide repo-specific context across Visual Studio Enterprise, VS Code, CLI, and GitHub.com. This setup enforces conventions for your C#/Python solutions while enabling `/delegate` workflows.







### Structure Summary

| Component         | Location                                        | Structure                            |
| ----------------- | ----------------------------------------------- | ------------------------------------ |
| **Repo-wide**     | `.github/copilot-instructions.md`               | Single root file                     |
| **Path-specific** | `.github/instructions/{{name}}.instructions.md` | **Flat files** (name describes path) |
| **Agents**        | `.github/agents/{{name}}.agent.md`              | **Flat files**                       |
| **Skills**        | `.github/skills/{{name}}/SKILL.md`              | **Folders**                          |

### Repository Custom Instructions (`.github/copilot-instructions.md`)

- **Purpose:** Always-on, repo-specific guidance.
- **Use case:** Enforce **stable, repo-wide norms**: coding style, architecture notes, build/test/deploy commands, libraries to prefer/avoid.
- **Behavior:** These instructions are automatically applied whenever Copilot interacts with the repo. They’re passive but persistent.
#### Rule of thumb:

> Use custom instructions for anything that should **always apply**, regardless of which agent or skill is being used.

**Example:**

- “All commits must pass `lint` and `unit-tests` before merging.”
- “Use `TypeScript` for backend services and `React` for frontend components.”


## How They Work Together

For a workflow like **“diagnose and fix failing GitHub Actions workflows in a monorepo”:**

| **Component**                      | **Role**                                                                                                                                                |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository Custom Instructions | Provide project-specific context (CI setup, test commands, repo structure).                                                                         |
| Agent Skills                   | Encapsulate the task-specific logic (github-actions-failure-debugging, parsing logs, suggesting fixes).                                             |
| Custom Agent                   | Orchestrates the workflow, deciding when and which skills to apply, interacts with CLI prompts, and provides a “persona” that understands the repo. |

**Recommended pattern:**

1. **Always define repo-wide instructions** for consistent context.
2. **Create modular skills** for repeatable, task-specific logic.
3. **Use custom agents** only when you need a named, orchestrated persona to handle complex workflows or multiple skills together.

## Choosing Between Instruction and Prompt Files

- Instruction Files: Best for repository-wide guidance and long-term standards across multiple contributors and projects.
- Prompt Files: Best for local, session-based guidance or for specific functionality in a single file or segment.
- Combine Both: For maximum results, use instruction files for your overall project and supplement with prompt files in areas that need extra clarity or specificity.







## Step 3: Create Generic CI-Debugger Agent

Create `.github/agents/ci-debugger.agent.md`:

```
---
name: CI Debugger
description: Analyzes failing GitHub Actions, suggests fixes
tools: [read, search, edit]
target: [vscode, github-copilot]
---

You debug CI failures in .NET/Python repos.

1. Read failing workflow logs from `.github/workflows/`
2. Check `src/` build/test errors  
3. Suggest fixes to code or YAML
4. Create PR from `main` via /delegate

Always reference `copilot-instructions.md`.

```

GitHub Copilot **does not support a sub-folder-per-agent structure** as it does for skills. Agents follow a **flat file naming convention** and all exist under the `agents/` folder.


- [Frontmatter Options](https://code.visualstudio.com/docs/copilot/customization/custom-agents#custom-agent-file-structure)




## Step 4: Add Commit Message Skill

Create `.github/skills/commit-message.SKILL.md`:

```
# Commit Message Skill

Generate conventional commits:

<type>[optional scope]: <description>

[optional body]

[optional footer]

Types: feat, fix, docs, style, refactor, test, chore

Examples:
- `feat: add user authentication`
- `fix(tests): resolve MSTest filter failures`
```

GitHub Copilot supports both Claude-style **skills in individual folders** (with `SKILL.md`) and flat `.SKILL.md` files, but the **folder-per-skill structure is the recommended modern approach** across VS Code, CLI, and GitHub.com.

```
.github/skills/
├── commit-message/                   # Each skill = folder
│   ├── SKILL.md                      # Required instruction file
│   └── examples/                     # Optional helpers
│       └── conventional-commits.md
└── mstest-generator/                 # Future skill
    └── SKILL.md
```


## Step 5: Daily Workflows

## Visual Studio Enterprise

1. Open `.sln` → Copilot Chat (`Ctrl+``)    
2. `@ci-debugger Explain this Actions failure` ([how to](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/coding-agent/create-custom-agents))
3. Chat auto-uses `.github/copilot-instructions.md`



