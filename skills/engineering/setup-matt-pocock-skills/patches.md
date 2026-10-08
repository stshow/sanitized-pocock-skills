# esr Patch log: skills/engineering/setup-matt-pocock-skills

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:a86df80e6a3f18d1563aba4e3a8e04576a1d973ed92d755864a27d253a6ed2d3
- Reason: Model-proposed fix for l1-fnd-2d9a99134e7ac4925783e9d3
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule Remote write to issue tracker is not part of the draft the user reviews in SKILL.md

Changes SKILL.md: 0 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +- When Section B ran on GitHub or GitLab, the exact label names step 4 will create in the remote tracker; create only the labels listed here.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- When Section B ran on GitHub or GitLab, the exact label names step 4 will create in the remote tracker; create only the labels listed here.\n","at":3,"remove":0}],"old_bytes":314,"old_digest":"sha256:ede93b9c5fbf09541fac7e64d08f9ca6eeb6df134eb186ac0e9f2d9fed1dcbc3","old_lines":6}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-2d9a99134e7ac4925783e9d3","resolved":[{"file":"SKILL.md","rule":"Remote write to issue tracker is not part of the draft the user reviews"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:a86df80e6a3f18d1563aba4e3a8e04576a1d973ed92d755864a27d253a6ed2d3"}],"skill":"skills/engineering/setup-matt-pocock-skills","version":1}
```
