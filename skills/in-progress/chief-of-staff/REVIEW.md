# esr review: skills/in-progress/chief-of-staff

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 58e0a4122260ba45c150d8201dad2d6de4153d18
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An explicitly invoked orchestration skill. It has the agent act as a long-
    running 'chief of staff' that sends work to background subagents, keeps a
    markdown wiki as lasting memory, runs procedures from other skills in the
    same package (retro, to-spec, to-tickets, implement-spec), and keeps
    improving the development environment.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- medium excessive_capability (claude review: model text, it can be wrong): The skill tells the agent to FIRST consider changes to the environment as part of any and all work, to be relentless about it, and to use every user message as an excuse to look for improvements. It also says any deviation from convention must be fixed proactively before feature work. This standing directive pushes the agent to change lint rules, coding standards, APIs and code beyond what the user asked for, and to put that work ahead of the user's actual request.
- low credential_access (claude review: model text, it can be wrong): The skill encourages giving agents access to production logs, test environment databases and the browser. Setting this up may mean the agent wires in or handles connection credentials and sensitive data that the user's request did not name.
- low other (claude review: model text, it can be wrong): For large work, the skill tells the agent to publish specs and tickets to the issue tracker. This uses the user's identity and third-party account, and no confirmation step is mentioned.
- low excessive_capability (claude review: model text, it can be wrong): The skill replaces the last step of the in-package retro procedure. Instead, the agent itself decides which improvement candidates to pursue and then pursues them. If retro's last step is where the user chooses, this removes the user from that decision and lets the agent carry out self-selected changes on its own.

## Fix applied

- Fix label: hygiene
- Targets: low credential\_access
- Targets: low other
- Targets: low excessive\_capability
- After the fix: medium excessive\_capability (claude review): – not addressed
- After the fix: low credential\_access (claude review): \~ targeted, not re-verified
- After the fix: low other (claude review): \~ targeted, not re-verified
- After the fix: low excessive\_capability (claude review): \~ targeted, not re-verified
- Fix id: sha256:234692d61d7b73d9d3a91e0f2bfa00baffe1a5aae46857ac51bda0f99ce63f15
- Changed: SKILL.md
- Fix offered: hygiene, checked
- medium excessive\_capability (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
