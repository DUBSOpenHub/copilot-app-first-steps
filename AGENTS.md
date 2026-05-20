# AGENTS.md - Working Guide for AI Agents

This file tells AI agents how to work effectively on the Copilot App First Steps repository.

## Architecture

Copilot App First Steps is a prompt-only tutor skill for the GitHub Copilot app.

```text
README.md                              -> user-facing landing and overview
install.html                           -> one-click start landing page
SKILL.md                               -> root inspection copy of the skill
skills/copilot-app-first-steps/        -> canonical skill package
.github/skills/copilot-app-first-steps -> GitHub-discoverable skill copy
agents/copilot-app-first-steps.agent.md -> tutor persona and operating rules
agents/copilot-app-first-steps.md      -> product/design notes
evals/copilot-app-first-steps/         -> mock eval suite
TESTING.md                             -> conversation playbooks
assets/*.svg                           -> accessible visual aids
```

## File ownership map

| File/Dir | Owner | Change rules |
| --- | --- | --- |
| `SKILL.md` | Tutor behavior | Keep synchronized with `skills/.../SKILL.md` and `.github/skills/.../SKILL.md`. |
| `skills/copilot-app-first-steps/` | Canonical skill package | Update catalog version when behavior changes. |
| `.github/skills/copilot-app-first-steps/` | GitHub skill copy | Must match canonical `SKILL.md`. |
| `agents/*.agent.md` | Agent persona/config | Keep under 200 lines and define exact behavior. |
| `install.html` | One-click entry | Do not invent unsupported app deep links. Keep fallback plain. |
| `assets/*.svg` | Visual aids | Include `<title>` and `<desc>` for accessibility. |
| `evals/` | Evaluation coverage | Add tasks when new user flows are introduced. |

## Before changing anything

1. Read the file you are changing completely.
2. Preserve the non-technical, beginner-first tone.
3. Keep terminal/manual setup out of the primary path.
4. Update tests/evals when behavior changes.
5. Run the validation workflow locally where possible.

## Tutor rules

- The user should never wonder where to start.
- Route vague beginner prompts to the Start Here menu.
- Explain technical terms before using them.
- Show safety guidance before any editing workflow.
- Never use destructive examples.
- Never claim one-click skill install exists unless a real supported URL is configured.

## One-click install rule

`install.html` has a `COPILOT_APP_SKILL_INSTALL_URL` constant. Leave it blank until GitHub documents an official Copilot app skill-install or prompt-launch deep link. The fallback should remain the official Copilot app download/releases page.

## Common pitfalls

1. Treating this like a CLI tutorial.
2. Leading with terminal commands.
3. Using Git jargon before explaining it.
4. Forgetting to keep the three `SKILL.md` copies synchronized.
5. Adding visual assets without text equivalents.
