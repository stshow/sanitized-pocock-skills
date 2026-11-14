# esr review: skills/engineering/setup-matt-pocock-skills

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: b644b684781fd5baae57f6be000a180a4d4448d7
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A one-time setup skill that configures a repository for the package's
    engineering skills. It looks at the repo, asks the user which issue tracker,
    triage labels and domain-doc layout to use, then writes config files under
    docs/agents/, adds an '## Agent skills' section to CLAUDE.md or AGENTS.md,
    and can create missing triage labels on GitHub or GitLab.

## What it could do (static profile)

- reaches https hosts: gitlab.com

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low persistence (claude review: model text, it can be wrong): The skill adds or updates an '\#\# Agent skills' block in CLAUDE.md or AGENTS.md and writes docs/agents/\*.md files. These files are loaded into agent context in later sessions, so they change how agents behave in this repo from then on. The content comes from the skill's templates: tracker conventions, label mappings, and domain-doc rules that tell future agents to run gh/glab commands and to 'proceed silently' when domain docs are missing. This is the skill's stated purpose. The user sees a draft before anything is written, and the templates contain no hidden or override text.

## Fix applied

- Fix label: hygiene
- After the fix: low persistence (claude review): – not addressed
- Fix id: sha256:285e017a822885f87e70aa7a67691783427c677e424db15bf5b259c9433046a4
- Changed: SKILL.md
- Changed: issue-tracker-github.md
- Changed: issue-tracker-gitlab.md
- Fix offered: hygiene, checked
- low persistence (claude review): No fix. The claude review says this is what the skill is for.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
