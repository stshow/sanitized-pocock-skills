# esr review: skills/engineering/triage

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 4cb951d62ecccaed601cdc5f9a1b7b3d8a799635
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A maintainer-invoked skill that moves issues and external pull requests on
    the project's issue tracker through triage states. It gathers context from
    the codebase, verifies claims, writes agent briefs or needs-info notes,
    applies labels, closes wontfix items and keeps a `.out-of-scope/` record of
    rejected feature requests.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen medium, Socket safe (0 alerts), Snyk medium; BAD: Gen medium, Snyk medium

## Findings

- medium unsafe_execution (claude review: model text, it can be wrong): The skill tells the agent to check out external contributors' pull requests and run the relevant tests or commands. It also tells the agent to reproduce bugs by following the reporter's steps. Both the PR code and the reporter's steps come from untrusted third parties. Running them in the maintainer's local working environment executes attacker-controllable code (for example test scripts, build hooks or package install scripts) with the maintainer's privileges and credentials. The skill does not mention any isolation.
- low prompt_injection (claude review: model text, it can be wrong): The review reports fetched text used as instructions at line 74 of SKILL.md.
- low prompt_injection (claude review: model text, it can be wrong): The agent reads full issue and PR bodies, comments, diffs and prior triage notes written by outside parties. The same agent can post comments, change labels, close issues, write files and run commands. The skill never says to treat this third-party text as data rather than instructions. Text planted in an issue or PR could therefore steer the agent into unwanted tracker actions or command execution.

## Fix applied

- Fix label: hygiene
- Targets: low prompt\_injection
- After the fix: medium unsafe\_execution (claude review): – not addressed
- After the fix: low prompt\_injection (claude review): \~ targeted, not re-verified
- After the fix: low prompt\_injection (claude review): – not addressed
- Fix id: sha256:aedcf7aca1c7b4597cad5c5c72c2c33cf264fdf5d972fefc9487b93288b1ed58
- Changed: SKILL.md
- Fix offered: hygiene, checked
- medium unsafe\_execution (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
