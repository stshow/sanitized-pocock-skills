# esr review: skills/in-progress/writing-beats

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 3a28fb076fdaaec0927080718abb98fc0f340011
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A writing aid that helps the user turn a markdown file of raw material into
    an article, one beat at a time. It offers candidate beats, makes sure each
    concept is explained before a later beat relies on it, and appends only the
    beat the user picks to an article file at a path the user chooses.

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
