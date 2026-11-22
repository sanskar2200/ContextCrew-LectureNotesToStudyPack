# Lecture Notes to Study Pack Generator

**Team:** Context Crew (PE-B25-42 | Batch 34)  
**Members:** Sanskar Patidar, Dhruv Bhoi  
**Faculty Mentor:** Dr. Saurabh Shrivastava  

## Overview
A two-stage LLM prompt pipeline built in Google AI Studio (**Gemini 4 Hydrogen**, Temperature: Default, Grounding: OFF) that converts raw lecture notes into a structured, exam-ready study pack with strict `[S#]` source citations and zero outside hallucination.

## Live Prototype & How to Run
- **Google AI Studio Prototype:** [Open Context Crew P1 Prototype](https://aistudio.google.com/app/prompts?state=%7B%22ids%22:%5B%2214kGuDk-lSN63LNp7fwo6JpQUhRyIfbLb%22%5D,%22action%22:%22open%22,%22userId%22:%22103755513252514862239%22,%22resourceKeys%22:%7B%7D%7D&usp=sharing)
- **Demo Reel:** [Watch on YouTube](https://youtu.be/1KoOh4T02q0)

### How to Run
1. Open the Google AI Studio prototype link above (sign in with any Google account; no access request needed).
2. Confirm model settings on the right panel: **Gemini 4 Hydrogen**, **Grounding with Google Search: OFF**, **Temperature: Default**.
3. Replace the `SOURCE_NOTES` block in the user prompt with your own tagged notes (`[S1]`, `[S2]`, ...) and click **Run**.

## Pipeline Architecture
1. **P1 — Study Pack Generator:** Converts tagged `SOURCE_NOTES` (`[S1]`, `[S2]`, ...) into a 5-section study pack (`Summary`, `Key Terms`, `Practice Questions`, `Answer Key and Explanations`, `Source Limitations`).
2. **P2 — Grounding & Quality Reviewer:** Audits the draft against `SOURCE_NOTES`, flags unsupported claims or heading mismatches, logs changes, and outputs a corrected study pack.

## Repository Structure
- `prompts/v1/` — Initial baseline prompt (unstructured, no citations)
- `prompts/final/` — Final production `P1` and `P2` prompts
- `test-data/` — 10 test inputs (6 normal, 3 edge, 1 invalid) and actual outputs
- `docs/` — Milestone 2 report and technical documentation

## Evaluation Summary (10 Test Runs)
- **Result:** 5 Pass / 5 Fail (100% factual grounding & citation accuracy across all 10 runs; 5 failures were strictly due to heading-format drift when headings were not enforced in System Instructions, which `P2` resolved cleanly).
- **Edge & Invalid Cases:** Passed sparse notes (Test 7), contradictory notes (Test 8), embedded prompt injection (Test 9), and gibberish input (Test 10).
