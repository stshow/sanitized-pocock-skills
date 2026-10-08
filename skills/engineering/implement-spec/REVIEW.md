# esr review: skills/engineering/implement-spec

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 0cfefc751d0cb64f0c948ffcb17e13b94e778f08
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An explicitly invoked orchestration skill that implements a spec and its
    tickets. It runs parallel implementer subagents in git worktrees, merges
    their work into an integration branch, runs code review, and closes the
    tickets or the PR through the issue tracker.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low other (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill
- low path_handling (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill

## Fix applied

- Fix label: hygiene
- Targets: low path\_handling
- After the fix: low other (claude review): – not addressed
- After the fix: low path\_handling (claude review): \~ targeted, not re-verified
- Fix id: sha256:6514824a40f369c241bbf85cad470c9faa9447c3d1b809f220ac2a75e4e55872
- Changed: SKILL.md
