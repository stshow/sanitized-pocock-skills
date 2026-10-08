# esr review: skills/engineering/ask-matt

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: d6a0d9bf3cdc78cbfcbd6466ac5fd3deffb52877
- Date: 2026-10-08
- Choice: keep

## What it does (claude review, model text)

    A documentation-only router skill: the user invokes it explicitly to find
    out which skill or workflow in the same package fits their situation. It
    describes a main flow, on-ramps and standalone skills, and gives a decision
    tree for what to do at a phase boundary (continue, /clear, /handoff,
    subagent, /compact).

## What it could do (static profile)

- reaches https hosts: www.aihero.dev

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 90): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)

## Fix applied

- none
