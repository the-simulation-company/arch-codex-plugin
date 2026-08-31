# Arch PR Authoring for Codex

A Codex plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

Built by [Foothill Labs](https://foothill.sh).

The included skill can be selected automatically when Codex prepares, creates, or edits a PR description.

## Install from the repository marketplace

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

Human-authored and template sections are preserved. The skill traces relevant repository evidence before asking the author for context that is genuinely unavailable.
