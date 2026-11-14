# esr review: skills/engineering/domain-modeling

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: ea30ee454ba264543dbe40737973b1a5afb9f0e6
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    Instruction-only skill that helps the agent build and refine a project's
    domain model. It challenges vague terms, checks them against the code, and
    records terms in GLOSSARY.md and decisions as ADRs under docs/adr/.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- none

## Fix applied

- none

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
