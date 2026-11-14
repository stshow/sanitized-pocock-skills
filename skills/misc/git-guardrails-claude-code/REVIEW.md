# esr review: skills/misc/git-guardrails-claude-code

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: ceed97af09633b300826d0ca0b1464c527ec9a35
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    The skill installs a Claude Code PreToolUse hook: it copies a bundled bash
    script into a project or user-level hooks folder and registers it in Claude
    Code settings. The hook blocks Bash commands that match dangerous git
    patterns such as push, reset --hard, clean -f, branch -D and
    checkout/restore of the whole tree.

## What it could do (static profile)

- ships scripts: scripts/block-dangerous-git.sh

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low input_validation (claude review: model text, it can be wrong): The guardrail is weak in two ways. First, it matches the raw command string against plain substring regexes such as 'git push'. Commands like 'git -C . push', 'git  push' with extra spaces, git aliases, or a command built through a variable or a subshell do not match, so they are allowed. Second, it fails open. If jq is missing or the input cannot be parsed, COMMAND ends up empty or 'null', no pattern matches, and the script exits 0, which allows the command. A user may therefore think destructive git operations are blocked when they are not.
- low persistence (claude review: model text, it can be wrong): The skill tells the agent to copy an executable script into the project's .claude/hooks folder or the user-wide \~/.claude/hooks folder and to add it to the hooks.PreToolUse array in the matching settings.json. Once registered, Claude Code runs the script before every Bash tool call, in every project when the global scope is chosen. This lasting change to agent settings is the stated purpose of the skill. The script itself only reads the tool input and exits with code 0 or 2. The skill asks the user to choose the scope and says to merge into existing settings rather than overwrite them.

## Fix applied

- none
- Fix offered: hygiene, checked
- low persistence (claude review): No fix. The claude review says this is what the skill is for.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
