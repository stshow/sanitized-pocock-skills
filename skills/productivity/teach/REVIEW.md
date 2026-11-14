# esr review: skills/productivity/teach

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 3fd617b610e59acbb99644de1ef37e394ff53cd1
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An explicitly invoked tutoring skill. Over several sessions it teaches the
    user a topic by keeping a learning workspace in the current directory: a
    mission, resources, learning records, a glossary, notes, HTML lessons,
    reference sheets and shared assets.

## What it could do (static profile)

- reaches https hosts: example.com, reddit.com

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- none

## Fix applied

- Fix label: hygiene
- Fix id: sha256:7df0414e7e6be28469d75e4b235b474dbec45b600b792ff5903c196b8e17dc51
- Changed: SKILL.md
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
