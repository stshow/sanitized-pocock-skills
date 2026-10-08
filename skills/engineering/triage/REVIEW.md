# esr review: skills/engineering/triage

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 4cb951d62ecccaed601cdc5f9a1b7b3d8a799635
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen medium, Socket safe (0 alerts), Snyk medium; BAD: Gen medium, Snyk medium

## Findings

- medium prompt_injection (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill
- medium unsafe_execution (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill

## Fix applied

- Fix label: security
- Targets: medium prompt\_injection
- Targets: medium unsafe\_execution
- After the fix: medium prompt\_injection (claude review): \~ targeted, not re-verified
- After the fix: medium unsafe\_execution (claude review): \~ targeted, not re-verified
- Fix id: sha256:8f1df24a0b31049046510d97a1778cfc494ab0dc15e4766bf697c97a0db56843
- Changed: SKILL.md
