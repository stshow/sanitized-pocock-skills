# esr review: skills/misc/setup-pre-commit

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 5b63f9f665bacc9be04cae51982e9ef1469d6699
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 32): SKILL.md runs an npm package through npx without pinning its version
- low other (claude review: model text, it can be wrong): withheld: the claude review's words quoted the skill
- low mutable_dependency (claude review: model text, it can be wrong): The skill installs husky, lint-staged and prettier as devDependencies without version pins. It runs \`npx husky init\` and \`npx lint-staged\` without pinned versions, so whatever versions the package registry serves at that moment get installed and run.

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- Targets: low other
- After the fix: low mutable\_dependency (esr rules): ✗ still there
- After the fix: low other (claude review): \~ targeted, not re-verified
- After the fix: low mutable\_dependency (claude review): – not addressed
- Fix id: sha256:477f3c3d9c0f0deb3d4a5398d9da43b32e8661327027fe841a293e566129a1bc
- Changed: SKILL.md
