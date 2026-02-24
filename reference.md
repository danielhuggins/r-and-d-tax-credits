
ADVANCE

[11:55 AM]
(1.1) At the start of the claim period (1 January 2025), the technological objective was to make it possible to develop analytically complex verbal-reasoning prompt chains (which as we define as 10 or more dependent steps), and to be able to iterate and incrementally improve those chains with manageable levels of regression.

(1.2) A "prompt" is a structured question or instruction to an LLM (an Artificial Intelligence), such as "Analyze this data in this way". A "prompt chain" is a sequence or network of such questions or instructions. By walking the AI through an analysis process, or through the steps needed to perform a task, you can making it possible to for the AI to answer questions and perform tasks that are much too complex for the AI to handle normally.

(1.3) Unfortunately, LLM outputs are non-deterministic (random) and the models operate as black-box systems (it's impossible to tell why they behave a certain way). That results in seemingly minor edits to their "prompts" can produce unexpected degradations in output quality that cannot be anticipated in advance. The model’s performance is sensitive to instruction load: adding constraints or additional instructions can degrade performance across multiple dimensions, rather than improving it as you might expect. In long prompt chains, these effects compound: a small upstream change subtly alters an intermediate artefact, which alters the input distribution for downstream steps, and this can cascade into materially different outcomes at later stages. As chain depth increases, the number of ways the chain can fail grows and regressions become harder to detect, attribute, and prevent.

(1.4) To deal with these issues, the following specific sub‑objectives were set at the start of the claim period (1 January 2025) for deep, multi-step LLM prompt chains:

- To make it possible to reliably and repeatedly create long (10+ steps) verbal-reasoning prompt chains with failure rates less than 5% or better.

- To be able to iterate - to make a small modification to a single step in a prompt chain - without a regression in the rest of the chain, in at most 200% of the time it takes to iterate a prompt of equivalent complexity in isolation.

- To be able to detect essentially all (~99.9%) “major regressions” while testing a new iteration, where a major regression means a change that would be expected to reduce end‑to‑end success below the 95% requirement.

- To be able to detect ~95% of “minor regressions”, where a minor regression meant a measurable reduction in one or more agreed quality dimensions that did not reach the threshold of an end‑to‑end failure.

- To be able use LLMs to speed up iteration of our individual prompts or on the chains as a whole; either to improve prompts or to identify and diagnose failures or quality regressions.

- To be able to observe & measure progress towards our domain-specific optimisation targets.

(1.5) This R&D aimed to make deep LLM prompt chains a dependable engineering technique for long-chain analytical reporting—i.e., turning source artefacts into structured, usable written analyses through multiple interdependent reasoning and transformation steps. If successful, the practical technological impact would be that such analytical-reporting prompt chains could be created, extended, and updated within predictable validation effort, while keeping end‑to‑end success rates, output stability/consistency, and other quality dimensions within predefined tolerances, rather than requiring extensive ad‑hoc trial‑and‑error and near full retesting after each prompt change. No publications or patents were produced during the 2025 claim period; knowledge capture was intended to be codified for potential wider release (including a supporting software toolkit) in a subsequent period

[11:55 AM]
Daniel Huggins - 11:36 PM 22nd Feb 2026

[11:55 AM]
BASELINE

[11:55 AM]
(2.1) By 1 January 2025 it was well understood that LLMs behave as stochastic, non-deterministic black-box systems. The same input could produce meaningfully different outputs across runs, and small prompt changes could produce large, hard-to-predict changes in quality. As a result, the baseline approach to improving reliability in the field relied heavily on empirical evaluation rather than predictable, fully deterministic engineering behaviour.

(2.2) The most developed and widely used practice was still single-prompt iteration. Teams increasingly used representative test sets, batch runs, and version-to-version comparisons to detect regressions, supported by early evaluation and prompt-testing tools such as OpenAI Evals and promptfoo, and by prompt management and evaluation platforms. “LLM-as-judge” methods and rubric-style grading were emerging to evaluate qualities that could not be checked with simple rules, but these approaches were most straightforward where success criteria were relatively explicit and low-dimensional.

(2.3) There were also early research and prototype techniques aimed at automatic prompt improvement, such as APE and OPRO, which treated prompt optimisation as a search or optimisation problem. These approaches provided useful inspiration, but they generally assumed clearer objective functions than are typical in deep analytical prompt-chain settings, and there was no widely accepted standard way to apply them to multi-dimensional quality targets with partly tacit criteria.

(2.4) For prompt chains, the field had some pieces of the puzzle, including chain construction frameworks, and early tracing/observability and chain-focused testing tools such as LangSmith. Related evaluation ideas also existed in adjacent areas such as retrieval-augmented generation pipelines, but these were not, by themselves, a solution to dependable deep-chain development and iteration.

(2.5) Tools and papers such as OpenAI Evals, APE and OPRO were therefore treated primarily as reference approaches for specific techniques—dataset-based evaluation, rubric or model-graded scoring, and prompt optimisation—rather than as end-to-end targets to recreate. At the start of 2025 these capabilities did not amount to a dependable, generally repeatable way to create and iterate deep, highly interdependent prompt chains. In practice, development of long chains with many interacting quality requirements still tended to be regression-prone and labour-intensive, with substantial re-testing after changes and limited ability to control non-local regressions across the chain

[11:55 AM]
Daniel Huggins - 8:29 PM 22nd Feb 2026

[11:56 AM]
Uncertainty

[11:56 AM]
(3.1) At the start of the claim period (1 January 2025), it was uncertain whether deep analytical prompt chains could ever be dependable in real use—i.e., achieve <5% end‑to‑end failures on representative tasks. Reliability was expected to compound with depth (even 99% per‑step gives ~90% over 10 steps), and stochastic black‑box behaviour meant small upstream variations could cascade into downstream failures, so established single‑prompt/shallow‑chain practices did not demonstrate that a stable, sufficiently accurate operating point even exists; a competent practitioner would recognise this as a genuine technological uncertainty because accepted practice and published demonstrations at that time largely covered individual prompts or short chains rather than repeatable 10+ step analytical chains.

(3.2) At the start of the claim period, it was uncertain whether deep analytical prompt chains (typically 10+ interdependent steps) could be iterated while optimising multiple interacting quality dimensions, without introducing non‑local downstream regressions that were difficult to detect and attribute. This was difficult because stochastic model variation and chain interaction effects can mask or mimic genuine change, and many relevant quality shifts are spectrum‑based rather than clean pass/fail. A competent practitioner would also view this as a genuine technological hurdle because, as of 1 January 2025, there was no generally accepted, repeatable approach for specifying and validating sufficiently reliable LLM‑as‑judge criteria and regression detection for multi‑dimensional evaluation of deep prompt chains.

(3.3) At the start of the claim period, it was uncertain whether LLMs could be used as dependable meta-tools to speed up improvement of complex prompt chains beyond executing explicitly specified edits—i.e., to act as an LLM‑as‑judge, to analyse outputs for recurring failure patterns and likely causes, and to propose coherent chain‑wide revisions that combined multiple tweak ideas consistently. This was difficult because published and widely used LLM‑as‑judge and automated prompt‑optimisation approaches were mainly evidenced on problems with clear, low‑dimensional metrics, whereas this context required guidance across multi‑dimensional, qualitative quality constraints, increasing the risk of plausible but incorrect judgments or revisions. A competent practitioner would recognise this as a genuine technological uncertainty because, as of 1 January 2025, there was no generally accepted, repeatable method showing that LLM‑based judging, diagnosis, and revision could be relied on to guide prompt‑chain iteration in this difficulty class

[11:56 AM]
Daniel Huggins - 11:41 PM 22nd Feb 2026

[11:56 AM]
OVERCOME

[11:57 AM]
(4.1) Feasibility of dependable deep analytical prompt chains
To test feasibility at the required depth, we built a pilot prompt chain on OpenAI-family models (data interpretation → analysis → prose rendering) and assessed outputs against prior human-written reports. We began from an end-to-end success rate of ~2% and iterated, making small changes at each step and expanding the chain, toward ~95% using batched human evaluation. We tested prompt-step variations, compared output batches, and analysed recurring failures; we also maintained a Google Sheets database prompt changes, observed effects, and progress across quality dimensions to guide iteration, including experiments to keep instruction-load manageable by redistributing requirements across steps.

(4.2) Safe iteration and managing non-local regressions
During the process described 4.1, we found that downstream effects began to become prevalent as we approached our 95% threshold. We tried adjusting our prompt-step edits to avoid non-local downstream regressions (e.g., preserving the “shape” of intermediate artefacts and using minimal, constraint-preserving edits). We found this was impractical for deep chains. Only very small changes reliably avoided downstream effects—so we shifted to a “power-through” approach: treat downstream regressions as expected, and use Gemini’s separate analysis to quickly attribute breakage to step-to-step interface changes, and then rapidly draft and re-test compensating downstream prompt edits.

(4.3) LLMs could as dependable meta-tools
During 2025 we carried out R&D to test whether LLMs could act as dependable meta-tools (uncertainty 3.3) for deep analytical prompt chains—covering automated evaluation (LLM‑as‑judge), failure diagnosis, and suggestion of prompt-step edits. We first trialled rubric-style LLM‑as‑judge prompts in a batch evaluation harness to compare chain versions, with spot-checking of LLM judgments against human preference; however single-pass judging was difficult to align with our multi-dimensional, partly tacit criteria (e.g., correctness, analysis quality, structure, writing quality) and, because outputs and judgments were non-deterministic, reducing variance required repeated runs that became impractical at the repeat counts required (computationally and in reviewer time). We then iterated an interactive, human-in-the-loop conversational meta prompt workflow (i.e., interactive rather than fire-and-forget) using Gemini (and later o3): since one-shot “improve the prompt” requests were rarely useful, we supplied concrete failure examples and constraints that must not change, generated multiple small targeted variants, used the LLM to analyse step outputs and step-to-step interface mismatches (including pattern-finding across output batches and our Google Drive database), and screened candidate edits via small batch runs and output comparisons with human preference checks for ambiguous cases.

(4.4) Ongoing R&D beyond 31 December 2025
R&D continued beyond 31 December 2025 to further develop the interactive meta prompt chain into a tool-assisted, human-in-the-loop system in which a meta‑LLM can directly propose and apply prompt-step changes, run controlled batch evaluations, and capture/compare outputs across versions. Ongoing technological challenges include maintaining auditability and constraint adherence while allowing model-driven edits and execution, and achieving dependable multi-dimensional regression detection and iteration at deep-chain depth under stochastic model behaviour; we also intend to package these methods into a reusable software toolkit and release the technique & tooling for wider technical use
[11:57 AM]
Daniel Huggins - 12:34 AM 23rd Feb 2026
