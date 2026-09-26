# NEPM US Edition v1.0

**Teacher-Controlled AI Assessment Workflow**

NEPM US Edition is a browser-based workflow for AI-assisted assessment generation. It separates AI generation, teacher review and approval, host-side state control, and student-sheet transformation so that the educator remains responsible for the final assessment.

This repository contains the first stable public release of NEPM US Edition.

## Use

Open `index.html` directly in a browser, or publish the repository with GitHub Pages.

Typical workflow:

1. Configure grade band, purpose, subject/topic, target DOK, accommodations, and target standard.
2. Generate the Phase 1 prompt and use it with the selected LLM.
3. Review the Teacher Master Sheet. The teacher decides whether it is acceptable.
4. Use `APPROVE` in the LLM workflow to finalize the reviewed Master Sheet.
5. Paste the approved Master Sheet into NEPM US Edition and generate the Phase 2 authorization prompt.
6. Use the Phase 2 prompt to transform the approved content into a Student Test Sheet.
7. Review the Student Test Sheet before classroom distribution.

Do not enter student names, IDs, IEP/504 information, or other personally identifiable or confidential student information.

## Design principles

- `Instruction ≠ Enforcement`
- `Self-report ≠ Evidence`
- `Shape Check ≠ Identity Verification`
- `Changed Dependency → Derived Artifact Invalidated`
- `State Invalidated → Re-Authorization Blocked`
- `Human Approval → Student-facing Content Freeze`

The host application controls its own state and minimum workflow checks. It does not claim to prove LLM compliance, educational correctness, or the identity of pasted content.

## Verification status

The v1.0 release uses the same tested application logic as **v0.7 RC5 Candidate**. The release changes are limited to release identity/version metadata and copyright/license notices.

Observed verification scope:

- Static verification: PASS within tested scope
- Host Runtime Tests 1–6: PASS within tested paths
- Gemini E2E: PASS in one observed trial
- ChatGPT E2E: PASS in one observed trial

These results do **not** establish universal LLM compliance, future-run reproducibility, provider-wide behavior, assessment quality, educational validity, fairness, answer correctness, or standards alignment.

See `docs/NEPM_US_Edition_v1_0_Verification_Record.docx` for the detailed verification record. The record preserves the verified-candidate provenance: **v0.7 RC5 Candidate → v1.0 release with unchanged tested application logic**.

## Known boundaries

NEPM US Edition is a teacher-controlled workflow, not an autonomous assessment authority. The teacher remains responsible for reviewing generated questions, answers, accommodations, standards alignment, fairness, and the final student-facing artifact.

The Master Sheet shape check is intentionally limited. Passing it means only that minimum structural signals were observed; it does not establish that the pasted artifact is the intended or correct Master Sheet.

LLM behavior can vary by model, provider, version, context, and run. Prompt instructions are not enforcement mechanisms.

## Repository structure

```text
nepm-us-edition/
├── index.html
├── README.md
├── LICENSE
└── docs/
    └── NEPM_US_Edition_v1_0_Verification_Record.docx
```

## License

Copyright © 2026 N. Nakata

NEPM US Edition is licensed under **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)**. See `LICENSE` for details.

This license notice applies to the NEPM US Edition materials distributed in this repository. It is not a claim by N. Nakata to ownership of user-created or AI-generated assessment content merely because that content was produced using this workflow.

## Disclaimer

NEPM US Edition is not affiliated with or endorsed by College Board, ETS, Google, OpenAI, Google DeepMind, or other AI providers. External AI services are governed by their own terms, privacy policies, and behavior.

Human review is required prior to classroom distribution.
