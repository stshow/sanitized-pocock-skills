# esr review: skills/productivity/teach

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 3fd617b610e59acbb99644de1ef37e394ff53cd1
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- reaches https hosts: example.com, reddit.com

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low prompt_injection (claude review: model text, it can be wrong): The skill tells the agent never to trust its own knowledge and to collect knowledge from external resources and communities. Lessons, RESOURCES.md and NOTES.md are then built from that material and reused in later sessions. Text from the web that contains instructions could therefore shape what the agent does or be saved into workspace files that guide future sessions. The skill gives no instruction to treat fetched content as data only.
- info unsafe_execution (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill

## Fix applied

- Fix label: hygiene
- Targets: low prompt\_injection
- After the fix: low prompt\_injection (claude review): \~ targeted, not re-verified
- After the fix: info unsafe\_execution (claude review): – not addressed
- Fix id: sha256:7df0414e7e6be28469d75e4b235b474dbec45b600b792ff5903c196b8e17dc51
- Changed: SKILL.md
