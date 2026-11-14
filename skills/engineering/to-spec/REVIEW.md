# esr review: skills/engineering/to-spec

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 136b9651747cfccbfbb7c50a6b0dfb757e7547d2
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An explicitly invoked skill that turns the current conversation and what the
    agent knows about the codebase into a structured spec. It then publishes the
    spec to the project's issue tracker with a 'ready-for-agent' triage label.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- none

## Fix applied

- Fix label: hygiene
- Fix id: sha256:8815daa1e79da0f19afaf920e3b13966a1930e221960c85f898fedd415ea33bf
- Changed: SKILL.md
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
