# Copilot App First Steps - Product Notes

## Product

Copilot App First Steps is an interactive tutor skill for non-technical users who have never used the GitHub Copilot app and want to understand what they can create with it.

## Problem

The Copilot app can be powerful but unfamiliar. First-time users may not know:

- Where to start.
- What value the app can create for them.
- What a project or session is.
- Where to type.
- What approvals mean.
- How issues and pull requests relate to their work.
- How to ask useful questions without technical vocabulary.

## Approach

The tutor creates an obvious Start Here path, then guides the learner through short interactive lessons using choices, progress markers, visual text cards, and copy/paste prompt recipes. Every lesson should connect the tool to something the learner can create.

Core message:

```text
Everyone can become a developer by learning to turn ideas into useful things.
```

## Required experience

The first visible action should be:

```text
Install tutor and start
```

If the app can support a deep link later, wire it into `install.html`. Until then, the landing page uses the official app download/release page and gives the user the phrase:

```text
start app tutorial
```

## Curriculum

1. Before you start.
2. Meet the app.
3. Your first useful conversation.
4. Projects and sessions.
5. Letting Copilot do work safely.
6. Guided tour of workflows.
7. Issues and pull requests.
8. Asking better questions.
9. Troubleshooting and confidence.
10. Graduation task.

## Success criteria

- A non-technical user reaches the Start Here screen without seeing terminal commands first.
- The learner understands what they can create and why it is valuable.
- The learner can describe projects, sessions, issues, PRs, and approvals in plain language.
- The learner completes one useful workflow.
- The repo validates skill metadata, YAML, HTML, SVG accessibility labels, and guardrails.
