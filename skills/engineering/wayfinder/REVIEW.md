# esr review: skills/engineering/wayfinder

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 25da74eadc3e388b2f2a2cc716f3d44b2fb9dfe0
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    Wayfinder plans a large piece of work as a map issue on the repo's issue
    tracker, with child decision tickets. It then resolves those tickets one per
    session by delegating to other in-package skills (grilling, domain-modeling,
    research, prototype) until the route to the stated destination is clear.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- medium excessive_capability (claude review: model text, it can be wrong): The Task ticket type lets the agent do real-world work on its own (AFK) to unblock a decision. The examples include signing up for a service, provisioning access and moving data, and the resolution records facts such as where the credentials are stored. In AFK mode the skill sets no limit on which accounts, services or data the agent may touch. An agent following it could create third-party accounts, accept terms, or provision access under the user's identity. It could also write credential locations into a shared tracker that collaborators can read.
- low prompt_injection (claude review: model text, it can be wrong): When working a ticket, the agent fetches related and closed ticket bodies on demand. It then calls whichever skills the map's Notes block names, and the map's Notes can also carry execution into the map itself. The map and tickets live on a shared tracker where other people or concurrent sessions can edit them. Text in the tracker therefore decides which skills run and how far the agent goes, and nothing says to treat ticket and map text as data rather than instructions.
- low prompt_injection (claude review: model text, it can be wrong): The review reports fetched text used as instructions at line 124 of SKILL.md.

## Fix applied

- Fix label: hygiene
- Targets: low prompt\_injection
- After the fix: medium excessive\_capability (claude review): – not addressed
- After the fix: low prompt\_injection (claude review): – not addressed
- After the fix: low prompt\_injection (claude review): \~ targeted, not re-verified
- Fix id: sha256:b5f20f6fba5320cb2a33df5e9db437d48087d44c021cc3ff68a43c128092d4a2
- Changed: SKILL.md
- Fix offered: hygiene, checked
- medium excessive\_capability (claude review): No fix. The fix did not apply to the files.
- low prompt\_injection (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
