# esr Patch log: skills/engineering/retro

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:e5b4aaddfe4f086233c6e8e02606a4419c2c8c784f902c34b676aaea88372b50
- Reason: Model-proposed fix for l1-fnd-e48003e2bdc924b084a261c1
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule Open-ended instruction to search machine-wide session logs without a defined scope in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +2. Read the primary sources for the session the user specifies. This may mean locating that one session's log on this machine; read only that session's log (not other sessions or projects), and do not repeat secrets or personal data from it in your output. If the user doesn't specify a session, default to the current one.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"2. Read the primary sources for the session the user specifies. This may mean locating that one session's log on this machine; read only that session's log (not other sessions or projects), and do not repeat secrets or personal data from it in your output. If the user doesn't specify a session, default to the current one.\n","at":3,"remove":1}],"old_bytes":335,"old_digest":"sha256:5c71e0f9d8855266f0b6fc0643ad598b5306eee19dd8178ac702ff839aac14ae","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-e48003e2bdc924b084a261c1","resolved":[{"file":"SKILL.md","rule":"Open-ended instruction to search machine-wide session logs without a defined scope"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:e5b4aaddfe4f086233c6e8e02606a4419c2c8c784f902c34b676aaea88372b50"}],"skill":"skills/engineering/retro","version":1}
```
