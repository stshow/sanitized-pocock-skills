# esr review: skills/in-progress/writing-shape

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: ac92229646fccf7315ae139c37b479b3790617f2
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A writing-assistant skill that reads a markdown file of raw material
    provided by the user and works through it with the user, paragraph by
    paragraph, to build a separate article file. The raw file is treated as
    read-only and the article file is updated as each block is agreed.

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
