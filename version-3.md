
## Qualifying R&D Projects (2025) – Version 3

Total of **2** R&D projects undertaken during this claim period (activity ran throughout 2025; reporting work was preliminary prior to May and became substantively applied thereafter).

1. **Scratchpad Workflow Platform – Data-Integrated Structured Reasoning Tooling**
2. **Scratchpad-Driven Verbal-Reasoning Reporting System (Candidate–Role–Team Fit)**

---

# PROJECT 1: Scratchpad Workflow Platform – Data-Integrated Structured Reasoning Tooling

**Engineering and technology > Information engineering / Software engineering**
**Ongoing** (R&D continued as uncertainty remained in execution semantics and regression anchoring)

## Existing technological and scientific solutions and knowledge

The Developing Leaders Partnership Limited (“DLP”, trading name: TextAlchemy) develops software that supports decision-making using structured, multi-step LLM reasoning workflows.

At the start of the 2025 claim period, the team continued development of its in-house workflow tooling known as the **Scratchpad**. The Scratchpad was intended to enable human-led design and iteration of multi-step “verbal reasoning” workflows, including operation by non-technical and semi-technical stakeholders. Conventional approaches—prompt text files combined with engineering scripts, or engineer-operated notebooks—were not effective for this purpose because they were difficult to run repeatedly against real datasets, difficult to compare outputs across changes, and not accessible to non-technical contributors.

The team considered available orchestration paradigms (including agent-oriented frameworks and visual “low-code” tools). However, these approaches did not provide, in combination, a practical method for: (i) authoring multi-step reasoning workflows; (ii) pushing qualitative data sources through the workflow with low friction; (iii) producing reviewable artefacts suitable for manual evaluation; and (iv) supporting controlled iteration with regression detection for qualitative outputs. Visual tools accessible to non-technical users also typically lacked robust support for long-form analytical writing, versioning, and practical data ingestion suitable for this use case.

## Technological and scientific objectives

### Gap statement (what necessitated commencing the project)

There was a gap in the **overall technological capability** available to competent professionals attempting to build **multi-step, data-driven, qualitative LLM reasoning workflows** that remained **manually evaluable**, **replayable**, and **iterable** by non-technical contributors. Existing practices did not provide an established, readily deducible method to integrate qualitative dataflow, workflow execution semantics, and evaluation artefacts into a single coherent system.

### Field-level advance sought (explicit)

The technological advance sought was an increase in capability in the field of **structured reasoning workflow orchestration for explainable decision support**, specifically enabling **tight integration between qualitative data sources and multi-step LLM workflow execution** with **replayability/iteration properties** and **evaluation artefacts** that support systematic improvement. This was a computer science/software engineering advance in execution modelling, dataflow semantics, and evaluation/observability of multi-step NLP pipelines, rather than an advance in the business/psychology content domain.

In practical terms, the objectives were to develop workflow tooling that could:

* support expressive chaining beyond a simple tree-like flow model (including non-tree execution graphs with merge/join semantics);
* enable qualitative data to be pushed through multi-step reasoning chains with materially less engineering overhead than prompt files and scripts;
* support workflow versioning and comparability across changes (regression anchoring) for qualitative outputs; and
* present intermediate artefacts in a form suitable for human review, enabling systematic iteration rather than ad-hoc “prompt tweaking.”

## Technological and scientific uncertainties

Technological uncertainty centred on whether it was feasible to represent, execute, and evolve complex qualitative reasoning workflows with sufficient determinism/replayability and observability to support systematic improvement.

Key uncertainties included:

1. **Execution model and representation uncertainty (non-tree workflows):** it was uncertain how to represent and execute non-tree workflows (e.g., directed acyclic graphs) with explicit join/merge semantics for intermediate artefacts, without losing comprehensibility, while also enabling replayable runs and stable artefact lineage.

2. **End-to-end dataflow semantics uncertainty:** it was uncertain how to push heterogeneous qualitative data (documents and structured inputs) through chained reasoning steps such that intermediate artefacts remained stable, referencable, and suitable for later report assembly and review, without unacceptable operational overhead.

3. **Regression anchoring uncertainty for qualitative outputs:** it was uncertain how to define regression signals and evaluation artefacts suitable for qualitative multi-step outputs—i.e., how to detect that a workflow change materially degraded behaviour when the output is not a simple numeric metric.

4. **Practical non-technical usability without losing technical guarantees:** it was uncertain whether non-technical authoring could be supported without sacrificing the execution semantics, traceability, and versioning needed for systematic engineering iteration.

### Not readily deducible (explicit)

These uncertainties were not readily deducible by a competent professional at the outset because publicly available approaches did not provide an established pattern that combined: (i) explicit execution graph semantics for multi-step LLM workflows, (ii) tight qualitative dataflow integration, and (iii) evaluation artefacts and regression anchoring suitable for human review of qualitative outputs.

## R&D activities to resolve technical and scientific challenges

The competent professionals undertook a systematic programme of design, prototyping, and testing to determine feasible execution and evaluation semantics.

### Representative experiments (hypothesis → test → outcome)

* **Experiment 1: Tree-flow vs execution-graph semantics**

  * **Hypothesis:** enabling merge/join semantics (non-tree workflows) would reduce duplication and enable consistent reuse of intermediate artefacts across downstream reasoning steps.
  * **Implementation/test:** prototype execution graph constructs supporting fan-out and re-join of artefacts; replay runs on the same qualitative inputs and compare artefact lineage and downstream stability.
  * **Outcome:** improved composability and reuse, but introduced new complexity in lineage tracking and regression anchoring, requiring additional artefact identity and versioning conventions.

* **Experiment 2: Artefact lineage and replayability**

  * **Hypothesis:** stable artefact identifiers and explicit lineage would improve replayability and support manual evaluation and debugging.
  * **Implementation/test:** introduce explicit artefact objects and lineage metadata per workflow run; rerun comparable cases to validate that artefacts could be traced and reviewed consistently.
  * **Outcome:** improved observability and comparability, but required further work to minimise overhead and to define practical regression signals for qualitative outcomes.

* **Experiment 3: Human-evaluable workflow iteration loop**

  * **Hypothesis:** presenting intermediate artefacts and deltas between versions would enable systematic improvement (as opposed to ad-hoc prompt edits).
  * **Implementation/test:** run batch comparisons on a fixed sample set, present deltas to reviewers, and record whether changes improved perceived accuracy/usefulness.
  * **Outcome:** iteration cycle became feasible at scale; remaining uncertainty persisted around robust regression signalling under ongoing feature additions.

## Rejected alternatives considered

* **Prompt files + scripts:** high friction for qualitative data ingestion and repeatable evaluation; unsuitable for non-technical contributors; weak support for systematic regression anchoring.
* **Notebooks (e.g., Jupyter):** engineer-oriented; difficult to operationalise for non-technical iteration and repeatable data-driven evaluation.
* **Agentic orchestration frameworks:** optimised for task completion/speed rather than replayable, explicative analysis; insufficient support for manual evaluation artefacts and regression anchoring for qualitative multi-step outputs.
* **Low-code visual tools:** generally weak long-form writing support, version control, and data ingestion patterns required for these workflows.

## Outcome and R&D start/stop boundary

**R&D activity in 2025:** continued throughout the period. By end of 2025 the Scratchpad supported materially more robust chaining (including non-tree workflow constructs) and improved qualitative dataflow integration and artefact traceability sufficient to support systematic iteration and downstream reporting work.

**Why R&D did not end:** uncertainty remained around regression anchoring and replayability under ongoing feature expansion; therefore, the work had not reached a point where uncertainties were fully resolved/codified across the intended capability envelope.

## Qualifying vs routine activities (boundary statement)

Qualifying activities relate to resolving uncertainties in execution modelling, dataflow semantics, artefact lineage/traceability, and regression anchoring for qualitative multi-step workflows. Routine activities excluded include general UI styling, standard product engineering, and non-novel implementation work not directly required to resolve the above uncertainties. UI work only qualified where instrumental to enabling traceability review and version-to-version comparison.

---

# PROJECT 2: Scratchpad-Driven Verbal-Reasoning Reporting System (Candidate–Role–Team Fit)

**Engineering and technology > Information engineering / Software engineering**
**Partially resolved in-period; ongoing** (prototype with functional characteristics achieved around October; new/continuing uncertainties remained in replayability under feature extension)

## Existing technological and scientific solutions and knowledge

The team sought to build a reporting system based on **multi-step LLM verbal reasoning over qualitative inputs**. Conventional automated reporting systems and NLG platforms typically focus on transforming structured or numerical datasets into narrative text (data-to-text). The team’s objective differed: to perform complex reasoning over qualitative evidence (CVs, psychological measures, role and team context) and produce decision-support reporting that was coherent, explainable, and sufficiently stable for client-facing use.

Existing agent frameworks prioritised speed and task completion rather than conservative, explicative analysis and did not directly address the technical challenge of generating grounded, consistent, replayable analytical reports from qualitative multi-source inputs with end-to-end traceability.

## Technological and scientific objectives

### Field-level advance sought (explicit)

The advance in the field for Project 2 was enabling decision-support reporting driven by multi-step AI verbal reasoning over qualitative inputs (e.g., CVs, psychological measures, and role/team context), producing prioritised, explainable analytical issues beyond conventional automated reporting systems that primarily convert structured or numerical data into narrative text.

**Explicit technology anchoring (avoid “content” framing):**
The technological advance was in the **methods and pipeline controls** used to generate, structure, trace, and replay grounded NLP outputs from qualitative inputs under multi-step workflows (computer science/software engineering), not in the underlying interpretation of psychology as a scientific field.

In practical terms, the system sought to:

* map role requirements and infer relevant team values from available data;
* cross-correlate candidate strengths/gaps against team and role context;
* produce a prioritised issue set; and
* assemble client-facing report prose with trace links to intermediate artefacts.

## Technological and scientific uncertainties

Uncertainty centred on whether it was feasible to engineer a reporting pipeline that remained consistent, grounded, traceable, and replayable given multi-step transformations and qualitative inputs.

1. **Cross-section consistency (system uncertainty):** it was uncertain how to prevent contradictions across sections when different reasoning stages produced locally plausible but globally inconsistent outputs.

2. **Grounding/substantiation (system uncertainty):** it was uncertain how to avoid persuasive narrative unsupported by inputs and intermediate reasoning artefacts, and whether substantiation could be enforced without unacceptable loss of analytical richness.

3. **Replayability and stability under evolution:** it was uncertain how to create a replayable generation pipeline whose behaviour remained materially consistent across re-runs and across versions, particularly when introducing new features while maintaining existing behaviours.

4. **End-to-end traceability under multi-step transformations:** it was uncertain whether trace links could be preserved from final conclusions back to source inputs through multiple intermediate transformations without unacceptable overhead or brittle coupling.

### Not readily deducible (explicit)

These uncertainties were not readily deducible by a competent professional because there was no established, publicly available approach that reliably converted multi-step LLM verbal reasoning over qualitative data into grounded, consistent, replayable client-facing reports with end-to-end traceability suitable for human review and regression control.

## R&D activities to resolve technical and scientific challenges

The team undertook systematic experimentation and prototyping, using Scratchpad as enabling tooling.

### Concrete mechanisms implemented (examples)

* **Intermediate representation (“Issue Register”):** generate a structured issue list including priority scores and references to the specific inputs/artefacts that support each issue, prior to prose generation. This was designed to reduce unsupported claims and to provide a stable assembly target.
* **Critic pass placement:** apply critique/review stages after issue generation and prior to prose assembly to identify contradictions and weakly supported issues before they become embedded in narrative text.
* **Versioned chains and batch evaluation:** pin chain/prompt versions per build and rerun fixed samples to compare outputs and detect regressions, supporting replayability and controlled iteration.

### Representative experiments (hypothesis → test → outcome)

* **Experiment 1: Single-pass narrative vs intermediate representation**

  * **Hypothesis:** separating issue generation (structured) from prose generation would reduce unsupported narrative and improve traceability.
  * **Test:** compare single-pass narrative reports to two-stage reports using an Issue Register; perform batch reruns on a small fixed sample set and review differences.
  * **Outcome:** structured intermediate artefacts improved reviewers’ ability to detect unsupported claims and reduced narrative drift; residual contradictions still occurred across sections and required additional controls.

* **Experiment 2: Critic pass location**

  * **Hypothesis:** inserting critique prior to prose assembly would reduce cross-section contradictions and prevent weak issues being amplified in prose.
  * **Test:** vary critic placement across runs (e.g., after issue generation vs after prose) and compare contradiction frequency and perceived grounding using comparative human review.
  * **Outcome:** earlier critique reduced some contradiction/grounding failures; however, feature additions continued to create regressions requiring disciplined versioning and review.

* **Experiment 3: Stability under feature extension**

  * **Hypothesis:** pinned versions and regression samples would maintain acceptable stability while new features were added.
  * **Test:** introduce new capabilities incrementally while rerunning baseline samples; compare outputs for stability and identify where behaviour shifted unexpectedly.
  * **Outcome:** reproducibility was generally good; the principal breakdown occurred when introducing new features while preserving old behaviours—indicating ongoing system uncertainty in stability under evolution.

### Human-judged evaluation

The system was intentionally designed to elicit human tacit judgement rather than relying on an automated “judge model.” Outputs and intermediate artefacts were presented efficiently to reviewers to assess accuracy and usefulness in real-world context, and batch reruns on samples were used to track progress and guide iterations.

## Rejected alternatives considered

* **Single-pass narrative generation with templated sections:** did not reliably prevent contradictions and often produced plausible narrative without sufficient grounding.
* **Conventional data-to-text reporting platforms:** suited to narrating structured/numeric data but not multi-step qualitative verbal reasoning with traceability and replayability controls.
* **Agent frameworks:** prioritised action/speed over conservative, traceable analysis; did not provide an obvious route to replayable, grounded reporting with regression anchoring.
* **Automated “judge model” as primary evaluator:** not adopted as the primary method due to uncertainty around bias/reliability; the approach instead centred on human review supported by traceable intermediate artefacts.

## Outcome and R&D start/stop boundary

**R&D activity in 2025:** preliminary investigation and architecture prior to May; substantive experimental work May onward. A prototype with functional characteristics suitable for client usage was achieved around **October 2025** (transition from PoC analysis flow to client-usable reporting workflow).

**Why R&D continued beyond that point:** while a client-usable workflow existed, uncertainties persisted around replayability/stability when adding new features while preserving prior behaviour. Accordingly, work to resolve those uncertainties remained qualifying where it directly addressed those unresolved technological uncertainties.

## Qualifying vs routine activities (boundary statement)

Qualifying activities relate to resolving uncertainties around consistency, substantiation/grounding, traceability, replayability, and regression anchoring in a multi-step qualitative NLP pipeline. Routine activities excluded include general UI/UX styling and layout, client-specific content work, and standard product engineering. UI/visual work is only qualifying where it was instrumental to enabling traceability review (e.g., presenting trace links and version comparisons) or to validating the underlying technological mechanisms.

---

## Competent professionals and evidence (applies to both projects)

The R&D programme was led by **Daniel Huggins**, who provided competent professional judgement on the technological uncertainties and feasibility in software engineering/NLP pipeline design, execution modelling, and evaluation mechanisms.

**Mark Loftus** contributed as a **domain specialist** supporting evaluation of usefulness/accuracy in context; his role informed human review of outputs but the technological uncertainty resolution and engineering judgement remained anchored in software/AI engineering disciplines.

Evidence supporting the systematic experimental programme includes:

* source control history (including prompt/workflow versioning),
* artefact structures used in intermediate representations and traceability,
* sample anonymised outputs demonstrating prior failure modes and post-change behaviour, and
* batch rerun comparisons showing stability/regression under workflow changes.

