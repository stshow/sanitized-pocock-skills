# esr review: skills/misc/setup-pre-commit

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 5b63f9f665bacc9be04cae51982e9ef1469d6699
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    Sets up Husky pre-commit hooks in the current JavaScript/TypeScript repo. It
    installs husky, lint-staged and prettier as devDependencies, writes the hook
    and config files, checks the setup and makes a commit.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 32): SKILL.md runs an npm package through npx without pinning its version
- low mutable_dependency (claude review: model text, it can be wrong): The skill installs husky, lint-staged and prettier and runs them through npx without pinning a version. Whatever version the npm registry serves at run time gets installed and runs. The pre-commit hook then runs lint-staged on every commit. This is normal for the stated purpose, but it is still a supply-chain dependency that can change.
- low mutable_dependency (claude review: model text, it can be wrong): The review reports an unpinned dependency or hash at line 26 of SKILL.md.
- low other (claude review: model text, it can be wrong): Step 8 tells the agent to stage all changed and created files and commit them. If the working tree already had unrelated uncommitted changes, those changes could end up in the commit together with the hook setup.

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- Targets: low other
- After the fix: low mutable\_dependency (esr rules): ✗ still there
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low other (claude review): \~ targeted, not re-verified
- Fix id: sha256:477f3c3d9c0f0deb3d4a5398d9da43b32e8661327027fe841a293e566129a1bc
- Changed: SKILL.md
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
