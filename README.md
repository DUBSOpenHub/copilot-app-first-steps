# Copilot App First Steps

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Security Policy](https://img.shields.io/badge/Security-Policy-brightgreen?logo=github)](SECURITY.md)

<p>
  <img src="assets/hero.svg" alt="Copilot App First Steps hero showing a simplified Copilot app window and Start Here guidance" width="100%">
</p>

> A guided, beginner-friendly tutor for people who have never used the GitHub Copilot app.

## Start here

If you are brand new, use the button below.

<p>
  <a href="https://dubsopenhub.github.io/copilot-app-first-steps/install.html">
    <img src="assets/install-button.svg" alt="Install tutor and start" width="360">
  </a>
</p>

This opens the simple start page, copies the tutor phrase, and sends you to the official Copilot app install/open path:

```text
start app tutorial
```

No terminal commands are required for the main path.

## Who this is for

This is for non-technical or first-time users who want to learn the GitHub Copilot app without needing to understand Git, branches, pull requests, terminals, or developer jargon first.

Good fits:

- Product managers
- Designers
- Support teammates
- Managers
- Founders
- Operations partners
- Anyone curious about what the Copilot app can do

## What you will learn

By the end, you will be able to:

1. Open the Copilot app and know where to start.
2. Understand the main parts of the app.
3. Ask useful questions in plain English.
4. Understand projects and sessions.
5. Approve, deny, or pause actions safely.
6. Ask Copilot to explain issues and pull requests in plain language.
7. Complete one real workflow with confidence.

## The guided path

```text
Start -> Open app -> First prompt -> Projects -> Safety -> Workflows -> Issues/PRs -> Graduation
```

The tutor shows a "You are here" marker at every step.

## Visual tour

### Start menu

![Start Here screen](assets/start-here.svg)

### App map

![App map](assets/app-map.svg)

### Approval prompt model

![Approval prompt model](assets/approval-prompt.svg)

## How to use the tutor

Open the Copilot app and type:

```text
start app tutorial
```

The tutor will ask one question at a time and guide you through the app.

## What makes this different

This is not a command-line tutorial. It is specific to the GitHub Copilot app:

- Chat overlay
- Project sessions
- Issue sessions
- Pull request sessions
- Permission prompts
- Guided work
- Session navigation

The tutor explains everything in beginner language and avoids technical shortcuts unless you ask for them.

## Having trouble?

### I do not have the Copilot app installed

Go to the official Copilot app releases page:

https://github.com/github/app/releases

The app may require preview access depending on your account or organization.

### I opened the app but do not know what to type

Type this exact phrase:

```text
start app tutorial
```

### I see a login or access message

That usually means one of these is true:

- You need to sign in to GitHub.
- Your Copilot subscription is not active for this account.
- Your organization has not enabled Copilot app access yet.
- The app preview is not available to your account yet.

Ask your GitHub or organization admin if you are using a work account.

### I see a permission prompt

You are still in control.

```text
Green: Read or explain - usually safe
Yellow: Create or edit - review first
Red: Delete, overwrite, publish, or merge - pause and ask why
```

When learning, choose the safest option and ask Copilot to explain what it wants to do.

## For technical helpers

This package includes the skill in two locations:

```text
skills/copilot-app-first-steps/SKILL.md
.github/skills/copilot-app-first-steps/SKILL.md
```

Use whichever location your Copilot app or skill loader supports. The primary learner path should remain the one-click install page, not manual setup.

## Repository contents

This repo follows the same pattern as the other DUBSOpenHub Copilot skill projects:

- `README.md` - learner-facing start page
- `install.html` and `index.html` - one-click landing page
- `SKILL.md` - root skill entry for quick inspection
- `skills/copilot-app-first-steps/SKILL.md` - canonical skill package
- `.github/skills/copilot-app-first-steps/SKILL.md` - GitHub-discoverable skill copy
- `agents/copilot-app-first-steps.agent.md` - agent persona/config
- `agents/copilot-app-first-steps.md` - product/design notes for the tutor
- `SECURITY.md` - private vulnerability reporting policy
- `CONTRIBUTING.md` - contribution workflow
- `docs/QA_REVIEW.md` - latest QA review results
- `docs/workflows/validate.yml` - ready-to-activate package validation workflow
- `docs/workflows/pages.yml` - ready-to-activate Pages deployment workflow

Maintainer note: the workflow files are committed as templates under `docs/workflows/` because the token used to create the repo did not include `workflow` scope. Move them to `.github/workflows/` after refreshing auth with `workflow` scope.

## Package layout

```text
copilot-app-first-steps/
├── README.md
├── index.html
├── install.html
├── TESTING.md
├── AGENTS.md
├── SECURITY.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── LICENSE
├── agents/
│   ├── copilot-app-first-steps.agent.md
│   └── copilot-app-first-steps.md
├── assets/
│   ├── start-here.svg
│   ├── hero.svg
│   ├── install-button.svg
│   ├── app-map.svg
│   └── approval-prompt.svg
├── docs/
│   └── workflows/
│       ├── validate.yml
│       └── pages.yml
├── skills/
│   └── copilot-app-first-steps/
│       ├── SKILL.md
│       └── catalog.yml
├── .github/
│   └── skills/
│       └── copilot-app-first-steps/
│           └── SKILL.md
└── evals/
    └── copilot-app-first-steps/
        ├── eval.yaml
        └── tasks/
```

## One-click install note

This package does not invent an unsupported Copilot app URL scheme. `install.html` keeps the app install/open URL in one place so an official skill-install deep link can be added as soon as the app exposes one.

## How it was built

This tutor was designed from the patterns used across DUBSOpenHub Copilot skill repos, with special attention to non-technical onboarding, visual guidance, one-click entry, security posture, and beginner-safe permission education.

🐙 Created with 💜 by [@DUBSOpenHub](https://github.com/DUBSOpenHub) with the GitHub Copilot CLI.
