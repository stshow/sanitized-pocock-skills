# esr Patch log: skills/in-progress/setup-ts-deep-modules

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:8fec7fcef2c9c96fd8f496ef9e9940400a799e956071e563fa260cc6d8482234
- Reason: Model-proposed fix for l1-fnd-02b8a22814e67c1017405c45
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule Dependency install instruction does not pin a version in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +Install `dependency-cruiser` as a devDependency with the detected package manager, pinned to an exact version (no `^`/`~` range, e.g. the package manager's exact/save-exact option) so the lockfile records it and later installs don't silently pull a different release.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"Install `dependency-cruiser` as a devDependency with the detected package manager, pinned to an exact version (no `^`/`~` range, e.g. the package manager's exact/save-exact option) so the lockfile records it and later installs don't silently pull a different release.\n","at":3,"remove":1}],"old_bytes":182,"old_digest":"sha256:caca9978964494e4b2d73e4448e0819a1326d8b2e9ea4a7417f6016bae9205a6","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-02b8a22814e67c1017405c45","resolved":[{"file":"SKILL.md","rule":"Dependency install instruction does not pin a version"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:8fec7fcef2c9c96fd8f496ef9e9940400a799e956071e563fa260cc6d8482234"}],"skill":"skills/in-progress/setup-ts-deep-modules","version":1}
```
