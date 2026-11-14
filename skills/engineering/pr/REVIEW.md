# esr review: skills/engineering/pr

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 00b896d811adffad747c7ca30078d909d60c7f93
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    An instruction-only skill that gives the agent a template and writing
    guidance for pull request descriptions, with Summary (visuals such as
    pseudocode, call trees, file trees, Mermaid or diffs), Evidence
    (before/after) and Merge Danger (one-way/two-way door, blast radius)
    sections.

## What it could do (static profile)

- reaches https hosts: github.com

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- none

## Fix applied

- none

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
