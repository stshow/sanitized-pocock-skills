# esr Patch log: skills/in-progress/chief-of-staff

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (security)

- Id: sha256:e657f0601be31d6eebb822f0a8c4e4fc859f1fb4b4bb999fedfcc128e440ba29
- Reason: Model-proposed fix for l1-fnd-8401597beb7437e1ecb747fe; Model-proposed fix for l1-fnd-6389522b6617649809e42609; Model-proposed fix for l1-fnd-b925953b14da44a471225ca2
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Resolves: rule A standing directive makes environment changes the agent decides on itself come before the user's explicit request. in SKILL.md
- Resolves: rule Broad data-source access is encouraged with no limit on scope or credentials. in SKILL.md
- Resolves: rule Recurring schedules are part of the skill's design, with no limit on how they are set up. in SKILL.md

Changes SKILL.md: 5 line(s) removed and 5 line(s) added, in 3 place(s).

Added:

    +Harness-permitting, you will suggest recurring schedules which can help in achieving the goal; describe them for the user to set up and do not create scheduled jobs or recurring runs yourself.
    +As part of your work, also consider how the environment the agents operate in might be improved, but the user's request always comes first and environment changes stay within the scope the user asked for. Agents thrive in the **pit of success**:
    +They also need relevant **data sources** to succeed, limited to sources the user has already provided or named (never search for or read credentials, keys or connection secrets to obtain access):
    +- Deviations from conventions should be fixed within the scope of the user's request
    +Keep looking for these improvements, but report changes outside the requested scope as suggestions instead of making them.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"Harness-permitting, you will suggest recurring schedules which can help in achieving the goal; describe them for the user to set up and do not create scheduled jobs or recurring runs yourself.\n","at":3,"remove":1}],"old_bytes":125,"old_digest":"sha256:80b03c337a151ebbd2d44fc369db05bc1a80066173016011332d3e7891c2a984","old_lines":7},{"edits":[{"add":"As part of your work, also consider how the environment the agents operate in might be improved, but the user's request always comes first and environment changes stay within the scope the user asked for. Agents thrive in the **pit of success**:\n","at":3,"remove":1},{"add":"They also need relevant **data sources** to succeed, limited to sources the user has already provided or named (never search for or read credentials, keys or connection secrets to obtain access):\n","at":9,"remove":1}],"old_bytes":518,"old_digest":"sha256:ca91cdf25602bdfd2a5f57f03f5d969d0ebf8474af137c122d3d0b2f9e86d61d","old_lines":13},{"edits":[{"add":"- Deviations from conventions should be fixed within the scope of the user's request\n","at":3,"remove":1},{"add":"Keep looking for these improvements, but report changes outside the requested scope as suggestions instead of making them.\n","at":5,"remove":1}],"old_bytes":360,"old_digest":"sha256:6f85c83a9730ba7803c6b44adf2bfe8c9b3566ec86b15f07d255e3f6fbad85e0","old_lines":6}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (security)","reason":"Model-proposed fix for l1-fnd-8401597beb7437e1ecb747fe; Model-proposed fix for l1-fnd-6389522b6617649809e42609; Model-proposed fix for l1-fnd-b925953b14da44a471225ca2","resolved":[{"file":"SKILL.md","rule":"A standing directive makes environment changes the agent decides on itself come before the user's explicit request."},{"file":"SKILL.md","rule":"Broad data-source access is encouraged with no limit on scope or credentials."},{"file":"SKILL.md","rule":"Recurring schedules are part of the skill's design, with no limit on how they are set up."}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:e657f0601be31d6eebb822f0a8c4e4fc859f1fb4b4bb999fedfcc128e440ba29"}],"skill":"skills/in-progress/chief-of-staff","version":1}
```
