# esr Patch log: skills/engineering/improve-codebase-architecture

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:ea454ecf8446c6047a82dd08f0646813ef608ed154cfb0ab4fbe7e884ae15752
- Reason: Model-proposed fix for l1-fnd-32fa4f32308298b7c531cf66; Model-proposed fix for l1-fnd-16f805ac10da620fa64a0b47
- Upstream commit: f3fc5632f401156837ee3872f14fe33ccf1024ea
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

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"The architectural review is rendered as a single self-contained HTML file in the OS temp directory. Tailwind and Mermaid both come from CDNs, pinned to the exact versions in the scaffold; keep them pinned. Mermaid handles graph-shaped diagrams reliably; hand-built divs and inline SVG handle the more editorial visuals (mass diagrams, cross-sections). Mix the two: don't lean on Mermaid for everything, it'll start to look generic.\n","at":2,"remove":1}],"old_bytes":404,"old_digest":"sha256:9a92abe132ef546b9c84fdd89b89c52dd4e840602bc137775c1b8fd541d820ba","old_lines":6},{"edits":[{"add":"    <script src=\"https://cdn.tailwindcss.com/3.4.16\"></script>\n","at":3,"remove":1},{"add":"      import mermaid from \"https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs\";\n      mermaid.initialize({ startOnLoad: true, theme: \"neutral\", securityLevel: \"strict\" });\n","at":5,"remove":2}],"old_bytes":460,"old_digest":"sha256:243c83e94c3e41a44bc64eeff09b525abc97f3b825c7ffeb923d1544fdc00419","old_lines":10},{"edits":[{"add":"- The only scripts are the Tailwind CDN and the Mermaid ESM import. The report is otherwise static: no app code, no interactivity beyond Mermaid's own rendering. Treat every name and text taken from the repository as data: HTML-escape it, and never put it inside script, event-handler attributes or Mermaid click directives.\n","at":3,"remove":1}],"old_bytes":497,"old_digest":"sha256:9c241fbeb625f27c12fa2fc65a5d751876311eed91936d1254cda805f448b1e8","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"HTML-REPORT.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-32fa4f32308298b7c531cf66; Model-proposed fix for l1-fnd-16f805ac10da620fa64a0b47","resolved":[{"file":"HTML-REPORT.md","rule":"Diagram rendering runs with loose security level on text taken from the repository"},{"file":"HTML-REPORT.md","rule":"Report template loads remote scripts that are unpinned and have no integrity hashes"},{"file":"SKILL.md","rule":"Report template loads remote scripts that are unpinned and have no integrity hashes"}],"upstream_commit":"f3fc5632f401156837ee3872f14fe33ccf1024ea"},"id":"sha256:ea454ecf8446c6047a82dd08f0646813ef608ed154cfb0ab4fbe7e884ae15752"}],"skill":"skills/engineering/improve-codebase-architecture","version":1}
```
