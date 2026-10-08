# esr review: skills/engineering/code-review

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: fee7bb5fdddc069d58cbea09b2c36b5a859eac05
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low prompt_injection (claude review: model text, it can be wrong): The skill fetches issue text that commit messages reference through the tracker workflow, reads spec files from the repo, and passes these contents to a sub-agent. Third parties may have written the issue bodies, commit messages and diffs. The skill never says to treat this content as data, so instructions embedded in it could steer the sub-agents or the final report. The skill itself contains no hostile instructions.
- low input_validation (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill

## Fix applied

- Fix label: hygiene
- Targets: low prompt\_injection
- Targets: low input\_validation
- After the fix: low prompt\_injection (claude review): \~ targeted, not re-verified
- After the fix: low input\_validation (claude review): \~ targeted, not re-verified
- Fix id: sha256:696069fc3ef6753dcaea3ce90874ab154ef43a84606d369d33d7a4a4942f178d
- Changed: SKILL.md
