# esr review: skills/in-progress/setup-ts-deep-modules

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: b32508a8a7d62c07d32d7c5cff84d357719def7f
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A user-invoked skill that installs dependency-cruiser in a TypeScript repo
    and adds rules so each package can be imported only through its root entry-
    point files. It also scaffolds an example package, checks that the rules
    fail on a deep import, and documents the convention.

## What it could do (static profile)

- reaches https hosts: github.com
- ships scripts: dependency-cruiser.config.cjs

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (claude review: model text, it can be wrong): The review reports an unpinned dependency or hash at line 49 of SKILL.md.
- low mutable_dependency (claude review: model text, it can be wrong): The skill tells the agent to install dependency-cruiser as a devDependency with the repo's package manager but gives no version. Whatever release the registry serves at install time gets installed, and its install scripts run on the user's machine.

## Fix applied

- Fix label: hygiene
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low mutable\_dependency (claude review): – not addressed
- Fix id: sha256:2b8d951d8196816838808cfdf8fd7796db7d6db8a66c394cf525bb420d98faf2
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
