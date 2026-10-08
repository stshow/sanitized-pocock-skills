# esr review: skills/engineering/wizard

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 47010ebd1f26c8263016f14cdba835355d278b9a
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

Not available: withheld: the claude review's summary quoted the skill.

## What it could do (static profile)

- reaches https hosts: dashboard.stripe.com
- ships scripts: template.sh

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 8): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low credential_access (esr rules; rule credential-path in template.sh line 100): template.sh references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low credential_access (claude review: model text, it can be wrong): In the scoping step, the agent is told to read the repo's \`.env\` and \`.env.\*\` files as well as \`.env.example\`. Real \`.env\` files usually hold live secret values, so reading them puts those secrets into the agent's context. To scope the wizard, the agent only needs the variable names, which \`.env.example\` and the \`secrets.\*\`/\`vars.\*\` references in workflows already supply.
- info other (claude review: model text, it can be wrong): The template's \`set\_secret\` and \`set\_var\` helpers use the person's authenticated gh session to write GitHub Actions secrets and variables. They overwrite any existing value of the same name and do not ask for confirmation. The person who runs the wizard triggers these writes, and SKILL.md tells the agent not to run the script itself. Still, which secrets get pushed, and to which repository, depends on the stages the agent writes at runtime.

## Fix applied

- Fix label: hygiene
- Targets: low credential\_access
- Targets: low credential\_access
- After the fix: low credential\_access (esr rules): ✗ still there
- After the fix: low credential\_access (esr rules): – not addressed
- After the fix: low credential\_access (claude review): \~ targeted, not re-verified
- After the fix: info other (claude review): – not addressed
- Fix id: sha256:30c656c84357f23a7ad5b35a83a9b376c4a0062b2ce895709f0d764a0bf647fb
- Changed: SKILL.md
