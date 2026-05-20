# QA Review

## Summary

Copilot App First Steps was reviewed for repository completeness, one-click start behavior, beginner clarity, safety guidance, validation coverage, and GitHub repo settings.

Result: pass with one known operational limitation.

## Scope reviewed

- README learner journey.
- Live one-click landing page.
- `install.html` behavior and fallback text.
- Skill instructions and lesson flow.
- Agent guidance.
- Catalog metadata.
- Security and contribution files.
- Issue and PR templates.
- Eval tasks and testing playbooks.
- GitHub Pages configuration.
- Repository settings and security posture.

## Checks performed

### User journey

- README has one obvious first action.
- README includes a top hero graphic with accessible alt text.
- Landing page is reachable from the README.
- Landing page contains the phrase `start app tutorial`.
- Landing page links to the official Copilot app releases page.
- Beginner-facing copy avoids terminal-first setup.

### Repository structure

- Root `SKILL.md` exists.
- Canonical skill exists at `skills/copilot-app-first-steps/SKILL.md`.
- GitHub-discoverable skill copy exists at `.github/skills/copilot-app-first-steps/SKILL.md`.
- Agent file exists at `agents/copilot-app-first-steps.agent.md`.
- Product notes exist at `agents/copilot-app-first-steps.md`.
- `AGENTS.md`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `LICENSE`, PR template, issue templates, CODEOWNERS, and Dependabot config exist.

### Validation

- Skill copies match.
- YAML parses.
- HTML parses.
- Catalog references resolve.
- SVG assets include `<title>` and `<desc>`.
- The top hero graphic is brand-safe and does not recreate unofficial GitHub or Copilot logos.
- Agent prompt is under 200 lines.
- User-facing content does not lead with terminal setup.
- Eval task count is 10.

### Remote repo

- Repository is public.
- Issues are enabled.
- Wiki is disabled.
- Delete branch on merge is enabled.
- GitHub Pages is configured from the `main` branch root.
- GitHub Pages landing page returns HTTP 200.
- Dependabot security updates are enabled.
- Secret scanning and push protection are enabled.

## Findings and fixes

### Fixed: maintainer details appeared too early

The README originally introduced repository internals before the learner value proposition was complete. That could distract non-technical users.

Fix: moved repository contents and workflow notes below learner-facing sections.

### Fixed: landing page exposed maintainer implementation details

The landing page trouble section originally mentioned the deep-link constant too early. That was accurate but not beginner-friendly.

Fix: rewrote the trouble section to first explain what the learner should do, then left the deep-link constant as a technical helper note.

### Fixed: catalog polish

The catalog had an empty emoji field.

Fix: set the project emoji to `🧭` to match the guided-tour concept.

### Added: maintainer-jargon eval

Added an eval task that protects the beginner path from leaking token scopes, workflow details, or repo internals.

### Added: top README hero graphic

Added `assets/hero.svg` at the top of the README. The graphic uses GitHub Primer-style colors, a simplified app window, and explicit Start Here guidance without recreating unofficial GitHub or Copilot logos.

## Known limitation

The current GitHub token used to create the repository does not include `workflow` scope. Because of that, active workflow files could not be pushed to `.github/workflows/`.

Mitigation:

- Workflow files are committed as ready-to-activate templates under `docs/workflows/`.
- Move them into `.github/workflows/` after refreshing GitHub auth with `workflow` scope.
- Branch-based GitHub Pages is already configured and the landing page is live without requiring the Pages workflow.

## Conclusion

The repo is ready for use as a beginner-friendly Copilot app tutor. The main learner journey is clear, the live landing page works, the package follows the DUBSOpenHub skill repo pattern, and security-related repository settings are enabled.
