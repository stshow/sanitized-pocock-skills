# esr Patch log: skills/misc/setup-pre-commit

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:0b9a10fc99a42adbf169fda342b224115c954082943e304a4395be40f12c13d1
- Reason: Model-proposed fix for sf-0001; Model-proposed fix for l1-fnd-0bdfd3233f7e50eca26aefba
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule broad-git-staging in SKILL.md
- Resolves: rule unpinned-npx in SKILL.md

Changes SKILL.md: 4 line(s) removed and 4 line(s) added, in 3 place(s).

Added:

    +npx --no-install husky init
    +npx --no-install lint-staged
    +- [ ] Run `npx --no-install lint-staged` to verify it works (only run the locally installed copy, never fetch one from the registry)
    +Stage only the files this skill created or changed (package.json, the lockfile, `.husky/pre-commit`, `.lintstagedrc`, and `.prettierrc` if created), never unrelated or untracked files, and commit with message: `Add pre-commit hooks (husky + lint-staged + prettier)`

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"npx --no-install husky init\n","at":3,"remove":1}],"old_bytes":125,"old_digest":"sha256:a259c68732d0c216cff0b766788c75f8d37ddee799ccf427a9ab9dc311316cb5","old_lines":7},{"edits":[{"add":"npx --no-install lint-staged\n","at":3,"remove":1}],"old_bytes":107,"old_digest":"sha256:343ee916d2d79b6dcc2e56884729d9f98ff6c853104ec547b5f3e267d3dc1ce4","old_lines":7},{"edits":[{"add":"- [ ] Run `npx --no-install lint-staged` to verify it works (only run the locally installed copy, never fetch one from the registry)\n","at":3,"remove":1},{"add":"Stage only the files this skill created or changed (package.json, the lockfile, `.husky/pre-commit`, `.lintstagedrc`, and `.prettierrc` if created), never unrelated or untracked files, and commit with message: `Add pre-commit hooks (husky + lint-staged + prettier)`\n","at":7,"remove":1}],"old_bytes":379,"old_digest":"sha256:7ec07b844fe5faaf1798f4a228edf417539d2cf8c9d368e55f239c4b41bef1e1","old_lines":11}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for sf-0001; Model-proposed fix for l1-fnd-0bdfd3233f7e50eca26aefba","resolved":[{"file":"SKILL.md","rule":"broad-git-staging"},{"file":"SKILL.md","rule":"unpinned-npx"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:0b9a10fc99a42adbf169fda342b224115c954082943e304a4395be40f12c13d1"}],"skill":"skills/misc/setup-pre-commit","version":1}
```
