# esr review: skills/misc/migrate-to-shoehorn

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 0aea91a3599a4bf7aeec17e3262d4cbcfcbeec23
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    Guides the agent to migrate TypeScript test files from `as` type assertions
    to the @total-typescript/shoehorn helpers (fromPartial, fromAny, fromExact):
    it installs the package, finds test files that use `as`, rewrites them and
    runs a type check.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (claude review: model text, it can be wrong): The skill tells the agent to run \`npm i @total-typescript/shoehorn\` with no version pin. Whatever version the registry serves at that moment gets installed, and its install scripts may run. This is normal for the stated purpose, but the dependency can change over time.
- low mutable_dependency (claude review: model text, it can be wrong): The review reports an unpinned dependency or hash at line 23 of SKILL.md.

## Fix applied

- Fix label: hygiene
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low mutable\_dependency (claude review): – not addressed
- Fix id: sha256:f76b4ab85e930af5a917d781d6f4d44f383cd707c1f32d8603ab11bf5fc2a0cc
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
