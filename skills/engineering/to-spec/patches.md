# esr Patch log: skills/engineering/to-spec

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:947b784212758a175467fa7d72681717efa31f8890114f73eb6427f97bddf872
- Reason: Model-proposed fix for l1-fnd-c35053fa33137ce02544ed97
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule External publish step under the user's identity with no review of the final content in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +3. Write the spec using the template below, then publish it to the project issue tracker. Apply the `ready-for-agent` triage label - no need for additional triage. The spec must contain only feature-relevant content: never include credentials, keys, tokens, environment values, personal data, or conversation details unrelated to the feature.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"3. Write the spec using the template below, then publish it to the project issue tracker. Apply the `ready-for-agent` triage label - no need for additional triage. The spec must contain only feature-relevant content: never include credentials, keys, tokens, environment values, personal data, or conversation details unrelated to the feature.\n","at":3,"remove":1}],"old_bytes":247,"old_digest":"sha256:ce3e147b820416801a29a51ade76c74f566cbf1234df73bdab4d926ed0352b5f","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-c35053fa33137ce02544ed97","resolved":[{"file":"SKILL.md","rule":"External publish step under the user's identity with no review of the final content"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:947b784212758a175467fa7d72681717efa31f8890114f73eb6427f97bddf872"}],"skill":"skills/engineering/to-spec","version":1}
```
