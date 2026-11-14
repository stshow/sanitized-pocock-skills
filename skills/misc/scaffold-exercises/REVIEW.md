# esr review: skills/misc/scaffold-exercises

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 44a0ee332b9d67ebbd59389c7eb4e5aff1ce845c
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    The skill scaffolds course exercise directories (sections, problems,
    solutions, explainers) with stub readme files under an exercises/ folder,
    checks them with the project's `pnpm ai-hero-cli internal lint`, and commits
    the result with git.

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
