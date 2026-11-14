# esr review: skills/engineering/implement-spec

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 407c196f5c88af53c71efc8f31ee37c02dbb12e7
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An orchestration skill that the user invokes explicitly. It implements a
    spec and its tickets (produced by /to-spec and /to-tickets) on one git
    integration branch. It runs one background implementer subagent per ticket,
    each in its own worktree, merges their work with a merger subagent, runs the
    in-package tdd and code-review skills, and then marks a draft PR ready or
    resolves the tickets in the issue tracker.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low other (claude review: model text, it can be wrong): The skill tells the agent to open a draft PR marked as closing the spec and tickets, mark it ready for review, and otherwise resolve each ticket the way the issue tracker closes work. These actions run under the user's identity on third-party services such as the code host and the issue tracker. The skill does not ask for a check before it changes their state. This is the stated purpose and the user must invoke the skill explicitly (model invocation is disabled), so the risk is low. It is noted because tickets can be closed in bulk with the user's account.

## Fix applied

- Fix label: hygiene
- After the fix: low other (claude review): – not addressed
- Fix id: sha256:372abd6ae450cb41c1cfcb5b42a4ead45eb37d837c49107d9236a9e6ae68ef88
- Changed: SKILL.md
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
