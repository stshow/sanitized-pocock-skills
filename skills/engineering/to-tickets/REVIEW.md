# esr review: skills/engineering/to-tickets

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 2dee20ad722a31c04ededf9f2d83842473573045
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    Turns a plan, spec, or the current conversation into a set of vertical-slice
    tickets, each listing the tickets that block it. After the user approves the
    breakdown, it publishes them either as local markdown files or as issues on
    the configured tracker.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- none

## Fix applied

- Fix label: hygiene
- Fix id: sha256:880538f26d3f93cd9f0356ca04e0c9425144ea1647a65df8f976b1c12ff6c08d
- Changed: SKILL.md
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
