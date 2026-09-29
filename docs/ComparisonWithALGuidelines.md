# How this guide relates to alguidelines.dev

**By:** AJ Ansari, OnlyCopilotFans  
**Last Updated:** September 28, 2026

This note exists to answer one question objectively: *"The community already has [alguidelines.dev](https://alguidelines.dev). Did we need another AL standards guide, and why not contribute there instead?"*

It is not a battle card. There is no better or worse here, and nothing in it is a criticism of the community project. It is a scope comparison, written so that a reader can decide which document answers the question they actually have.

## The short version

The two documents barely overlap in ambition.

**alguidelines.dev** is a broad, community-owned pattern catalog and style guide. It holds design patterns collected since 2013, coding guidelines from the C/AL era (some pages dated 2015), and the newer AI-oriented *Vibe Coding Rules*. Its strength is breadth of implementation patterns and a long community pedigree.

**This guide** is a narrow, deep, governance-first rulebook for agentic per-tenant-extension development. It does not try to be a pattern catalog. Every naming, ID-allocation, permission-set, translation, upgrade, and field-inclusion decision ties to the project's own intake parameters and is backed by symbol-file or Microsoft Learn verification with a dated citation.

Put as one line: alguidelines.dev answers *"how do I write idiomatic AL patterns?"* This guide answers *"how does an AI agent build a governed, AppSource-grade PTE end to end without a human holding its hand?"* We did not find a published answer to the second question anywhere else.

## Side by side

| Dimension | alguidelines.dev | This guide |
|---|---|---|
| Ownership | Community, hosted under the `microsoft/alguidelines` GitHub organization | AJ Ansari and OnlyCopilotFans, open to contribution under MIT |
| Age and lineage | Design patterns since 2013; C/AL Coding Guidelines published 2015; AI-oriented rules added recently | Written for AL and current Business Central from the start |
| Kind of content | Patterns and style rules | Governance rules with verification procedures |
| Granularity | Independent entries a reader picks from | Numbered rules meant to be applied as a whole, cited by number |
| Verification contract | Varies by page; community-reviewed | Every platform claim cites Microsoft Learn (dated) or a symbol-file reference |
| Primary reader | A developer looking up how to write something | An AI agent, or a person directing one, deciding what to build and how to prove it correct |
| Process coupling | None | None by design; the guide holds rules only and leaves the build sequence to any process |
| Currency | Parts explicitly note they "might fall out of sync as time goes by"; the `CaptionML` guidance conflicts with current AL/XLIFF practice | Rules carry dated citations so staleness is visible rather than silent |

## Topics this guide covers that alguidelines.dev does not

A side-by-side reading found 24 topics in this guide on which alguidelines.dev is silent or nearly silent. Nine are rated high significance:

| # | Topic | Why it matters | Where |
|---|---|---|---|
| 1 | Permission-set Role-ID collision analysis | Extensions that share a prefix produce colliding Role IDs; namespaces mask the collision until deployment | Part 5, §5.4 |
| 2 | Editable versus read-only API page matrix | Page editability follows data mutability, and `DelayedInsert` rules follow from that | Part 2, §2.2 |
| 3 | Localization-aware field-ID range logic | W1 ranges (1–9,999 and 99,000,000+) differ from ranges reserved by specific localizations | Part 5, §5.5 |
| 4 | Growth-buffer math for object-ID allocation | The percentage table and tail-block reservations keep a module from running out of IDs | Part 5, §5.2 |
| 5 | Parent–child page filter-group defect analysis | Child records created in the parent's context lose the parent key and vanish behind a filter; from real client defects | Part 11, §11.1 |
| 6 | Translation state governance | Locked versus translatable captions and the full state model from source string to approved translation | Part 8, §8.3, §8.6, §8.7 |
| 7 | Symbol-file verification as mandatory discipline | Never trust model memory or a documentation page when the symbols are on disk | Appendix B, §3.4 |
| 8 | Upgrade and data-migration governance | Upgrade tags, the two-version deprecation cycle, and upgrade testing as a gate | Part 9 |
| 9 | The agentic lifecycle architecture itself | The split between a process document and a rules document, zero-error gates, pre-flight checklists an agent runs on its own output | Preamble and throughout |

The remaining fifteen are lower-significance items inside the same Parts: individual anti-patterns, API naming character limits, reserved-keyword conflicts, terminology verification against Microsoft's own translations, language support by market, gap-analysis table classes, and the AppSource manifest checklist.

## Where alguidelines.dev is stronger

Two areas, both deliberately outside this guide's scope:

- **Design-pattern breadth.** Dozens of implementation patterns refined by the community over more than a decade. This guide has no ambition to replicate them. For bug-derived, verified patterns that pair with this guide, see [OCPF BC AL Patterns](https://github.com/ajansari/ocpfBCALPatterns).
- **AL-Go and test-project workspace structure.** How to lay out a test project and an AL-Go workspace is out of scope here and belongs to the reader's build process.

## Why not contribute this to alguidelines.dev?

We considered it seriously. Three reasons the answer was no:

1. **Different premise.** A catalog holds independent entries. A rulebook holds rules that reference each other by number and are applied as a whole by an agent that does not get to pick. Splitting this guide into catalog entries would lose the property that makes it useful to an agent.
2. **Different verification contract.** Dated citations on every claim and append-only numbering are promises that downstream runbooks depend on. That is a heavier editorial obligation than a community catalog should be asked to take on.
3. **Different release cadence.** Consumers pin this guide at a tag. The tag has to mean something specific to the build process that consumes it, which requires a repository with its own release discipline.

Where a rule in this guide generalizes into a pattern that belongs in the community catalog, contributing it upstream is welcome. The two documents are complementary: one is a community pattern reference, the other is an agentic governance rulebook for building compliant, symbol-verified, translation-governed, upgrade-safe Business Central extensions end to end.

## Closing position

alguidelines.dev occupies the niche of a community style guide and pattern library: broad, general-purpose, historically rooted in C/AL and NAV-era design patterns, now extended with AI-assistant-oriented style rules. Its strength is breadth and pedigree; its known limitation is that parts of its content are explicitly dated and in at least one documented instance conflict with current practice.

This guide occupies a different and narrower niche: agentic, AI-assisted, per-tenant-extension development with full lifecycle governance. Where alguidelines.dev is silent, this guide is deep. Where this guide is deliberately silent, it defers by design to pattern libraries and to the reader's own build process rather than duplicating territory the community already covers well.
