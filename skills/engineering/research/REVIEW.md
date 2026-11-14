# esr review: skills/engineering/research

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 2f8f36af48796faed5c687c75bb650071631a984
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    The skill starts a background agent that researches a question against
    primary sources such as official docs, source code, specs and first-party
    APIs. The agent writes the findings, with a source for each claim, to a
    single Markdown file in the repository.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- info prompt_injection (claude review: model text, it can be wrong): The skill sends a background agent to read outside material: docs, source code, specs and API responses. Nothing tells that agent to treat what it reads as data rather than instructions. If a page it reads contains hidden instructions, the agent might follow them while it works out of the user's view. The skill itself does not tell the agent to obey fetched text, so this is only a possible exposure, not shown behaviour.

## Fix applied

- Fix label: hygiene
- After the fix: info prompt\_injection (claude review): – not addressed
- Fix id: sha256:e9a988b74fdad5a766a85cfab53f562505d3bafd80b5f8d4d5d53a7187e383c4
- Changed: SKILL.md
- Fix offered: hygiene, checked
- info prompt\_injection (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
