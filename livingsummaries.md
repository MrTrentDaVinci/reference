
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


3.
## Tag — “Your it!”

### Executive Summary
**Tag — Your it!** is a dual-version, user- and AI-centric discovery and planning platform that combines icon-based workflows, RGB-coded tags, knowledge graphs, AI agents, and multi-medium accessibility. It empowers users, creators, and power players to discover, organize, and act on structured and semi-structured information with full control, privacy, and clarity.

### Core Problem
Modern information systems suffer from:
- Fragmented discovery across apps, platforms, and devices  
- Overwhelming notifications with little user control  
- Poor mapping between ideas, content, people, places, and time  
- AI systems that push suggestions instead of supporting intent  
- Limited support for both casual use and advanced workflows  

### Proposed Solution
A **privacy-first, icon-driven tagging and planning platform** with:
- Personal, evolving tag databases controlled by users  
- A thin external interface to global knowledge graphs  
- Explicit icon workflows for discovery, planning, and reasoning  
- AI assistance that is reactive, explainable, and user-initiated  
- Seamless operation across smartphones, desktops, and enterprise environments  

### Dual-Version Model
**User Tag**
- Visual icon workspaces with a typing bar for uniconed instructions  
- Preset workflows (Search, Plan, Generate, Validate, Temporal, Geo)  
- Personal tag DB with favorites, bundles, and maps  
- Batch-based, user-requested notifications  

**Creator Tag**
- Rapid tagging anywhere  
- Concept clustering and synonym suggestions  
- Analytics dashboards (usage, popularity, evolution history)  
- Local DB sync with optional external publishing  

### Core Architecture
- **Personal Tag Database:** Private, local, append-only evolution history  
- **External Tag Interface:** Fetch-on-demand access to global knowledge graphs  
- **Knowledge Graph Layer:**  
  - Nodes: Tags (primary/secondary/tertiary), Creators, Content, Entities, Events  
  - Edges: IS_A, RELATED_TO, SYNONYM_OF, CREATED_BY, HOSTED_ON, USED_WITH, VERSION_OF, TEMPORAL  
- **Vector Search & AI Layer:** Semantic search, embeddings, NLP auto-tagging, agent support  

### Icon & Workflow System
- Icons represent explicit operations (Search, Expand, Cluster, Temporal Slice, Geo, Plan)  
- Sequential workflows with structured inputs/outputs  
- Combinable macros for common or advanced operations  
- Customizable semantics with AI dialog resolving ambiguity  
- Icons integrate directly with maps, databases, and notifications  

### Notification Philosophy
- **Batch-based and user-controlled** (no unsolicited pushes)  
- Medium-aware delivery:
  - Smartphones: push digests, geo-aware alerts  
  - Desktops: dashboards and batch exploration  
- Privacy-centric learning: only user-initiated interactions inform AI adaptation  

### Tag & Map Management
- Deletion, merging, renaming with seamless map/workflow updates  
- Notification muting and batch clearing  
- AI suggestions dynamically respect removed or muted tags  

### Multi-Medium & Context Awareness
- Smartphone: quick capture, geo-aware discovery  
- Desktop/Laptop: deep exploration, analytics, map editing  
- Enterprise: shared maps, role-based access, team notifications  
- Optional geo-temporal tagging for real-world planning and trend analysis  

### Power Player Mode (Advanced)
- Complex icon macros and multi-map workflows  
- AI-assisted research, planning, and reasoning over graphs  
- Rule-based agents for batch operations and expansions  
- Temporal and geospatial reasoning across linked maps  

### Key Principles
- **User empowerment over automation**  
- **Privacy first, local by default**  
- **Explicit structure beats opaque intelligence**  
- **AI assists, never overwhelms**  

### Current Status
Concept & architecture definition complete.  
Positioned for phased implementation beginning with personal DB, icon workflows, and knowledge graph foundations.

### Strategic Value
- A unifying interface for discovery, planning, and action  
- Bridges casual use and advanced workflows without fragmentation

4.
## System Design Decision Framework (SDDF)

### Executive Summary
The **System Design Decision Framework (SDDF)** is a structured, change-aware methodology for designing, validating, and evolving software system architectures.  
Version 2.0 transforms the original v1.0 framework from large, monolithic documents into a **modular, JSON-driven, dependency-aware system** optimized for LLM interaction, team collaboration, and automated validation.  
SDDF provides explicit decision capture, automated cohesion checking, and impact analysis when architectural choices change.

### Core Problem
System design documentation commonly fails because it is:
- Large, monolithic, and difficult to reason about holistically  
- Linear and static, despite systems evolving non-linearly  
- Hard to validate for internal consistency  
- Extremely costly to update when a single decision changes  
- Poorly suited for LLMs, automation, or collaboration  

### Evolution from v1.0 → v2.0
**v1.0**
- 11 large documents (up to 45 pages each)  
- 300+ pages total  
- Manual cohesion checks  
- No automated change tracking  

**v2.0**
- 40+ focused modules (5–10 pages each)  
- JSON-standardized inputs and outputs  
- Automated dependency graphs  
- Built-in change impact analysis  
- Designed for structured LLM workflows  

### Architectural Philosophy
- **Decisions are first-class artifacts**  
- **Structure beats prose** for validation and automation  
- **Change is inevitable** and must be explicitly managed  
- **LLMs are collaborators**, not black boxes  
- **Modularity enables parallelism and scale**

### Core Architecture (v2.0)
SDDF v2.0 operates as a **five-phase workflow**:

1. **User Prep**  
   Minimal JSON input describing goals, constraints, scale, and context.

2. **Section Processing**  
   - Each design area is driven by a Section Script (JSON).  
   - LLM asks clarifying questions.  
   - All viable options are presented.  
   - User selects and confirms decisions.  
   - Output is a standardized Section Summary (JSON).

3. **Summary Collection**  
   All section summaries are stored as versioned decision records.

4. **Cohesion Validation**  
   - Dependency graph generation  
   - Conflict and gap detection  
   - Cost, scaling, and security consistency checks  
   - Structured Cohesion Report output

5. **Change Management (NEW in v2.0)**  
   - Change Impact Engine analyzes decision updates  
   - Affected sections identified with confidence scores  
   - Re-evaluation order recommended  
   - Cyclical dependencies flagged

### Modular Structure
- **Tier 0:** Initialization & LLM protocols  
- **Tier 1:** Project context and constraints  
- **Tier 2:** Design domains (Architecture, Scaling, API, Database, Caching, Security, Monitoring, Deployment)  
- **Tier 3:** Validation, dependency mapping, and change impact analysis  
- **Tier 4:** Governance, versioning, and review cycles  
- **Tier 5:** Reference schemas, examples, and templates  

### JSON-Driven Design
SDDF v2.0 standardizes:
- User input context  
- Section instructions  
- Decision summaries  
- Dependency graphs  
- Cohesion validation output  
- Change impact analysis  

This enables:
- Git-friendly version control  
- Automated validation  
- Tooling and visualization  
- Reduced hallucination in LLM outputs  

### Key Innovation: Change Impact Engine
When a decision changes:
- Old vs new summaries are compared  
- Dependency graph determines affected sections  
- Impact levels (High/Medium/Low) are assigned  
- Confidence scores are calculated  
- Re-evaluation order is generated  

This replaces manual document audits with **explicit, explainable system intelligence**.

### Benefits
**For Users**
- Faster completion (1–2 weeks vs 2–4)  
- Clearer decision records  
- Safer iteration when requirements change  

**For Teams**
- Parallel work across modules  
- Explicit handoffs and dependencies  
- Easier onboarding and review  

**For LLMs & Tooling**
- Smaller, well-scoped contexts  
- Schema validation reduces ambiguity  
- Automation-ready decision artifacts  

### Current Status
- **v1.0:** Complete, stable, in active use  
- **v2.0:** Design complete, implementation planned  
- **Target Release:** Q1–Q2 2026  

### Roadmap
- **Phase 1:** JSON schemas, section scripts, dependency model  
- **Phase 2:** Content migration from v1.0  
- **Phase 3:** Change Impact Engine implementation  
- **Phase 4:** Tooling, validation, visualization  
- **Phase 5:** Documentation and examples  
- **Phase 6:** Community iteration and extensions  

### Forward Path (v3.0 Direction)
SDDF v3.0 will evolve from a framework into an **interactive worksheet / application / decision database**, featuring:
- Visual system design editors  
- Real-time collaboration  
- AI-assisted recommendations  
- Cost and compliance automation  
- Infrastructure-as-Code generation  
- CI/CD and monitoring integration  

### Strategic Value
SDDF provides a **foundational control plane for system design decisions**, enabling:
- Safer architectural evolution  
- Explainable tradeoffs  
- Scalable collaboration  
- A bridge from documentation → tooling → intelligent systems
- Provides a stable substrate for AI agents grounded in user intent  
- Future-proof platform for geo-temporal reasoning, collaboration, and AI integration

5.
## Automated Policy-Adherent Email Routing System

### Executive Summary
The **Automated Policy-Adherent Email Routing System** is a systematic, enterprise-grade approach to processing incoming emails according to complex regulatory, confidentiality, escalation, and time-sensitive policies.  
Unlike generic LLM-based email tools or brittle rule engines, this system decomposes email routing into **explicit, auditable, multi-phase decision processes** that preserve context, prevent assumptions, and provide verifiable compliance trails.

The system is designed for **high-risk enterprise environments** where incorrect routing creates regulatory violations, legal exposure, or operational failures.

---

### Core Business Problem
Enterprises receive thousands of emails daily that must be routed according to overlapping and evolving policies involving:
- Regulatory compliance (GDPR, HIPAA, SOX, FINRA, AML)
- Escalation hierarchies (legal threats, executive issues, crisis communications)
- Confidentiality levels (personnel, proprietary, client-sensitive data)
- Time-sensitive obligations (contracts, audits, regulatory deadlines)

Current solutions fail to reliably interpret **policy combinations**, **context ambiguity**, and **edge cases**, forcing costly manual intervention.

---

### Why Existing Solutions Fail

#### Generic LLM-Based Tools
- Treat emails as single-step classification problems
- Cannot preserve decision context across multi-step evaluations
- Lack embedded knowledge of enterprise policies
- Produce un-auditable, black-box decisions
- Collapse under ambiguous or incomplete inputs

#### Traditional Rule-Based Systems
- Extremely brittle when policies change
- Require heavy manual maintenance
- Cannot interpret nuanced language
- Generate excessive false positives
- Fail silently in edge cases

---

### Real-World Impact
- **Compliance fines:** $50K–$5M per incident
- **Missed escalations:** Legal exposure, customer churn, reputational damage
- **Operational cost:** 2–4 FTEs managing routing exceptions
- **Audit failures:** No demonstrable systematic controls

---

### Design Philosophy
- **Routing decisions must be explainable**
- **Assumptions must be explicitly prevented**
- **Policies must be decomposed, not embedded**
- **Accuracy is prioritized over speed**
- **Every decision must be auditable**

---

### Core Architectural Concept

#### Incoming-Only Processing Model
Each email is evaluated independently (no reply-chain context), enabling:
- Cleaner decision boundaries
- Simplified audit trails
- Deterministic processing
- Safer failure handling

---

### Multi-Phase Decision Architecture

#### Phase 1: Sender Identification (“Who”)
Horizontal binary agents applied to every email:
- Is internal sender
- Is known customer
- Is approved vendor
- Is regulatory authority
- Is media/press
- Is unknown external

Outputs are **explicit True/False decisions** with stored reasoning.

#### Phase 2: Content & Intent Analysis (“What”)
Triggered conditionally based on Phase 1 results:
- Legal indicators
- Regulatory request language
- Personnel or HR signals
- Financial or contractual language
- Risk and urgency markers

#### Phase 3: Policy Evaluation (“Which Rules Apply”)
- Jurisdiction-specific compliance logic (GDPR vs CCPA vs internal)
- Confidentiality handling requirements
- Escalation thresholds
- Deadline and SLA activation

#### Phase 4: Risk & Routing Decision
- Routing destination(s)
- Required notifications
- Deadline tracking
- Manual review triggers (when ambiguity remains)

---

### Key Innovation: Binary, Sequential Agents
Each decision point:
- Produces a constrained True/False output
- Stores reasoning and metadata
- Writes to a persistent decision record
- Enables replay and audit reconstruction

This replaces probabilistic classification with **explicit decision trees**.

---

### Context Preservation Infrastructure
- Database-backed storage of every agent decision
- JSON-defined agent prompts and outputs
- Versioned policy logic
- Full audit trail for compliance and review

---

### Handling Ambiguity & Failure
- Explicit manual-review triggers
- Safe defaults for high-risk uncertainty
- Multi-LLM validation for critical decisions
- Disagreement detection between agents
- Clear error and retry paths

---

### Integration Scope
Designed to integrate with:
- Enterprise email systems
- CRM and customer databases
- Legal and compliance platforms
- Incident management and escalation tools
- Audit and reporting systems

---

### Industry Applicability
- **Financial Services:** FINRA, AML, complaint escalation
- **Healthcare:** HIPAA, medical urgency routing
- **Legal & Consulting:** Conflict checks, confidentiality enforcement
- **Large Enterprises:** Executive, HR, and risk communications

---

### Strategic Value
This system demonstrates how **systematic methodology outperforms ad hoc AI automation** by:
- Making policy logic explicit
- Preserving reasoning context
- Enabling compliance-grade auditability
- Scaling complexity without chaos

---

### Current Status
- Conceptual architecture defined
- Methodology validated against real enterprise failures
- Suitable for phased prototyping and controlled rollout

---

### Forward Path
Future evolution may include:
- Visual policy editors
- Agent orchestration tooling
- Compliance dashboards
- Real-time SLA monitoring
- Integration with decision frameworks (ASD / SDDF)
- Transition from framework → worksheet → application

6.
## Enterprise Large Document Processing System

### Executive Summary
The **Enterprise Large Document Processing System** is a systematic architecture for processing, querying, and validating large digital documents (50–500+ pages) while preserving full structural integrity, cross-references, and precise page citations.  
It addresses a core enterprise failure of current LLM solutions: **context window limits force arbitrary chunking that destroys document structure, traceability, and compliance reliability**.

The system transforms large documents into **structured, auditable, queryable organizational assets** using multi-database architecture, multi-system validation, and context-aware retrieval.

---

### Core Business Problem
Enterprises rely on large documents for compliance, legal, academic, and operational purposes, but current AI systems fail because they:
- Cannot process entire documents holistically
- Destroy navigation elements (TOC, index, glossary)
- Lose cross-references and citations
- Fail to maintain precise page references
- Break existing analysis when documents are updated
- Lack systematic multi-document relationship handling

These failures create **regulatory risk, audit exposure, and operational inefficiency**.

---

### Design Philosophy
- **Structure must be preserved, not inferred**
- **Validation must be redundant and explicit**
- **Assumptions must be prevented, not averaged**
- **Accuracy is prioritized over speed**
- **Every decision must be traceable and auditable**

---

### System Evolution Overview

#### Phase 1: Structural Foundation
Key insight:  
Instead of arbitrary chunking, use **native document structure** (TOC, hierarchy, pagination, indices) as the navigation framework.

Decision:
- Separate document structure, content, and navigation into specialized databases
- Preserve verbatim content alongside structural metadata

---

#### Phase 2: Multi-System Validation
Single analysis methods proved unreliable across document formats.

Solution:
Four independent structural validation systems:
- Table of Contents analysis
- Typography hierarchy detection
- Whitespace and layout pattern analysis
- Document bookend analysis (front/back scope validation)

Innovation:
- **Consensus-based confidence scoring**
- No single system can determine structure alone
- Explicit reliability metrics for every structural decision

---

#### Phase 3: Document Type Classification
Recognition that different domains follow different structural conventions.

Document Type Classification Agent:
- **Legal:** Bluebook citations, case numbers, certificates of service
- **Business:** Executive summaries, financial tables, corporate formatting
- **Academic:** Abstracts, bibliographies, institutional affiliations

Value:
- Domain-specific expectations improve accuracy
- Avoids one-size-fits-all structural assumptions

---

#### Phase 4: RAG & Context-Aware Querying
Transition from static processing to dynamic information retrieval.

Capabilities:
- Query-driven context assembly
- Temporary, traceable context documents
- Multi-document batching (controlled scope)
- Dynamic knowledge graph generation per query

---

### Core Architecture

#### Two-Phase Processing Model
**Phase 1: Document Digestion (One-Time)**
- Structural extraction and validation
- Database population
- Relationship and reference mapping

**Phase 2: Document Utilization (Ongoing)**
- Context-aware querying
- Dynamic retrieval and synthesis
- Confidence-filtered results

---

### Multi-Database Architecture
- **Structure Database:** Hierarchy, sections, page ranges (relational)
- **Content Database:** Verbatim page content (document/vector)
- **Navigation Database:** Terms, definitions, cross-references (search-optimized)
- **Master Database:** Document registry, lifecycle tracking, cross-document relationships

---

### Agent-Based Processing Framework
- Document Type Classification Agent
- Structure Analysis Agent (TOC)
- Typography Analysis Agent
- Layout / Whitespace Analysis Agent
- Validation Orchestrator Agent (consensus + confidence)
- Relationship Analysis Agent
- Dynamic Context Mapping Agent

---

### Context Preservation & Auditability
- Original document content preserved verbatim
- Structural metadata maintained separately
- Cross-references validated and tracked
- Confidence scores attached to all determinations
- Full processing and update audit trails

---

### Business Value

#### Enterprise Compliance
- Precise page and section references
- Audit-ready decision trails
- Cross-document citation validation
- Version-aware update handling

#### Operational Efficiency
- Reliable navigation of large documents
- Multi-document relationship analysis
- Domain-optimized processing
- Reduced manual research and verification effort

---

### Strategic Applicability
Applicable to:
- Regulatory compliance documentation
- Legal research and case analysis
- Academic literature review
- Corporate policy and procedure systems
- Technical documentation and manuals

Each processed document becomes a **reusable organizational asset**.

---

### Current Status
- Architecture validated
- Multi-system validation framework proven
- Domain-specific processing implemented
- RAG-based query model established

---

### Forward Path
Potential future enhancements:
- Performance optimization at scale
- Advanced relationship visualization
- Enterprise DMS integration
- Automated quality monitoring
- Optional ML augmentation for classification and confidence scoring

---

### Strategic Significance
This project demonstrates how **systematic methodology outperforms brute-force AI approaches** by:
- Preserving structure instead of discarding it
- Replacing single-point inference with validation consensus
- Maintaining compliance-grade traceability
- Scaling complexity without losing reliability

7.
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

