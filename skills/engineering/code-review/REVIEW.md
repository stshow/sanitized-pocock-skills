# esr review: skills/engineering/code-review

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: a8ef561571acbb611de8ff19ba6da75b197c63a8
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    Reviews the git diff between HEAD and a fixed point the user names, checking
    two things: whether the code follows the repo's documented coding standards
    plus a baseline of Fowler code smells, and whether it matches the issue or
    spec it came from. It runs the two checks in parallel sub-agents and shows
    their reports side by side.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low prompt_injection (claude review: model text, it can be wrong): The skill finds issue numbers in commit messages and fetches those issues through the tracker workflow. It then pastes the fetched spec text into the Spec sub-agent's prompt. The skill does not say that this text, or the commit messages and diff, must be treated as data and not as instructions. Anyone who can write commits or issues could put instructions there that steer the reviewing sub-agents. The skill itself contains nothing hostile.

## Fix applied

- Fix label: hygiene
- After the fix: low prompt\_injection (claude review): – not addressed
- Fix id: sha256:31fd80e84e8b8808348c8b4c693b0b56550f72ab5ef28072a572f1909b5196f4
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low prompt\_injection (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
