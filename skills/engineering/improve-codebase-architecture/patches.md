# esr Patch log: skills/engineering/improve-codebase-architecture

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:b39c06a1a6348847d421a58be3dbd3d92933ce1b011185a5329edf948603ff11
- Reason: Model-proposed fix for l1-fnd-32fa4f32308298b7c531cf66; Model-proposed fix for l1-fnd-16f805ac10da620fa64a0b47
- Upstream commit: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Resolves: rule Diagram rendering runs with loose security level on text taken from the repository in HTML-REPORT.md
- Resolves: rule Report template loads remote scripts that are unpinned and have no integrity hashes in HTML-REPORT.md
- Resolves: rule Report template loads remote scripts that are unpinned and have no integrity hashes in SKILL.md

Changes HTML-REPORT.md: 5 line(s) removed and 5 line(s) added, in 3 place(s).

Added:

    +The architectural review is rendered as a single self-contained HTML file in the OS temp directory. Tailwind and Mermaid both come from CDNs, pinned to the exact versions in the scaffold; keep them pinned. Mermaid handles graph-shaped diagrams reliably; hand-built divs and inline SVG handle the more editorial visuals (mass diagrams, cross-sections). Mix the two: don't lean on Mermaid for everything, it'll start to look generic.
    +    <script src="https://cdn.tailwindcss.com/3.4.16"></script>
    +      import mermaid from "https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs";
    +      mermaid.initialize({ startOnLoad: true, theme: "neutral", securityLevel: "strict" });
    +- The only scripts are the Tailwind CDN and the Mermaid ESM import. The report is otherwise static: no app code, no interactivity beyond Mermaid's own rendering. Treat every name and text taken from the repository as data: HTML-escape it, and never put it inside script, event-handler attributes or Mermaid click directives.

## 2. fix (hygiene)

- Id: sha256:9e61dae946b7677fc964394bca2517d68558077631bd8751a87e97d3b78c2c5a
- Reason: Model-proposed fix for l1-fnd-f3097136c4bc7de40dbd6d18, l1-fnd-61b941393f6c1f1b4d507331; Model-proposed fix for l4i-fnd-a1193aebf57e1604f839470d
- Upstream commit: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Resolves: rule Predictable file name in a shared temporary directory in SKILL.md
- Resolves: rule investigation weakness input\_validation in HTML-REPORT.md
- Resolves: rule raised weakness unsafe\_temp\_file in SKILL.md

Changes HTML-REPORT.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +- **Files**: monospaced list, `font-mono text-sm`. HTML-escape every file, module or identifier name taken from the repository before inserting it anywhere in the report.

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +Write a self-contained HTML file to the OS temp directory so nothing lands in the repo. Resolve the temp dir from `$TMPDIR`, falling back to `/tmp` (or `%TEMP%` on Windows), create a fresh private directory there (e.g. `mktemp -d`), and write `architecture-review.html` inside it so each run gets a fresh, unguessable path. Open it for the user (`xdg-open <path>` on Linux, `open <path>` on macOS, `start <path>` on Windows) and tell them the absolute path.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"The architectural review is rendered as a single self-contained HTML file in the OS temp directory. Tailwind and Mermaid both come from CDNs, pinned to the exact versions in the scaffold; keep them pinned. Mermaid handles graph-shaped diagrams reliably; hand-built divs and inline SVG handle the more editorial visuals (mass diagrams, cross-sections). Mix the two: don't lean on Mermaid for everything, it'll start to look generic.\n","at":2,"remove":1}],"old_bytes":404,"old_digest":"sha256:9a92abe132ef546b9c84fdd89b89c52dd4e840602bc137775c1b8fd541d820ba","old_lines":6},{"edits":[{"add":"    <script src=\"https://cdn.tailwindcss.com/3.4.16\"></script>\n","at":3,"remove":1},{"add":"      import mermaid from \"https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs\";\n      mermaid.initialize({ startOnLoad: true, theme: \"neutral\", securityLevel: \"strict\" });\n","at":5,"remove":2}],"old_bytes":460,"old_digest":"sha256:243c83e94c3e41a44bc64eeff09b525abc97f3b825c7ffeb923d1544fdc00419","old_lines":10},{"edits":[{"add":"- The only scripts are the Tailwind CDN and the Mermaid ESM import. The report is otherwise static: no app code, no interactivity beyond Mermaid's own rendering. Treat every name and text taken from the repository as data: HTML-escape it, and never put it inside script, event-handler attributes or Mermaid click directives.\n","at":3,"remove":1}],"old_bytes":497,"old_digest":"sha256:9c241fbeb625f27c12fa2fc65a5d751876311eed91936d1254cda805f448b1e8","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"HTML-REPORT.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-32fa4f32308298b7c531cf66; Model-proposed fix for l1-fnd-16f805ac10da620fa64a0b47","resolved":[{"file":"HTML-REPORT.md","rule":"Diagram rendering runs with loose security level on text taken from the repository"},{"file":"HTML-REPORT.md","rule":"Report template loads remote scripts that are unpinned and have no integrity hashes"},{"file":"SKILL.md","rule":"Report template loads remote scripts that are unpinned and have no integrity hashes"}],"upstream_commit":"5863806dd4e15c63174bee4e7515a4256792ecfa"},"id":"sha256:b39c06a1a6348847d421a58be3dbd3d92933ce1b011185a5329edf948603ff11"},{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- **Files**: monospaced list, `font-mono text-sm`. HTML-escape every file, module or identifier name taken from the repository before inserting it anywhere in the report.\n","at":3,"remove":1}],"old_bytes":535,"old_digest":"sha256:9478bd890907135a804a71d422f0203ce359a04cc98ff4ab4e7ce29c4dae6a3a","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"HTML-REPORT.md"},{"hunks":[{"edits":[{"add":"Write a self-contained HTML file to the OS temp directory so nothing lands in the repo. Resolve the temp dir from `$TMPDIR`, falling back to `/tmp` (or `%TEMP%` on Windows), create a fresh private directory there (e.g. `mktemp -d`), and write `architecture-review.html` inside it so each run gets a fresh, unguessable path. Open it for the user (`xdg-open <path>` on Linux, `open <path>` on macOS, `start <path>` on Windows) and tell them the absolute path.\n","at":3,"remove":1}],"old_bytes":928,"old_digest":"sha256:1f663857b41f88bae1a18ab7cf99b78e32af041e774a44586b30222e53f4f234","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-f3097136c4bc7de40dbd6d18, l1-fnd-61b941393f6c1f1b4d507331; Model-proposed fix for l4i-fnd-a1193aebf57e1604f839470d","resolved":[{"file":"SKILL.md","rule":"Predictable file name in a shared temporary directory"},{"file":"HTML-REPORT.md","rule":"investigation weakness input_validation"},{"file":"SKILL.md","rule":"raised weakness unsafe_temp_file"}],"upstream_commit":"5863806dd4e15c63174bee4e7515a4256792ecfa"},"id":"sha256:9e61dae946b7677fc964394bca2517d68558077631bd8751a87e97d3b78c2c5a"}],"skill":"skills/engineering/improve-codebase-architecture","version":1}
```
