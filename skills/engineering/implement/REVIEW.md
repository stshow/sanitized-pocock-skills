# esr review: skills/engineering/implement

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 4804b466ab26c9b9d8d42917547db133d1f20a9f
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A short, user-invoked workflow skill that implements work from a spec or
    tickets. It fetches a referenced ticket, uses the in-package tdd skill, runs
    typechecks and tests, asks the in-package code-review skill to review the
    work, and commits to the current branch.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- none

## Fix applied

- none
- Fix offered: none
- No fix needed. esr found no weakness to fix.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
