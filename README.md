# Arch PR Authoring for Codex

A Codex plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

Published by [Foothill Labs](https://foothill.sh).

The included skill can be selected automatically when Codex prepares, creates, or edits a PR description. It does not run QA, simulations, MCP tools, or any Arch workflow.

## Install from the repository marketplace

After this repository is published:

```bash
codex plugin marketplace add the-simulation-company/arch-codex-plugin --ref main
codex plugin add arch-codex-plugin@arch-pr-authoring
```

Start a new Codex task after installation so the packaged skill is discovered.

## What it adds

The `pr-qa-description` skill asks Codex to ground the PR description in the diff, relevant tests, and repository template, then capture:

- the user-visible change;
- affected pages and components;
- how to reach the behavior;
- required setup or state; and
- evidenced behavioral variants.

Human-authored and template sections are preserved. Missing facts are marked for the author instead of invented.

## Local development

```bash
codex plugin marketplace add /absolute/path/to/arch-codex-plugin
codex plugin add arch-codex-plugin@arch-pr-authoring
```

Validate before publishing:

```bash
python3 /path/to/plugin-creator/scripts/validate_plugin.py plugins/arch-codex-plugin
python3 /path/to/skill-creator/scripts/quick_validate.py plugins/arch-codex-plugin/skills/pr-qa-description
```

Ask Codex to create or edit a PR description without naming the skill. Confirm that product context is added, the repository template is preserved, and no external QA action occurs.

Use [`fixtures/pr-description-cases.md`](fixtures/pr-description-cases.md) for the shared information-level behavior checks.
