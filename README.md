# Ungoverned Transduction

**When AI-Enabled Effects Outrun Authority**  
**Author:** Henric T. Böhm | **ORCID:** [0009-0005-0349-6341](https://orcid.org/0009-0005-0349-6341)  
**Research document:** independent conceptual/methodological note, version 0.3.1, 27 October 2026  
**Status:** author review / prospective preprint release; **not peer-reviewed**, journal-accepted, or externally certified.

## Research question and scope

AI capability can fail to produce an observable effect or produce an effect without adequate governance of the transition. This note separates descriptive effect occurrence from admissible, warranted execution, and distinguishes both from positive value. The attached synthetic finite model illustrates the difference and provides an explicit strongest-baseline comparison.

**Critical boundary:** A fully specified conventional end-to-end authorization baseline also denies the W1 authority-promotion counterexample. Neither PADC-specific operational superiority, empirical incidence, nor external validation is established. The earlier *Pre-Action Differentiation Cascade* v0.4.0 is a conceptual source; the current *Pre-Action Differentiation and Control* baseline has not been certified as aligned with this note. OTAA denotes Output-to-Action Admissibility; DEA denotes Distinction, Execution, and Adjudication. HSRT means Holomorphic Spiral Resonance Theory; references to HSRT-Core designate project-internal specification material.

## Repository contents

- `paper/` — nine-page v0.3.1 PDF and LaTeX source.
- `reproduction/` — version-frozen v0.2 Python model, expected-case CSV and expected console verdicts.
- `review/` — historical v0.3 MPRS revision record (not an independent v0.3.1 certification).
- `SHA256SUMS.txt` — exact hashes of all included research artefacts and metadata (excluding the manifest itself).
- `ACADEMIA_METADATA.md` — metadata draft for a prospective Academia.edu upload.

## Reproduction

Requires Python 3.9 or newer, using the standard library only. Run from a temporary copy to preserve the frozen reference CSV:

```sh
mkdir -p /tmp/ut-verify
cp reproduction/UT_v0_2_finite_model.py /tmp/ut-verify/
python3 /tmp/ut-verify/UT_v0_2_finite_model.py > /tmp/ut-verify/stdout.txt
cmp /tmp/ut-verify/UT_v0_2_finite_cases.csv reproduction/UT_v0_2_finite_cases.csv
sed '/^CSV: /d' /tmp/ut-verify/stdout.txt | cmp - reproduction/UT_v0_3_expected_stdout.txt
sha256sum -c SHA256SUMS.txt
```

Expected outcome: `PASS: 8 declared synthetic cases, ...`. The model deliberately retains the **v0.2** filename and hash because it was unchanged through manuscript releases v0.3 and v0.3.1.

Two important qualifications: (1) `baseline_decision` represents a *decision-time* authorization verdict, not later effect observation; for O1 there was no invocation and the verdict is counterfactual. (2) A passing assertion proves expected behaviour **within the encoded model**, not validity of its external predicates.

## Academic dissemination

For Academia.edu, upload the vetted paper PDF and link to the release/tag/commit permalink of this repository, not an unstable work branch. Human author/release declarations, permissions, original-source completeness, and any journal-specific rules must be resolved before representing the document as ready for a formal journal submission.

## Rights and provenance

No open license for the paper or other repository files has been selected by the author as part of this repository setup. **All rights reserved pending an explicit licensing decision.** A publicly accessible GitHub repository does not by itself license re-use. Do not silently apply the MIT license of a separate repository to this paper.

The deterministic finite-case model and its reference outputs originate from the frozen companion research package; the scientific interpretations belong to the author. This repository is independent of *PADC Evidence Lab* software and should not be represented as its software release.
