# esr review: skills/engineering/retro

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 335c1862a43da9d629abafdb79ca0c0de118be08
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A user-invoked skill that runs a retrospective on a coding session: it reads
    the session's logs and the repo's steering files, check scripts and CI
    configuration, then suggests improvements to the agent's environment
    (navigation pointers, automated checks, coding standards, tool economy,
    information access) to the user in order of severity.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low excessive_capability (claude review: model text, it can be wrong): The review reports a read or permission that is too broad at line 13 of SKILL.md.
- info other (claude review: model text, it can be wrong): The skill tells the agent to read session logs on the machine and to search through them when the user names a session, and to look at the user's global AGENTS.md. Session transcripts can contain secrets or personal data that were pasted or printed during earlier sessions. The skill does not say which log locations to search or limit the search to the session the user named. The reads fit the retrospective purpose, and nothing in the skill sends the data anywhere. Results are only shown to the user.

## Fix applied

- Fix label: hygiene
- After the fix: low excessive\_capability (claude review): – not addressed
- After the fix: info other (claude review): – not addressed
- Fix id: sha256:5dc115ff2dbc5d211c4988741b6df7f80eb7770ca6533677f90b530155b4323c
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low excessive\_capability (claude review): No fix. The fix did not apply to the files.
- info other (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
