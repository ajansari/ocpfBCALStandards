# Contributing

Thank you for considering a contribution. This guide is small on purpose, so the bar for a change is "verified and necessary," not "interesting."

## Three rules that every change must respect

### 1. Numbering is append-only

Other documents cite rules by number (*Standards §5.4*, *Part 11*, *Appendix B*). A renumbering silently breaks every one of those citations.

- Never renumber a Part, section, or appendix.
- A new rule takes the next free number in its Part. A new Part or appendix takes the next free number or letter.
- To retire a rule, keep its number and heading and replace the body with one line: `*Retired in v2.3.0.0 — superseded by §X.Y.*`
- If a rule moves conceptually, add it at the new number and retire the old one with a pointer.

### 2. Every platform claim is verified and cited

The guide's value rests on the reader never having to wonder whether a rule is still true.

- Cite official Microsoft Learn documentation with the URL and the date you read it, or cite the symbol-file object (table, field, enum, codeunit) you verified against and the Business Central version of those symbols.
- Do not cite blog posts, forum answers, or model memory as the authority for a platform behavior. They can be mentioned as context, never as proof.
- A claim you cannot verify does not go in. Open an issue instead and say what you could not confirm.

### 3. No project parameters

The guide is project-agnostic. It never contains a publisher name, prefix, namespace, object-ID range, version number, or app ID from any real project. Rules refer to "your project's parameter sheet" and leave the values to the reader.

## What makes a good rule

A rule in this guide answers five questions in order:

1. **What is the decision?** One sentence.
2. **What does it depend on?** The project parameter, platform version, or deployment target.
3. **What is the rule?** Stated so it can be applied mechanically, by a person or an agent.
4. **How do you verify it?** Symbols, compiler behavior, Microsoft Learn, or a test.
5. **Why?** The defect, requirement, or platform behavior that made the rule necessary.

If you cannot fill in the fourth and fifth, the rule is not ready.

## Pull requests

- One logical change per pull request. A new rule and a citation refresh are two pull requests.
- Title the PR with the section it touches: `§8.6: clarify locked-caption rule for API queries`.
- In the description, state which of the five questions above the change affects and quote the verification source.
- Update the guide's `Version` and `Last Updated` header lines and add a `CHANGELOG.md` entry.
- Do not bump the major version in a PR; that is a maintainer decision.

## Issues

Use an issue for:

- A rule you believe is wrong, with the evidence.
- A platform change (new BC version, new analyzer, new AppSource requirement) that a rule should reflect.
- A topic the guide should cover and does not, with a sentence on why it belongs here rather than in a pattern library such as [OCPF BC AL Patterns](https://github.com/ajansari/ocpfBCALPatterns) or [alguidelines.dev](https://alguidelines.dev).

## Style

- Plain Markdown, one file, no build step.
- Code samples are minimal and compile against a current Business Central version.
- Write for a reader who will apply the rule without you in the room.
