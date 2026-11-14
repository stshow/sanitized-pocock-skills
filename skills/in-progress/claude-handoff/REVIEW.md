# esr review: skills/in-progress/claude-handoff

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 57d198aca08eddccb113632d52c6c13f1f3066ac
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    The user runs this skill by hand to write a summary of the current
    conversation to a file in the OS temporary directory. It then starts a new
    background Claude Code agent (`claude --bg --name ...`) that gets that
    summary as its prompt and carries on the work in the current working
    directory.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low path_handling (claude review: model text, it can be wrong): The review reports an unsafe temp file at line 8 of SKILL.md.
- low unsafe_execution (claude review: model text, it can be wrong): The skill starts a separate background agent that runs without supervision in the current working directory. Its prompt is a summary of the conversation, built from whatever the conversation held, and that can include text from untrusted files, web pages or tool output. Any instructions hidden in that text can be passed on to an agent that the user does not watch as it works. This is the skill's stated purpose, and only the user can invoke it, so it is a design risk rather than hidden behaviour.
- low path_handling (claude review: model text, it can be wrong): The summary is saved to the shared OS temporary directory. The skill sets no unique name and no restrictive permissions. On a multi-user system, another local user could read the summary, which may contain project details, or could swap the file between the write and the \`$(cat ...)\` read, changing the background agent's prompt. The skill does tell the agent to redact secrets and personal data before writing.

## Fix applied

- Fix label: hygiene
- After the fix: low path\_handling (claude review): – not addressed
- After the fix: low unsafe\_execution (claude review): – not addressed
- After the fix: low path\_handling (claude review): – not addressed
- Fix id: sha256:a0d01ebb9f7117349dc2d72ae8d204ed21ec6cd085c5c397c4edb6fbdb3ac867
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low path\_handling (claude review): No fix. The fix did not apply to the files.
- low path\_handling (claude review): No fix. The fix did not apply to the files.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
