## SCIS — Structured, Contract-Driven, Deterministic Software Framework

### One-Sentence Definition
SCIS is a deterministic, map-first software framework where all structure, behavior, metrics, and evolution are explicitly declared, role-bounded, and phase-locked, enabling humans and LLMs to design, build, support, reconstruct, and evolve software without guessing, scanning, or loss of intent.

---

### Why SCIS Exists
SCIS exists to eliminate systemic failure modes in modern software and LLM-assisted development, including:
- Lost design intent due to context limits and code sprawl
- Hallucinated or inferred structure
- Unsafe, implicit edits and side effects
- Undocumented legacy behavior
- Support and operations dependent on logs, folklore, or reproduction
- Metrics that influence decisions without declared authority

SCIS replaces inference with **explicit declaration and enforced observability**.

---

### Core Worldview
- **Software is not code-first**  
  Code is an implementation artifact, never the source of truth.
- **Maps are authoritative**  
  Humans and LLMs operate on declared maps, not inferred structure.
- **Nothing implicit is trusted**  
  If something matters, it must be declared, identified, and measured.
- **Determinism is a safety requirement**  
  Non-determinism is treated as a defect, not a convenience.

---

### Fundamental Axioms
1. If it exists, it is declared  
2. If it is declared, it is ID-addressable  
3. If it can change, fail, or be depended on, it is measured  
4. If it is measured, its role is explicit  
5. If authority is explicit, action is safe  
6. If action is safe, evolution is possible

---

### Maps-First Architecture
Maps define:
- Files
- Components (CA)
- Non-components (NCA)
- Logic
- Dependencies
- Tools
- Databases
- APIs
- Metrics

Runtime behavior and code **must conform to maps**, never the reverse.

**Key Metrics**
- Map coverage ratio
- Map-to-runtime drift
- Undeclared reference rate

---

### Components and Non-Components

#### Components (CA)
Contracted units with declared:
- Purpose
- Inputs / outputs
- Constraints
- Dependencies

Mandatory metrics include:
- Contract compliance
- Input/output violations
- Dependency failures
- Latency / SLA breaches
- Determinism variance

#### Non-Components (NCA)
Configs, schemas, datasets, assets, helpers, templates.

Mandatory metrics include:
- Access frequency
- Mutation history
- Promotion signals

Nothing is “just config.”

---

### Contracts Over Code
Behavior is defined by **NCCF contracts**, not by reading code.
Code implements contracts and may be replaced without redefining intent.

**Key Metrics**
- Contract compliance rate
- Contract-to-code drift

---

### Deterministic Lifecycle & Phases
SCIS enforces:
- Explicit lifecycle stages
- Phase-locked access
- No future-stage reads or writes

Violations are measured and blocked.

---

### Append-Only Evolution
All changes to:
- Maps
- Logic
- Contracts
- Metrics
are append-only, traceable, and reversible.

**Key Metrics**
- Change traceability depth
- Rollback frequency
- Upgrade reversibility time

---

### Role-Aware Metrics System
Metrics are first-class artifacts with declared roles:

- **Diagnostic** – localize failures
- **Evolutionary** – guide improvement
- **Guardrail** – prevent unsafe action
- **Validation** – prove claims
- **Reporting** – communicate status

Rules:
- Every metric has exactly one declared role
- Metrics may not influence actions outside their role
- Unauthorized metric influence is a SCIS violation

---

### Control Plane (A0)
The control plane governs:
- Schemas
- Enforcement rules
- Tools
- Metric roles
- LLM behavior

Supports:
- New system construction
- Legacy reconstruction
- Shared utilities

---

### Programs (A1+)
Programs are:
- Self-contained
- Language-agnostic
- Independently evolvable
- Fully observable

Cross-program dependencies are declared and enforced.

---

### Legacy Reconstruction
Legacy systems are rebuilt deterministically from partial signals.
Unknown behavior is measured, not ignored.

---

### LLM & Human Roles
- **LLMs:** Suggest, generate, validate
- **Humans:** Approve, commit, run
- **SCIS:** Enforce structure, determinism, and metric authority

LLMs are read-only by default.

---

### Memory Without Context Explosion (MEM)
Canonical, token-efficient knowledge layer enabling:
- Accurate recall
- Controlled evolution
- No re-scanning or rediscovery

---

### Strategic Significance
SCIS is not just a framework for writing code —  
it is a framework for **making software safe to understand, operate, and evolve indefinitely**, even with LLMs in the loop.

It underpins:
- ASD (architecture decisions)
- SDDF (design decisions & change impact)
- Policy-adherent automation
- Large document processing
- Enterprise AI systems requiring auditability and determinism
