# Thesis Audit

![skill](https://img.shields.io/badge/skill-thesis__audit-blue)
![method](https://img.shields.io/badge/method-two--layer%20audit-green)
![languages](https://img.shields.io/badge/bilingual-EN%20%2B%20%E4%B8%AD%E6%96%87-orange)
![inputs](https://img.shields.io/badge/inputs-PDF%20%7C%20LaTeX%20%7C%20Word-lightgrey)

Audit an academic paper the way a strict examiner would, then keep auditing it until the findings stop changing.

This skill was distilled from a real audit, not written from theory. It was built while reviewing a law bachelor's thesis, where it found **136 issues** across one first pass, one full second pass, and 25 half-hour follow-up rounds. The same two-layer pattern was later used on a computer-science conference submission (EICA AI-CS 2026, **182 issues**), which is what motivated the format-aware intake: PDF, LaTeX, and Word are all handled, not just PDF.

## How it works

**Two layers, no more by default.**

1. **First pass — find problems.** Read the whole paper against its requirements document and template. Number every issue in one continuous sequence, each with its location, the evidence, and a concrete fix. Keep going until the target is reached (default: 100). Never pad the list to hit the number.
2. **Second pass — verify everything.** Re-check every first-pass item against a primary source: statutes against the official text, citations against the publisher or index record, cases against the court or regulator publication, numbers recomputed from their parts. Each item gets exactly one verdict: confirmed, discrepancy, unverifiable, or serious error.

**Short follow-up rounds are optional**, only for a paper that is still being revised or where the stakes justify another look (a defense, a submission). Each round takes one rotating angle — statutes, citations, cases, numbers, language, logic, dates, structure — and **stops at the first round that finds nothing**. No timers by default.

**Authenticity is graded, never a certainty.** "Not found" is not "fabricated." "Highly suspected AI assistance" is not "pure AI generation." The skill weighs forensic signals (generated metadata, small-hours creation time, footnotes that do not match the bibliography, zero figures) against counter-evidence (precise distinctions the author demonstrably made), and names the extra proof that would settle the question — a similarity report, earlier drafts, supervision records.

## Quick start

This is a [Muse](https://muse.ai) skill. To use it:

1. Copy this folder into your custom skills directory, e.g. `~/workspace/custom-skills/thesis_audit/`.
2. Send Muse your paper file and its requirements document or template, and say: `按 thesis_audit 核查这篇论文` (or: `Audit this paper with thesis_audit`).
3. Tell Muse the issue target if you have one; otherwise it defaults to 100. Tell Muse whether the paper is a draft or a final version.

Muse will deliver a first-pass report, a second-pass verification report, and — if you ask for one — a closing summary PDF.

## What it checks

- Requirements and template compliance, scoring rubric band by band
- Every number, date, case, quotation, and citation against its primary source
- Statistics recomputed from the reported parts (kept as a rerunnable script)
- Citation direction and attribution — including references whose titles, identifiers, or claims do not match the source
- Legal and regulatory sources, with jurisdiction and effective dates checked
- Discipline-matched checks: statutes and cases for law, repository and publisher records plus model, prompts, and data for computing, data, code, and units for science
- Authenticity signals, kept strictly separate from verdicts

## Repo layout

```
thesis-audit/
├── SKILL.md      # The skill, bilingual: English first, then 中文
├── skill.yaml    # Skill metadata (name, title, description)
└── README.md     # This file
```

## Changelog

### v1.1 — 2026-11-23

- **Format-aware intake.** PDF, LaTeX, and Word are now handled explicitly. LaTeX is read as source, and page counts are audited statically when no local compiler is available.
- **Re-baseline on revision.** If a new version arrives mid-review, only the changed passages and their dependents are re-checked, and the re-baseline is logged.
- **Discipline-matched checks.** The two layers stay the same; the sources change with the discipline.
- **Recomputation scripts are kept** with the round logs so later rounds rerun them instead of redoing the arithmetic.

### v1.0 — 2026-11-22

- Initial bilingual release. Two layers (first pass + full second pass), optional follow-up rounds that stop at the first empty round, closing-summary PDF workflow, correction ledger, and bookkeeping rules.
- Validated end to end on the originating law thesis audit.

## License

To be decided.
