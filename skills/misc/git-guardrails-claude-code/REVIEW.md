# esr review: skills/misc/git-guardrails-claude-code

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: ceed97af09633b300826d0ca0b1464c527ec9a35
- Date: 2026-10-08
- Choice: keep

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- ships scripts: scripts/block-dangerous-git.sh

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low input_validation (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill
- low persistence (claude review: model text, it can be wrong): The skill tells the agent to write an executable script into the project or user-level Claude Code hooks directory and to merge a PreToolUse hook entry into the project or global settings.json. The hook then runs on every Bash tool call in all later sessions, and in every project if the global scope is chosen. This is the skill's stated purpose and the bundled script only reads the tool input and exits, but it is still a lasting change to agent configuration.

## Fix applied

- none
