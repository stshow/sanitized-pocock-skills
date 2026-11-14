# esr review: skills/engineering/wizard

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: e396d3ba97c723a78ffd350fb14a3c409137b306
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    The skill has the agent write an interactive bash "wizard" script from a
    bundled template. The script walks a person through manual setup steps, such
    as copying API keys from a third-party dashboard, then saves the values to a
    .env file and to GitHub Actions secrets or variables through the gh CLI.

## What it could do (static profile)

- reaches https hosts: dashboard.stripe.com
- ships scripts: template.sh

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 8): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low credential_access (esr rules; rule credential-path in template.sh line 106): template.sh references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low excessive_capability (claude review: model text, it can be wrong): The review reports a read or permission that is too broad at line 20 of SKILL.md.
- low credential_access (claude review: model text, it can be wrong): In the scoping step, the agent is told to read the repo's \`.env\`, \`.env.example\` and \`.env.\*\` files. The \`.env\` and \`.env.\*\` files usually hold real secret values, which would then enter the agent's context. To scope the wizard, the agent only needs the key names. \`.env.example\` and the \`secrets.\*\`/\`vars.\*\` references in CI workflows already give it those names.
- info other (claude review: model text, it can be wrong): When the person runs the generated wizard, it writes secrets in plain text to a .env file in the current directory. It also uses the person's authenticated gh CLI session to set repository secrets and variables on GitHub. This is the stated purpose. The human runs the script, and the skill tells the agent not to run it. Still, it acts on the user's GitHub identity and stores credentials on disk.

## Fix applied

- Fix label: hygiene
- Targets: low credential\_access
- After the fix: low credential\_access (esr rules): ✗ still there
- After the fix: low credential\_access (esr rules): – not addressed
- After the fix: low excessive\_capability (claude review): – not addressed
- After the fix: low credential\_access (claude review): – not addressed
- After the fix: info other (claude review): – not addressed
- Fix id: sha256:8fa8c101629b5d8bbc4ace6d3e8c3e6f039251f85be443b24c89883ed2f51538
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low credential\_access (esr rules): No fix. The claude review says this is what the skill is for.
- low excessive\_capability (claude review): No fix. The fix did not apply to the files.
- low credential\_access (claude review): No fix. The fix did not apply to the files.
- info other (claude review): No fix. The claude review says this is what the skill is for.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
