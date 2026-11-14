# esr review: skills/productivity/handoff

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: ce24892bd2d4b9e7fd5ac9b95c03175e18bef388
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    The skill has the agent summarise the current conversation into a handoff
    document that another agent can pick up. It saves the document in the
    operating system's temporary directory, suggests skills for the next agent
    and tells the agent to redact sensitive information.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low other (claude review: model text, it can be wrong): The skill writes a summary of the conversation to the shared system temporary directory and does not set a file name or file permissions. On a machine with several users, other local users might be able to read the document or plant a file at the same name beforehand. The content is reduced by the instruction to redact API keys, passwords and personal information, but whether that redaction is complete depends on the model.
- low path_handling (claude review: model text, it can be wrong): The review reports an unsafe temp file at line 8 of SKILL.md.

## Fix applied

- none
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
