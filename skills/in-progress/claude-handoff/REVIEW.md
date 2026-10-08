# esr review: skills/in-progress/claude-handoff

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 57d198aca08eddccb113632d52c6c13f1f3066ac
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low path_handling (claude review: model text, it can be wrong): The skill saves the summary to the shared OS temporary directory, then reads it back with \`$(cat \<summary file\>)\` to build the background agent's prompt. It does not say how to name the file, set its permissions, or delete it afterwards. On a multi-user system, a predictable name or default permissions could let another local user read the summary, which holds conversation content. That user could also replace or symlink the file between the write and the read, and so put their own instructions into the new agent's prompt. The file also stays on disk after the handoff.
- low secret_exposure (claude review: model text, it can be wrong): The summary is built from the whole current conversation and is written to disk and passed on the command line. The skill does tell the agent to redact API keys, passwords and personal data. That redaction depends on the model's judgment, and nothing enforces it. Any secret the model misses ends up in a temp file and in the new agent's command-line arguments, where other local processes may be able to see it.

## Fix applied

- Fix label: hygiene
- Targets: low path\_handling
- After the fix: low path\_handling (claude review): \~ targeted, not re-verified
- After the fix: low secret\_exposure (claude review): – not addressed
- Fix id: sha256:a0d01ebb9f7117349dc2d72ae8d204ed21ec6cd085c5c397c4edb6fbdb3ac867
- Changed: SKILL.md
