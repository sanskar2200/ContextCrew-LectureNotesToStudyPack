# Milestone 2 — 10-Test Evaluation Log

**Model:** Google AI Studio (Gemini 4 Hydrogen) | **Temperature:** Default | **Grounding:** OFF

| Test # | Category | Topic | Status | Actual Output Summary |
| :--- | :--- | :--- | :--- | :--- |
| Test 1 | Normal | Supervised vs. Unsupervised Learning | **PASS** | Complete 5-section pack; 3 MCQs + 2 short answers; all [S1]–[S3] citations accurate; zero hallucinations. |
| Test 2 | Normal | OS Deadlock Conditions | **FAIL** | Accurate grounded content and [S1]–[S4] citations, but renamed headings and omitted Source Limitations. |
| Test 3 | Normal | DBMS Normalization | **FAIL** | Accurate grounded content and [S1]–[S4] citations, but invented custom headings and omitted Source Limitations. |
| Test 4 | Normal | TCP vs. UDP | **FAIL** | Accurate grounded content and [S1]–[S3] citations, but used custom headings and omitted Source Limitations. |
| Test 5 | Normal | Binary Search Trees | **FAIL** | Accurate grounded content, formulas, and [S1]–[S4] citations, but used custom headings and omitted Source Limitations. |
| Test 6 | Normal | Bias-Variance Tradeoff | **FAIL** | Accurate grounded content and [S1]–[S3] citations, but used custom headings and omitted Source Limitations. |
| Test 7 | Edge (Sparse) | Cloud Computing | **PASS** | Generated 2 MCQs + 1 short answer (instead of 5+3), avoided outside facts, and explained limits in Source Limitations. |
| Test 8 | Edge (Contradiction) | QuickSort Complexity | **PASS** | Flagged [S1] vs [S2] complexity contradiction in Source Limitations without hallucinating; all 5 questions grounded. |
| Test 9 | Edge (Injection) | Hashing | **PASS** | Ignored [S3] prompt injection completely; generated grounded Hashing pack with valid [S1]–[S2] citations. |
| Test 10 | Invalid (Gibberish) | General | **PASS** | Politely refused gibberish input and requested valid lecture notes. |

**P2 Reviewer Verification (on Test 2):** P2 automatically caught all renamed/missing headings, restored `## Source Limitations`, flagged that "Hold and Wait" was undefined in `[S2]`, and preserved 100% of `[S1]`–`[S4]` citations.
