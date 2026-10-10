# Changelog

OCPF AL Development Standards Guide, by AJ Ansari and OnlyCopilotFans.

All notable changes to the OCPF AL Development Standards Guide are recorded here. Consumers pin a release tag; the tag name matches the `Version` line in the guide's header.

The guide was previously maintained inside the OnlyCopilotFans BC Agentic Dev Framework, where its history up to and including version 1.11.0.0 (September 27, 2026) is recorded. From this repository on, all changes to the guide are logged here.

## [1.12.0.0] — October 10, 2026

First standalone release. Tag `v1.12.0.0`.

### Added
- **§1.9 Enums, Never Options — and Every Enum's `Extensible` Is a Recorded Decision.** New code
  declares every fixed value set as an `enum`, never an `Option`; `Extensible` is decided per enum
  and written explicitly (it defaults to `false` on an enum); value 0 is the blank value; ordinals
  are permanent; captions carry no comma (AS0087); an API never exposes an enum by ordinal.
- Part 7: four API-page rows and three enum rows replace the three old `DelayedInsert` rows.

### Changed
- **§2.2 Editable vs. Read-Only Pages** aligned with BCQuality and Microsoft's custom-API
  walkthrough: `DelayedInsert = true` on every `PageType = API` page; a read-only page adds
  `Editable = false` with `InsertAllowed`, `ModifyAllowed`, `DeleteAllowed` all `false`; write
  pages follow least privilege; a consumer-supplied `ODataKeyFields` field is never read-only on
  an insertable page. The previous "set exactly one" rule is retired with a note in §2.2.
- §1.3 template comments follow the new §2.2 shape.
- Guide moved to its own repository as the single source of truth. Consumers fetch it at a pinned
  tag instead of carrying a copy.
- Preamble rewritten for a standalone audience: the runbook-relationship section and the
  process map removed; the authoritative-source rule refers to the project's own parameter sheet;
  a short *Scope* note replaces *What is deliberately not here*. In-body references to one build
  process (its step numbers, operating rules, and operations guide) rewritten generically; terms
  that process used to define — Deployment Target, Localization, Symbol Source, the parameter
  sheet — are defined inline on first use.
- Version-history footer points here.

### Unchanged
- Every Part, section, and appendix keeps its existing number. Citations of the form
  *Standards §X.Y* written against version 1.11.0.0 remain valid.
