# esr review: skills/in-progress/chief-of-staff

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 22d9deee06f8fe60b752ea386c5fa50312aa15c3
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A prompt-only skill that turns the agent into a long-running 'chief of
    staff'. It hands work to background subagents, suggests recurring schedules,
    and keeps changing the project environment (lint rules, coding standards,
    data sources) so that later tasks go better. It contains no scripts and is
    set to run only when invoked explicitly.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- medium instruction_override (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill
- low persistence (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill
- low excessive_capability (claude review: model text, it can be wrong): The skill tells the agent that subagents need data sources such as production logs, test-environment databases and browser access. It says nothing about scope or about how that access is obtained. Following it may push the agent to look for database connection details or production credentials, or to drive a browser, which goes beyond a typical coding request.

## Fix applied

- Fix label: security
- Targets: medium instruction\_override
- Targets: low persistence
- Targets: low excessive\_capability
- After the fix: medium instruction\_override (claude review): \~ targeted, not re-verified
- After the fix: low persistence (claude review): \~ targeted, not re-verified
- After the fix: low excessive\_capability (claude review): \~ targeted, not re-verified
- Fix id: sha256:04955256f814c9029a5132c5a0154bbfdf0707e4b682811375f019ff2d8c9440
- Changed: SKILL.md
