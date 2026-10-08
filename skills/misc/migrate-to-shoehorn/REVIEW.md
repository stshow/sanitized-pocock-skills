# esr review: skills/misc/migrate-to-shoehorn

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 0aea91a3599a4bf7aeec17e3262d4cbcfcbeec23
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- After the fix: low mutable\_dependency (claude review): \~ targeted, not re-verified
- Fix id: sha256:f76b4ab85e930af5a917d781d6f4d44f383cd707c1f32d8603ab11bf5fc2a0cc
- Changed: SKILL.md
