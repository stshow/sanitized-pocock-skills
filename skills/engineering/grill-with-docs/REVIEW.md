# esr review: skills/engineering/grill-with-docs

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: eedaf2562c83155115e9c649fa3ecaac2e10e81d
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A user-invoked wrapper skill that runs an in-depth interview to sharpen a
    plan or design and produces documentation (ADRs and a glossary). It does
    this by telling the agent to call the in-package "grilling" and "domain-
    modeling" skills.

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
