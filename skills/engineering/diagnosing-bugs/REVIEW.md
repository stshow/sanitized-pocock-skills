# esr review: skills/engineering/diagnosing-bugs

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 5fdd6cc53385395441910b026c72d71768e993d4
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A step-by-step method for diagnosing hard bugs and performance regressions.
    The agent builds a reproducible pass/fail feedback loop, minimises the
    failing case, ranks hypotheses, adds tagged instrumentation, writes a
    regression test with the fix, and cleans up afterwards. It ships an optional
    template script for when a person has to carry out some of the steps.

## What it could do (static profile)

- reaches http hosts: localhost
- ships scripts: scripts/hitl-loop.template.sh

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- none

## Fix applied

- none

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
