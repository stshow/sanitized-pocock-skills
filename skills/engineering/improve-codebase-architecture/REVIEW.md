# esr review: skills/engineering/improve-codebase-architecture

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: f3fc5632f401156837ee3872f14fe33ccf1024ea
- Skill tree reviewed: 39bd9cc130f7dfcc4e3ea0b3613f6ebed0d0ad2b
- Date: 2026-10-08
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An explicitly invoked skill that scans a codebase for chances to deepen
    shallow modules. It reads git history, the project glossary and ADRs, writes
    a visual HTML report to the temp directory and opens it, then walks the user
    through a chosen candidate using sibling skills, updating GLOSSARY.md and
    ADRs as decisions are made.

## What it could do (static profile)

- reaches https hosts: cdn.jsdelivr.net, cdn.tailwindcss.com

## Public scores (outside opinions)

- public scores (outside opinions): Gen medium, Socket safe (0 alerts), Snyk medium; BAD: Gen medium, Snyk medium

## Findings

- low mutable_dependency (claude review: model text, it can be wrong): The generated report loads Tailwind from its CDN with no version and Mermaid from a CDN pinned only to major version 11, with no subresource integrity. When the user opens the report, whatever code those CDNs serve at that moment runs in the browser. The page holds architecture details of the user's codebase: file names, module names and problem descriptions.
- low input_validation (claude review: model text, it can be wrong): Mermaid is set up with securityLevel "loose". This allows HTML and click handlers inside diagram labels. Labels come from repository content such as module, file and glossary names. If the reviewed repository holds crafted names or glossary text, they could inject markup or script into the locally opened report.

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- Targets: low input\_validation
- After the fix: low mutable\_dependency (claude review): \~ targeted, not re-verified
- After the fix: low input\_validation (claude review): \~ targeted, not re-verified
- Fix id: sha256:d90630cc307a7ed4b1ff28a789839fab781fa3857e978c241c6126ce23cee70a
- Changed: HTML-REPORT.md
