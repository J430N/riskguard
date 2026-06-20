# RiskGuard

**An automated, framework-aligned cyber risk assessment platform for SMBs.**

RiskGuard lets a non-specialist run a credible first-pass cyber risk assessment without GRC consultants. A guided questionnaire produces a transparent, defensible **Cyber Health Score** and a prioritised, actionable remediation roadmap mapped to recognised security controls — and it's repeatable, so an organisation can re-run it after remediation and track posture over time.

> Cyber Storm Centre — Phase 1.1 project. Open-source, MIT-licensed.

---

## The problem

Small and medium-sized businesses sit in a dangerous middle ground: large enough to be attacked, but too small to staff a dedicated security or compliance function. Frameworks like **NIST CSF 2.0**, **CIS Controls v8**, and **ISO/IEC 27001:2022** exist to help, but their volume and abstraction put them out of reach for a generalist IT team. The result: many organisations skip structured risk assessment entirely, or pay for consultancy they can't sustain.

RiskGuard makes that first-pass assessment self-service.

## How it works

1. **Guided assessment** — a conditional-logic questionnaire adapts to organisation size, sector, and cloud-vs-on-premise footprint.
2. **Deterministic scoring** — questionnaire responses establish each control's implementation status. Every gap is tied to a risk scenario scored as `Asset Criticality × Threat Likelihood × Vulnerability Impact`, and the aggregate is normalised to a **0–100 Cyber Health Score** with per-domain grades.
3. **Prioritised roadmap** — gaps become a remediation plan ordered critical → low, mapped to specific controls.
4. **Track over time** — re-run after remediation to measure improvement.

### Scoring is fully deterministic

No score, status, or remediation text is produced by a language model. This keeps results **reproducible and audit-defensible** — essential for a tool that issues security guidance.

### AI is narrow and human-in-the-loop

An optional NLP assist lets a user upload an existing policy document. Using retrieval-augmented generation against the framework text, a lightweight model suggests which questionnaire items the prose supports, returning a **confidence level and the exact source span**. Every suggestion is a draft the user confirms or rejects — **the AI never finalises a mapping or computes risk**. Uploaded documents are processed in-session and not retained, with redaction and a local-model path available for data-sensitive users.

## Framework scope

Phase 1 anchors on **CIS Controls v8 Implementation Group 1 (IG1)** — the safeguard set explicitly designed for SMBs — and cross-maps to **NIST CSF 2.0** and **ISO/IEC 27001:2022** using published mappings, rather than attempting every framework at once.

## Tech stack

| Layer    | Technology              |
| -------- | ----------------------- |
| Frontend | React / Next.js         |
| Backend  | Python (FastAPI)        |
| Database | PostgreSQL              |
| AI       | LLM via API (optional, human-in-the-loop policy mapping only) |

## Deliverables

- An open-source, MIT-licensed codebase: the Next.js front end, the FastAPI back end, and the rule-based scoring engine.
- A versioned, machine-readable **control-and-mapping library** (CIS IG1 ↔ NIST CSF ↔ ISO 27001), reusable by other Cyber Storm Centre projects.
- An **executive reporting dashboard** with radar-chart gap analysis and a downloadable, prioritised PDF action plan.
- A short **whitepaper** documenting the scoring methodology, the framework mappings, and the human-in-the-loop AI design.

## Status

🚧 Early development. Repository scaffolding and core scoring engine are the next milestones.

## License

[MIT](LICENSE)
