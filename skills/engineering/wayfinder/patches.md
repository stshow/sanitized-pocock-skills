# esr Patch log: skills/engineering/wayfinder

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:926063fde8909ea20431b3b63d308d6a7e458b9bff0c5d3532be2a2a3ea6ee92
- Reason: Model-proposed fix for l1-fnd-6f38cc3b57285f5e8df1e294
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule Open-ended AFK 'Task' work that includes account sign-up and access provisioning in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +- **Task** (HITL or AFK): Manual work that must happen before a _decision_ can be made: nothing to decide, prototype, or research, but the discussion is blocked until it's done. Signing up for a service so its API can be judged, provisioning access, moving data so its shape can be seen. This is the one type that _does_ rather than decides, and it earns its place by unblocking a decision, not by delivering the destination. The agent drives it alone where it can (AFK), but work that creates accounts, grants access, spends money or acts under the user's identity is always HITL: the agent hands the human a precise checklist. Resolved when the work is done; the answer records what was done and any resulting facts (credentials location, new URLs, row counts) later tickets depend on, never secret values such as keys, tokens or passwords.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- **Task** (HITL or AFK): Manual work that must happen before a _decision_ can be made: nothing to decide, prototype, or research, but the discussion is blocked until it's done. Signing up for a service so its API can be judged, provisioning access, moving data so its shape can be seen. This is the one type that _does_ rather than decides, and it earns its place by unblocking a decision, not by delivering the destination. The agent drives it alone where it can (AFK), but work that creates accounts, grants access, spends money or acts under the user's identity is always HITL: the agent hands the human a precise checklist. Resolved when the work is done; the answer records what was done and any resulting facts (credentials location, new URLs, row counts) later tickets depend on, never secret values such as keys, tokens or passwords.\n","at":3,"remove":1}],"old_bytes":1433,"old_digest":"sha256:df07eed0edc77607124b025278c5abcc578a5892d9969e996609a0ec679dc7c0","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-6f38cc3b57285f5e8df1e294","resolved":[{"file":"SKILL.md","rule":"Open-ended AFK 'Task' work that includes account sign-up and access provisioning"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:926063fde8909ea20431b3b63d308d6a7e458b9bff0c5d3532be2a2a3ea6ee92"}],"skill":"skills/engineering/wayfinder","version":1}
```
