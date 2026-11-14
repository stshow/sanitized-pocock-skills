# esr Patch log: skills/misc/migrate-to-shoehorn

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:d55be077623ba25e3202a1b339dd6d1499943909bc930317b0efc05ed19acb80
- Reason: Model-proposed fix for l1-fnd-7c47fce8ff0d51ad482e915b
- Upstream commit: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Resolves: rule Package install command has no pinned version in SKILL.md

Changes SKILL.md: 2 line(s) removed and 2 line(s) added, in 2 place(s).

Added:

    +npm i -D --save-exact --ignore-scripts @total-typescript/shoehorn
    +   - [ ] Install: `npm i -D --save-exact --ignore-scripts @total-typescript/shoehorn`

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"npm i -D --save-exact --ignore-scripts @total-typescript/shoehorn\n","at":3,"remove":1}],"old_bytes":80,"old_digest":"sha256:213afe3851a2af4d1d35443f0a730166e84c1da0343374a01ade46beb4912de4","old_lines":7},{"edits":[{"add":"   - [ ] Install: `npm i -D --save-exact --ignore-scripts @total-typescript/shoehorn`\n","at":3,"remove":1}],"old_bytes":368,"old_digest":"sha256:1125cc0fb331493bf480339083c7bbdcd8f815247be46653c746b30b54738884","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-7c47fce8ff0d51ad482e915b","resolved":[{"file":"SKILL.md","rule":"Package install command has no pinned version"}],"upstream_commit":"5863806dd4e15c63174bee4e7515a4256792ecfa"},"id":"sha256:d55be077623ba25e3202a1b339dd6d1499943909bc930317b0efc05ed19acb80"}],"skill":"skills/misc/migrate-to-shoehorn","version":1}
```
