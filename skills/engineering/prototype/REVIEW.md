# esr review: skills/engineering/prototype

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: mattpocock/skills
- Upstream commit reviewed: 5863806dd4e15c63174bee4e7515a4256792ecfa
- Skill tree reviewed: e41d92e171f074a2b6887d8f6faca4a15c83d1ca
- Date: 2026-11-14
- Choice: keep

## What it does (claude review, model text)

    Guides the agent to build throwaway prototypes that answer a design
    question. For logic questions it builds a single self-contained HTML demo
    with a pure state module. For UI questions it builds several switchable UI
    variants on one route. When the prototype is done, it commits the prototype
    to a throwaway branch.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low other (claude review: model text, it can be wrong): After the prototype has answered its question, the skill tells the agent to commit the prototype to a throwaway branch and to leave a context pointer on the implementation issue. It also says to record the verdict in the issue or in a commit. Posting on an issue tracker acts under the user's identity on a third-party service, and the skill does not say which tracker or how it is reached. The content shows no hidden or malicious intent. This is a normal development workflow step.

## Fix applied

- none
- Fix offered: hygiene, checked

## Claude Code reported

During this run Claude Code reported these values, which differ from what esr expects. None of them lets the reviewer act; the review went ahead.

- init.plugins: cc-plugin-privacy@builtin
