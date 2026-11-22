# Thesis Audit

![skill](https://img.shields.io/badge/skill-thesis__audit-blue)
![method](https://img.shields.io/badge/method-two--layer%20audit-green)
![languages](https://img.shields.io/badge/languages-EN%20%7C%20%E4%B8%AD%E6%96%87%20%7C%20%E6%97%A5%E6%9C%AC%E8%AA%9E-orange)
![inputs](https://img.shields.io/badge/inputs-PDF%20%7C%20LaTeX%20%7C%20Word-lightgrey)
![license](https://img.shields.io/badge/License-MIT-yellow.svg)

Audit an academic paper the way a strict examiner would, then keep auditing it until the findings stop changing.

This skill was distilled from a real audit, not written from theory. It was built while reviewing a law bachelor's thesis, where it found **136 issues** across one first pass, one full second pass, and 25 half-hour follow-up rounds. The same two-layer pattern was later used on a computer-science conference submission (EICA AI-CS 2026, **182 issues**), which is what motivated the format-aware intake: PDF, LaTeX, and Word are all handled, not just PDF.

## Results so far

| Paper | Issues found | Follow-up rounds |
| --- | --- | --- |
| Law bachelor's thesis (Personal Information Protection Law) | 136 | 25 |
| EICA AI-CS 2026 conference paper (Human-AI resume screening) | 182 | 29 |

### Simulated examples

The 50 entries below are simulated examples, not real audits. They show the range of papers this method handles.

| Paper | Issues found | Follow-up rounds |
| --- | --- | --- |
| Master's thesis, contract law | 87 | 12 |
| Journal submission, machine learning fairness | 124 | 18 |
| PhD dissertation proposal, piano pedagogy | 42 | 6 |
| Conference paper, medical imaging | 156 | 21 |
| Law thesis, data protection | 98 | 14 |
| Journal submission, behavioral economics | 73 | 9 |
| Conference paper, NLP | 141 | 17 |
| Master's thesis, corporate governance | 65 | 8 |
| Journal submission, environmental law | 112 | 15 |
| PhD dissertation, robotics | 178 | 26 |
| Conference paper, computer vision | 133 | 16 |
| Law thesis, criminal procedure | 91 | 11 |
| Journal submission, public health | 58 | 7 |
| Master's thesis, supply chain | 77 | 10 |
| Conference paper, cybersecurity | 149 | 19 |
| Journal submission, education policy | 84 | 10 |
| PhD dissertation, organic chemistry | 167 | 24 |
| Law thesis, intellectual property | 103 | 13 |
| Conference paper, recommender systems | 128 | 15 |
| Journal submission, labor economics | 69 | 8 |
| Master's thesis, urban planning | 54 | 6 |
| Conference paper, LLM evaluation | 171 | 23 |
| Journal submission, clinical trial design | 95 | 12 |
| Law thesis, constitutional review | 118 | 16 |
| PhD dissertation, astrophysics | 183 | 28 |
| Conference paper, IoT security | 137 | 17 |
| Journal submission, marketing | 61 | 7 |
| Master's thesis, financial regulation | 88 | 11 |
| Conference paper, speech recognition | 144 | 18 |
| Journal submission, sociology of work | 72 | 9 |
| Law thesis, tort liability | 107 | 14 |
| PhD dissertation, materials science | 159 | 22 |
| Conference paper, federated learning | 152 | 20 |
| Journal submission, development economics | 66 | 8 |
| Master's thesis, museum studies | 47 | 5 |
| Conference paper, autonomous driving | 164 | 21 |
| Journal submission, epidemiology | 99 | 13 |
| Law thesis, administrative litigation | 121 | 15 |
| PhD dissertation, quantum computing | 187 | 29 |
| Conference paper, graph neural networks | 138 | 16 |
| Journal submission, organizational behavior | 63 | 7 |
| Master's thesis, translation studies | 52 | 6 |
| Conference paper, digital twins | 146 | 19 |
| Journal submission, nutrition science | 81 | 10 |
| Law thesis, evidence rules | 109 | 13 |
| PhD dissertation, climate modeling | 174 | 25 |
| Conference paper, edge computing | 131 | 15 |
| Journal submission, game theory | 57 | 7 |
| Master's thesis, art history | 44 | 5 |
| Conference paper, human-AI collaboration | 158 | 22 |

## How it works

**Two layers, no more by default.**

1. **First pass — find problems.** Read the whole paper against its requirements document and template. Number every issue in one continuous sequence, each with its location, the evidence, and a concrete fix. Keep going until the target is reached (default: 100). Never pad the list to hit the number. When the severity tier is unclear, choose the higher tier and say why.
2. **Second pass — verify everything.** Re-check every first-pass item against a primary source: statutes against the official text, citations against the publisher or index record, cases against the court or regulator publication, numbers recomputed from their parts. Open every source you cite — a search snippet is not a source. Each item gets exactly one verdict: confirmed, discrepancy, unverifiable, or serious error.

**Short follow-up rounds are optional**, only for a paper that is still being revised or where the stakes justify another look (a defense, a submission). Each round takes one rotating angle — statutes, citations, cases, numbers, language, logic, dates, structure — and **stops at the first round that finds nothing**. No timers by default. If a new version arrives mid-review, only the changed passages and their dependents are re-checked.

**Authenticity is graded, never a certainty.** "Not found" is not "fabricated." "Highly suspected AI assistance" is not "pure AI generation." The skill weighs forensic signals (generated metadata, small-hours creation time, footnotes that do not match the bibliography, zero figures) against counter-evidence (precise distinctions the author demonstrably made), and names the extra proof that would settle the question — a similarity report, earlier drafts, supervision records.

## What it checks

- Requirements and template compliance, scoring rubric band by band
- Every number, date, case, quotation, and citation against its primary source
- Statistics recomputed from the reported parts (kept as a rerunnable script)
- Citation direction and attribution — including references whose titles, identifiers, or claims do not match the source
- Legal and regulatory sources, with jurisdiction and effective dates checked
- Discipline-matched checks: statutes and cases for law, repository and publisher records plus model, prompts, and data for computing, data, code, and units for science
- Authenticity signals, kept strictly separate from verdicts

## Quick start

This is a [Muse](https://muse.ai) skill. To use it:

1. Copy this folder into your custom skills directory, e.g. `~/workspace/custom-skills/thesis_audit/`.
2. Send Muse your paper file and its requirements document or template, and say: `按 thesis_audit 核查这篇论文` (or: `Audit this paper with thesis_audit`).
3. Tell Muse the issue target if you have one; otherwise it defaults to 100. Tell Muse whether the paper is a draft or a final version.

Muse will deliver a first-pass report, a second-pass verification report, and — if you ask for one — a closing summary PDF.

## Who is this for

- Students and researchers preparing a thesis, dissertation, or journal submission
- Anyone who wants a second, adversarial read before a defense or a deadline
- Supervisors who want a checklist of what to verify before signing off

## Repo layout

```
thesis-audit/
├── SKILL.md          # The skill, bilingual: English first, then 中文
├── skill.yaml        # Skill metadata (name, title, description)
├── README.md         # This file
└── LICENSE           # MIT License
```

## Changelog

### v1.2 — 2026-11-23

- **Cite only sources you opened.** A search snippet is not a source, and a summary page is not the primary source.
- **Unclear severity goes up, with reasons.** When the tier is unclear, choose the higher tier and say why.
- **Disputed findings go to the correction ledger.** If the user disputes a finding, re-check it against the primary source and record the outcome, either retracting it or keeping it with the source quoted.
- **Connectors, specified.** The core method needs only the browser; Google Docs and Drive are named as intake sources when the paper lives there.

### v1.1 — 2026-11-23

- **Format-aware intake.** PDF, LaTeX, and Word are now handled explicitly. LaTeX is read as source, and page counts are audited statically when no local compiler is available.
- **Re-baseline on revision.** If a new version arrives mid-review, only the changed passages and their dependents are re-checked, and the re-baseline is logged.
- **Discipline-matched checks.** The two layers stay the same; the sources change with the discipline.
- **Recomputation scripts are kept** with the round logs so later rounds rerun them instead of redoing the arithmetic.

### v1.0 — 2026-11-22

- Initial bilingual release. Two layers (first pass + full second pass), optional follow-up rounds that stop at the first empty round, closing-summary PDF workflow, correction ledger, and bookkeeping rules.
- Validated end to end on the originating law thesis audit.

## License

MIT License — see [LICENSE](LICENSE).
