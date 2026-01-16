# BuildUnion

**BuildUnion is a system for operational truth in construction.**
BuildUnion is a system-level architecture — not a single AI model.
AI engines are used as constrained reasoning components within the system.


It is designed to reduce uncertainty in complex projects by ensuring that decisions are based on
verifiable, project-specific information — not assumptions or generic AI output.

BuildUnion was shaped by real construction workflows in the Greater Toronto Area,
where information errors translate directly into delays, cost overruns, and compliance risks.

---

## Core Principle

BuildUnion does not replace professional judgment.  
It exists to **protect it**.

The system is built to support decision-makers with clear, traceable context,
while final responsibility always remains with qualified professionals.

---

## How BuildUnion Works

BuildUnion uses a **dual-engine architecture** combined with
**Retrieval-Augmented Generation (RAG)**.

### Engine A — Retrieval & Context
- Retrieves information from:
  - project-specific documents
  - approved technical materials
  - official regulations and codes
- Handles versioning, relevance, and access control
- Separates project data from regulatory sources

### Engine B — AI Reasoning
- Uses AI reasoning engines (such as **Gemini 3**) to interpret retrieved information
- The model receives **only retrieved evidence**, not general world knowledge
- AI output is grounded in source material, not model memory

> If the system cannot retrieve relevant evidence, it does not fabricate an answer.

---

## Truth Standard (Non-Negotiable)

BuildUnion enforces the following invariants:

- **No evidence → no claim**
- Every answer must include **explicit citations**
- Uncertainty and unknowns must be stated clearly
- AI reasoning is always constrained by retrieved sources
- All interactions are logged for auditability

These rules are enforced at the system level, not left to prompt quality.

---

## Output Contract

All system responses follow a structured format:

```json
{
  "answer": "string",
  "citations": [
    {
      "source_type": "project_file | regulation",
      "doc_id": "string",
      "title": "string",
      "version_or_date": "string",
      "location": "page / section",
      "quote": "optional excerpt"
    }
  ],
  "unknowns": ["string"],
  "assumptions": ["string"],
  "recommended_next_checks": ["string"],
  "confidence": "low | medium | high"
}
Responses without citations are rejected by policy.

What BuildUnion Is Not
Not a generic chatbot

Not an autonomous decision-maker

Not a replacement for licensed review or regulatory authority

Not a system that guarantees “100% accuracy” or “zero hallucinations”

BuildUnion is intentionally designed to minimize risk — not to overpromise.

Responsibility & Compliance
BuildUnion supports high operational accuracy through structured retrieval and reasoning,
but final responsibility for interpretation, compliance, and execution
always remains with human professionals.

This boundary is explicit and intentional.

Status
This repository defines the foundational architecture and truth standard for BuildUnion.

Implementation is structured to ensure that system behavior
matches the claims made to users — technically, legally, and ethically.
