# esr review: skills/engineering/ask-matt

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: d6a0d9bf3cdc78cbfcbd6466ac5fd3deffb52877
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    A documentation-only router that helps the user pick which skill or workflow
    from the same package fits their situation (main idea-to-ship flow, on-
    ramps, codebase health, standalone skills), plus guidance on context
    management at phase boundaries.

## What it could do (static profile)

- reaches https hosts: www.aihero.dev

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 90): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)

## Fix applied

- none
- Fix offered: none
- low credential\_access (esr rules): No fix. The claude review says this is what the skill is for.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
