# esr Patch log: skills/in-progress/claude-handoff

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:f182c7c4761872866c61bf8bf5b2a5050dbcce87c9a33c21b5ef02032bc80619
- Reason: Model-proposed fix for l1-fnd-776bd4212eb3c2d59b9ccb60
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule Unspecified temp-file naming, permissions and cleanup for content that becomes an agent prompt in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +Write a handoff summary of the current conversation so a fresh agent can continue the work. Save it to a new file created with `mktemp` (unpredictable name, readable only by the user) in the temporary directory of the user's OS, then launch a background agent seeded with it as its prompt: `claude --bg --name "<descriptive name>" -- "$(cat <summary file>)"`. Passing the file keeps the shell from running backticks or expanding `$` in the summary. Delete the summary file as soon as the launch command returns. It starts in the current working directory and returns immediately; the user manages it with `claude agents`.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"Write a handoff summary of the current conversation so a fresh agent can continue the work. Save it to a new file created with `mktemp` (unpredictable name, readable only by the user) in the temporary directory of the user's OS, then launch a background agent seeded with it as its prompt: `claude --bg --name \"<descriptive name>\" -- \"$(cat <summary file>)\"`. Passing the file keeps the shell from running backticks or expanding `$` in the summary. Delete the summary file as soon as the launch command returns. It starts in the current working directory and returns immediately; the user manages it with `claude agents`.\n","at":3,"remove":1}],"old_bytes":680,"old_digest":"sha256:1a34aab1e3123da01b325df08246bdb6553317d6a6d8c80f4ff61a0cd16f8365","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-776bd4212eb3c2d59b9ccb60","resolved":[{"file":"SKILL.md","rule":"Unspecified temp-file naming, permissions and cleanup for content that becomes an agent prompt"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:f182c7c4761872866c61bf8bf5b2a5050dbcce87c9a33c21b5ef02032bc80619"}],"skill":"skills/in-progress/claude-handoff","version":1}
```
