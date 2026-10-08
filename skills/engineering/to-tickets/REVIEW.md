# esr review: skills/engineering/to-tickets

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 2dee20ad722a31c04ededf9f2d83842473573045
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low prompt_injection (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill

## Fix applied

- Fix label: hygiene
- Targets: low prompt\_injection
- After the fix: low prompt\_injection (claude review): \~ targeted, not re-verified
- Fix id: sha256:880538f26d3f93cd9f0356ca04e0c9425144ea1647a65df8f976b1c12ff6c08d
- Changed: SKILL.md
