# esr Patch log: skills/engineering/wizard

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:49684a9d61e5c60ab88f1a7116338f53be5f4681a17f01267d6e2daa17c573b5
- Reason: Model-proposed fix for l1-fnd-9c29a2f1894abec771cf3414, sf-0001
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule Scoping reads whole secret-bearing env files when only key names are needed in SKILL.md
- Resolves: rule credential-path in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +- For setup: `.env.example`, only the key names (never the values) defined in `.env` and `.env.*`, `README`, `docker-compose*`, framework config, and `.github/workflows/*` (every `secrets.*` / `vars.*` reference is a value the wizard must produce).

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- For setup: `.env.example`, only the key names (never the values) defined in `.env` and `.env.*`, `README`, `docker-compose*`, framework config, and `.github/workflows/*` (every `secrets.*` / `vars.*` reference is a value the wizard must produce).\n","at":3,"remove":1}],"old_bytes":568,"old_digest":"sha256:7807b26aacd905b80b5c66ed30d7a02448abb2f25b0dc2b823e3c070eff421eb","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-9c29a2f1894abec771cf3414, sf-0001","resolved":[{"file":"SKILL.md","rule":"Scoping reads whole secret-bearing env files when only key names are needed"},{"file":"SKILL.md","rule":"credential-path"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:49684a9d61e5c60ab88f1a7116338f53be5f4681a17f01267d6e2daa17c573b5"}],"skill":"skills/engineering/wizard","version":1}
```
