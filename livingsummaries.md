
https://raw.githubusercontent.com/MrTrentDaVinci/reference/main/livingsummaries.md

# Living Summaries

## Meta
- Author: Warren Whitlark
- Purpose: Canonical internal memory for LLM grounding
- Update cadence: As-needed, append-only where possible

# Living Summaries TOC
1. ASD
2. Golden SLM 
3. Tag
4. System Design Decision Framework
5. Email Routing
6. Document Processing
7. SCIS
8. Program Builder
9. 

...

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

8.
## ProgramBuilder (PB) — Hybrid LLM–SLM Software Assembly System

### One-Sentence Definition
ProgramBuilder (PB) is a deterministic software construction system where external LLMs design intent, a non-creative SLM mechanically assembles code from RGB building blocks with embedded rules, and Agent Matrices validate both specification and output—ensuring correctness, safety, and repeatability by design.

---

### System Identity
- **Name:** ProgramBuilder (PB)
- **Type:** Python desktop application (PyQt6 GUI)
- **Role:** Automated software assembly from structured specifications
- **Foundation:** SCIS 4.x (maps-first, ID-based, deterministic)
- **Core Insight:** Design is creative; assembly must not be

---

### Core Philosophy
PB enforces a strict separation of concerns:

- **External LLMs** design *what* should be built
- **Users** approve intent and fixes
- **SLM Orchestrator** assembles *how* it is built — mechanically
- **Agent Matrices** validate structure and correctness
- **PB** executes, tests, reports, and applies approved fixes

At no point is creative reasoning allowed inside the assembly engine.

---

### High-Level Flow
External LLM + User  
→ Design **Development Summary (DS)** using RGB references  
→ **Agent Matrix 1** validates DS structure & rule inheritance  
→ **SLM Orchestrator** assembles code with enforced rules  
→ **Agent Matrix 2** validates generated code  
→ **Testing**  
→ Success or controlled fix cycle

---

### Key Innovation: Rules Embedded in RGBs
PB’s defining breakthrough is **rule inheritance via RGB selection**.

- Every RGB represents an atomic code element
- Each RGB carries **embedded enforced rules**
- Selecting an RGB automatically inherits its rules
- Rules do **not** need to be manually listed in the DS
- Only *overrides* (extended rules only) may be specified

This eliminates forgotten rules, hallucinated constraints, and implicit assumptions.

---

### RGB System
- **RGB (0–255)** = atomic code element
- **Four Zones:**
  - 0–63: Commands / Meta
  - 64–127: Keywords & structural syntax
  - 128–191: Pre-assembled components
  - 192–255: Utilities & auxiliaries
- Each RGB includes:
  - Code template
  - Parameters
  - Embedded rules (core / extended)
  - Validation stage

RGBs are the *only* building blocks SLM may use.

---

### Development Summary (DS)
PB consumes a strict **11-section Development Summary**, which defines:

- Project metadata
- Dependencies
- SCIS phase/file structure
- Component definitions (via RGB lists)
- Dependency graph
- Build order
- Validation & testing requirements
- Mandatory components
- Final metadata & checksums

The DS specifies **intent**, not assembly instructions.

---

### Rule System
#### Core Rules (🔒)
- Safety-, correctness-, and security-critical
- Never configurable
- Always enforced

#### Extended Rules (⚙️)
- Quality, style, or project-specific
- Configurable via DS Section 1
- May be auto-applied by SLM

Rules are enforced based on:
- Their declared role
- Their declared validation stage
- Their RGB origin

---

### Agent Matrix Architecture
#### Agent Matrix 1 — Specification Validator
Validates:
- DS structure and JSON integrity
- RGB existence and zone correctness
- Automatic rule inheritance
- Allowed rule overrides (extended only)
- SCIS coordinates and component IDs
- Dependency integrity and mandatory components

Rejects invalid specs before assembly begins.

#### Agent Matrix 2 — Code Validator
Validates:
- Python syntax
- All inherited rules
- Core rule compliance
- Extended rule compliance (per mode)
- Naming, indentation, security, structure
- Alignment with DS intent

Reports violations with **RGB + rule context**.

---

### SLM Orchestrator (Inside PB)
The SLM is **mechanical by design**.

**It DOES:**
- Fetch RGB templates and embedded rules
- Substitute parameters
- Auto-generate docstrings, headers, markers
- Enforce indentation, naming, imports
- Validate syntax
- Apply allowed rule overrides

**It NEVER:**
- Chooses RGBs
- Designs logic
- Adds features
- Overrides core rules
- Makes architectural decisions

---

### Build–Test–Fix Cycle
1. External LLM designs DS
2. Agent Matrix 1 validates spec
3. SLM assembles code
4. Agent Matrix 2 validates output
5. PB runs tests
6. If failure:
   - Error reports include RGB + rule origin
   - User + LLM design a fix spec
   - Cycle repeats deterministically

---

### Determinism Guarantees
PB guarantees:
- No hallucinated rules
- No implicit structure
- No unsafe edits
- No creative assembly
- No silent failures

Given the same DS and RGB database, PB produces the same result.

---

### User Interface (PyQt6)
- Section-based DS input
- Validation and assembly progress
- Rule inheritance visibility
- Error reports with copyable RGB/rule context
- Session resume and auto-save

The GUI is an observability surface, not a decision-maker.

---

### Relationship to SCIS
- PB **implements SCIS principles**
- SCIS defines structure, phases, IDs, and determinism
- PB is the **execution engine** for SCIS-compliant software construction
- Agent Matrices act as SCIS enforcement points

PB cannot violate SCIS by design.

---

### Strategic Role
ProgramBuilder is not a code generator.

It is a **deterministic compiler of intent**, designed so that:
- LLMs can participate safely
- Humans retain authority
- Software can be rebuilt, audited, and evolved without loss of meaning

PB turns SCIS from theory into an operational system.

9.

