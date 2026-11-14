# esr review: skills/productivity/wait-what

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: c8b050e6b8c711be1a9008ceacb2126914f0763e
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A user-invoked prompt skill. It asks the agent to re-explain its last
    message more simply: give more context, write in ASD-STE100 Simplified
    Technical English, and use the project's terms from GLOSSARY.md, using
    GLOSSARY-MAP.md to find the right glossary when there is more than one.

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
