# Testing Guide

Copilot App First Steps is a conversational tutor skill. Testing is done with conversation playbooks and lightweight eval tasks.

## Core acceptance criteria

- A non-technical user sees one obvious place to start.
- README has a top hero graphic with accessible alt text.
- GitHub Pages root URL is a discovery landing page, not a redirect-only page.
- Discovery and tutor copy explain value through things the learner can create.
- The experience reinforces that everyone can become a developer.
- No terminal commands appear in the primary onboarding path.
- The tutor routes vague beginner messages to the Start Here menu.
- Lessons show progress, a clear goal, and a safety note.
- Permission prompts are explained before any editing exercise.
- The tutor does not teach CLI, VS Code, Git branches, or advanced development concepts unless asked.
- The one-click install page does not invent an unsupported Copilot app deep link.

## Playbook 1: One-click entry, app installed

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Open README | The first visible action is **Open the app and build**. |
| 2 | Click install button | Landing page copies `start app tutorial` or shows it clearly. |
| 3 | Open Copilot app | User has one phrase to paste: `start app tutorial`. |
| 4 | Start tutor | Skill shows Start Here menu with three choices. |

## Playbook 1A: Public discovery page

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Visit `https://dubsopenhub.github.io/copilot-app-first-steps/` | User sees a premium landing page with a clear hero, outcome cards, role cards, Open/Ask/Build path, safety model, FAQ, and CTA. |
| 2 | Click **Open the app and build** | User lands on `install.html`. |
| 3 | Click **See what you can build** | User jumps to the outcome cards. |

## Playbook 2: One-click entry, app not installed

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Click install button | User reaches official Copilot app download/release page. |
| 2 | User cannot install | Troubleshooting explains preview/org/subscription access plainly. |
| 3 | User returns after install | README still shows one phrase: `start app tutorial`. |

## Playbook 3: Vague beginner message

| Step | User says | Expected behavior |
| --- | --- | --- |
| 1 | `help` | Skill shows Start Here menu, not a technical answer. |
| 2 | `what now` | Skill shows Start Here menu. |
| 3 | `I'm new` | Skill shows Start Here menu. |

## Playbook 4: First app tour

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Select "I am in the app but do not know what to do" | Skill initializes progress. |
| 2 | Skill starts L1 | Shows progress map, lesson card, and app map. |
| 3 | User says they do not know where to type | Skill points to the message box using plain visual language. |

## Playbook 5: First useful prompt

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Start L2 | Skill explains prompts as plain requests. |
| 2 | User picks a role | Skill gives one tailored copy/paste prompt. |
| 3 | User says answer is too technical | Skill teaches "Say it simpler. Assume I am brand new." |

## Playbook 6: Projects and sessions

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Start L3 | Skill defines project and session without Git jargon. |
| 2 | User sees only chat | Skill explains this is okay and continues orientation. |
| 3 | User asks about repositories | Skill defines repository only as "the stored project files" unless more detail is requested. |

## Playbook 7: Permission prompt

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Start L4 | Skill shows safety card before any editing task. |
| 2 | User sees Allow/Deny | Skill explains Allow, Deny, and when to pause. |
| 3 | User is nervous | Skill normalizes stopping and gives a safer explanation prompt. |

## Playbook 8: Issue workflow

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Choose "Understand an issue" | Skill defines issue as request/problem/task. |
| 2 | User has no real issue | Skill provides a practice prompt instead of blocking. |
| 3 | User asks for next steps | Skill returns a short checklist. |

## Playbook 9: PR workflow

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Choose "Review a pull request" | Skill defines PR as proposed change for review. |
| 2 | User says "what is merge?" | Skill explains merge as "accepting the proposed change into the project." |
| 3 | User asks for non-engineer summary | Skill gives changed/why/watch-outs format. |

## Playbook 10: Reset and resume

| Step | User action | Expected behavior |
| --- | --- | --- |
| 1 | Complete L1 and L2 | Progress is tracked in SQL. |
| 2 | Say `next lesson` | Skill resumes at L3. |
| 3 | Say `restart tutorial` | Skill drops progress tables and returns to Start Here. |

## Manual content checks

- Search for `terminal`, `CLI`, `branch`, and `rebase`; confirm none are primary onboarding concepts.
- Confirm every visual has text equivalents.
- Confirm `assets/hero.svg` includes `<title>` and `<desc>` and does not recreate unofficial GitHub or Copilot logos.
- Confirm the design uses the official Copilot palette direction from the GitHub Brand Toolkit: GitHub dark surfaces, blue primary actions, and Copilot purple accents.
- Confirm no raw brand guideline sheets or product lockup reference images are shown in learner-facing pages.
- Confirm no destructive exercise examples exist.
- Confirm `install.html` uses a blank `COPILOT_APP_SKILL_INSTALL_URL` until a supported URL is known.
