# esr review: skills/engineering/improve-codebase-architecture

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: 587147dd230da299cc5e84971cb0a33f6676f8a6
- Date: 2026-11-14
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    Reviews a local codebase for architectural refactoring opportunities
    (shallow modules that could be made deeper), writes them up as an HTML
    report with before/after diagrams in the temp directory, opens it, and then
    walks the user through a chosen candidate using sibling skills. Along the
    way it updates GLOSSARY.md and offers to write ADRs.

## What it could do (static profile)

- reaches https hosts: cdn.jsdelivr.net, cdn.tailwindcss.com

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low mutable_dependency (claude review: model text, it can be wrong): The generated report loads executable JavaScript from third-party CDNs. Tailwind comes from the unversioned cdn.tailwindcss.com script, and Mermaid is pinned only to major version 11. Neither has a subresource-integrity hash. What runs in the user's browser when the report opens depends on whatever those CDNs serve at that moment.
- low path_handling (claude review: model text, it can be wrong): The report is written to a predictable, timestamp-named file in the shared temp directory (falling back to /tmp) and then opened with xdg-open, open or start. On a multi-user system, another local user could pre-create or swap the file before it is opened.
- low mutable_dependency (claude review: model text, it can be wrong): The review reports an unpinned dependency or hash at line 13 of HTML-REPORT.md.
- low mutable_dependency (claude review: model text, it can be wrong): The review reports an unpinned dependency or hash at line 15 of HTML-REPORT.md.
- low path_handling (claude review: model text, it can be wrong): The review reports an unsafe temp file at line 39 of SKILL.md.
- low input_validation (claude review: model text, it can be wrong): Mermaid is initialized with securityLevel "loose", which allows HTML and click handlers inside diagram labels. The labels and card contents are built from names and text in the scanned codebase. If a repository contains crafted identifiers or glossary text that the agent copies into the report, script could run in the local report page.
- info undeclared_egress (claude review: model text, it can be wrong): The skill opens the generated report in the user's default browser, and the browser then fetches scripts from the Tailwind and jsDelivr CDNs. This is network contact the review context does not declare as an external service. It reveals the user's IP address and the time of use, but no repository content.

## Fix applied

- Fix label: hygiene
- Targets: low path\_handling
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low path\_handling (claude review): – not addressed
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low mutable\_dependency (claude review): – not addressed
- After the fix: low path\_handling (claude review): \~ targeted, not re-verified
- After the fix: low input\_validation (claude review): – not addressed
- After the fix: info undeclared\_egress (claude review): – not addressed
- Fix id: sha256:cb66e17fb9c016840dde86b42118f5f2e0927c526bed30f7d5b39745fb7f8732
- Changed: HTML-REPORT.md
- Changed: SKILL.md
- Fix offered: hygiene, checked
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.
- low path\_handling (claude review): No fix. The fix did not apply to the files.
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.
- low mutable\_dependency (claude review): No fix. The fix did not apply to the files.
- low input\_validation (claude review): No fix. The fix did not apply to the files.
- info undeclared\_egress (claude review): No fix. The claude review says a fix must rewrite too much of the skill.

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
