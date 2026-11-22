# Changelog

## v1.0 — 18 Nov 2026 (Baseline)
- Created single unguided prompt with no system instructions.
- **Issues observed:** Dropped `[S#]` citations, leaked outside knowledge (labelled Regression/Classification as supervised tasks despite notes not stating so), and omitted answer explanations.

## v2.0 — 20 Nov 2026 (Structured Grounded Generator — P1)
- Added strict system instructions, `[S#]` inline citation rules, 5 mandatory headings, and edge/invalid input handling.
- **Issues observed:** Achieved 100% factual grounding across all 10 tests, but drifted on heading names and omitted `Source Limitations` in Tests 2–6 when exact headings were not repeated in system instructions.

## v3.0 — 22 Nov 2026 (Two-Stage Pipeline — P1 + P2)
- Added `P2` (Grounding & Quality Reviewer) to audit drafts against `SOURCE_NOTES`.
- Verified on Test 2: `P2` caught all renamed/missing headings, restored `## Source Limitations`, and flagged undefined terms without hallucinating.
