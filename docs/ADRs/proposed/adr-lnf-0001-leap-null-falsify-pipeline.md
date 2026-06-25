# ADR-LNF-0001: Leap–Null–Falsify — A Portable Pipeline for Candidate-Insight Generation and Falsification

**Status:** proposed
**Date:** 2026-06-24 (US/Mountain)
**Author:** shanevcantwell, with Claude (orchestrator) as drafting collaborator
**Related:** ADR-LNF-0002 (refines Null-former node role, Falsifier return shape, and Appendix-A Falsifier instantiation); ADR-LNF-0003 (scored-atom interaction medium built on this pipeline's gate discipline)
**Supersedes:** —
**Superseded by:** —

> **Promotion note (2026-06-24):** Promoted from design-docs/incoming-ideas/ into leap-null-falsify, the canon home for the LNF discipline. ADR-LNF-0003 was re-coded from ADR-AOT-0001.

---

## Context

A system that generates compelling non-dominant material and then validates it against a verifier that is motivated toward acceptance cannot distinguish discovery from confabulation. The failure is not bad output; it is *frictionless* output — when the leap-to-confirmation loop runs without resistance, fluency rises while discriminability falls, and the more persuasive the artifact the less its persuasiveness means. Any pipeline that produces candidate insights needs a brake that does not weaken as the candidate gets more convincing. This spec records the shape of that brake as a composed structure rather than as operator discipline, because a brake that lives in an operator's vigilance goes slack invisibly.

The pipeline composes from a node substrate it does not redefine here but restates so the document is self-contained. The substrate is a **uniform recursive node**: there is no distinct "leaf" or "worker" type. A node orchestrates a set of primitives that resolve to either other nodes or tool calls; it reaches for a node-primitive before a tool-primitive and executes only when no further decomposition is warranted (*orchestrate first, execute at the threshold*). Leaf-ness is a property of a node's contract — a job with no interior to decompose holds tool-primitives only and can return nothing but compressed pointers — not a depth rule imposed from outside. Because nodes are separated by real dispatch boundaries, a node that hits ambiguity or an uncertain destructive operation returns a **framed sub-panic**: a structured, located, decision-typed artifact naming what is happening and what tier of judgment owns the call above it. Bare "failed" is invalid; the framing is the deliverable, and producing it is real work, which is what stops a node from escalating everything and acting on nothing.

### Conceptual foundation

Four distinctions, drawn from the surrounding architecture and information-theory work, determine why the pipeline has the stages it has. They are stated because the stage roles are arbitrary without them.

**Boundaries re-infer; they do not transmit.** A dispatch boundary is not a membrane that passes signal intact for re-evaluation. It is a place where one model collapses its context into a fresh artifact that seeds a different context. A caller collapses goal-plus-context into a dispatch prompt; the child's world is that prompt joined to its system prompt, not the caller's context; the child collapses its own accumulated context into a report; the report — not the child's findings — is what the caller receives. Each collapse is a lossy inference, and lossy in the dangerous direction: a synthesis can confabulate coherence and narrate an unresolved ambiguity into a resolved one. Every seam in the tree is such an inference. None is a safe deterministic pass-through.

**Envelope-approaching versus envelope-raising.** Pure reasoning over a fixed context can only recover signal already latent in that context — it approaches the Bayesian envelope of what the context implies; it cannot move it. Only crossing a boundary into the world (running a test, reading an unloaded file, observing an external fact) adds evidence new to the system and raises the envelope. A reasoner's contribution is bounded and, in principle, checkable against what it was given; a world-crosser's contribution is unbounded and unverifiable by a caller that never saw the world it touched. These are different operations, not different amounts of one operation.

**Caller-exogenous versus system-exogenous.** A child's report is almost entirely new to its caller, which is why dispatch beats injection regardless of lossiness — the loss falls on high-novelty material, so what survives still dominates the caller's prior on the subject. But "new to the caller" splits: a report can surface something derivable from the dispatch prompt that the caller simply hadn't computed (recovers under-extraction; new to the caller, not the system) or something fetched from the world (new to both). Only the second moves the system envelope. The two coincide exactly to the degree a world boundary was crossed downstream.

**Verification value is conditional on non-redundancy.** An added verifier signal improves a decision only if it is non-redundant relative to the terminal state. Self-critique — a verifier that only reasons over the synthesis it is checking — is bounded by the same information and cannot improve the envelope. An executable test can. A clear failure report is a high-information posterior update; a fabricated success replaces that signal with noise indistinguishable from evidence and corrupts everything downstream. This is the information-theoretic reason a leap must be checked across a boundary the leap could not see, and the reason fabricated success is worse than honest failure.

## Decision

Adopt the **Leap–Null–Falsify pipeline**: a candidate-insight generator and filter built from three uniform recursive nodes and one measurement gate, composed under five rules.

**1. Three node roles.**

- **Leap node** — samples off the dominant path (the controllable stand-in for the incubation phase reasoning cannot natively have) to produce a candidate claim. Its product is a candidate, never a conclusion. It explicitly does not audit its own leap; a node cannot both leave the manifold and check the departure in one pass.
- **Null-former node** — a cold, low-temperature node that converts the candidate claim into its sharp, falsifiable null. Forming a precise negation is deliberate dominant-path work and belongs in a different node from the leap for the same reason restructuring and verification are different operations. Its product is a null statement, not a verdict.
- **Falsifier node** — the only world-crossing node. It receives the *null* and attempts to *kill* it against exogenous evidence. Success is finding the evidence that falsifies the null. Its return shape is a framed sub-panic, not a verdict: "I could not falsify this; here is what would have falsified it and whether I looked." A return of mere supporting evidence has accomplished nothing.

**2. The null is the dispatch contract, not a hypothesis.** The Falsifier is never handed a claim to confirm. A claim handed to a world-crosser invites motivated retrieval — there is always some corroboration — and launders a confabulation through a citation. A null handed to a world-crosser invites attack. The asymmetry between confirming and failing-to-falsify is the entire epistemic value of the structure; Popper sits at the dispatch boundary.

**3. Two gates, held distinct.** A *geometry gate* and a *falsification gate* do different jobs and must not be conflated.

- The **geometry gate** routes spend. A directional measurement over the leap trajectory identifies candidates with an excursion-then-recohere signature — motion that left the prior line and was pulled into a new coherent line by the cold work downstream — and only those are worth the Falsifier's cost. Excursions that never recohere are noise, filtered before they incur a world-crossing call.
- The **falsification gate** governs belief. A candidate graduates from "compelling" to "credited" only when its null is attacked and survives the attempt — i.e. the Falsifier tried to disconfirm and failed. Geometry decides what to spend on; falsification decides what to believe. Conflating them lets a geometrically clean confabulation through.

**4. Ordering invariant.** Leap → cold null-formation → (geometry gate) → world-crossing. The cold stage between the leap and any world-crossing call is non-optional. Wiring a raw leap directly to the Falsifier builds a confabulation amplifier.

**5. Substrate-class invariant.** Only the Falsifier raises the envelope. The Leap and Null-former are pure-reasoning nodes: they recover latent structure and cannot add evidence. The pipeline is therefore a generator-and-filter for insight that is *latent-plus-checkable* — recombinations of what was already present, confirmed against the world. It is structurally incapable of manufacturing envelope-raising discovery except through the world-crossing stage, and its yield is low by construction. A high yield is the alarm, not the goal (see Failure Modes).

## Rationale

Each handoff strips a bias rather than carrying one. The Leap proposes under conditions that maximize access to non-dominant associations; the Null-former negates under conditions that maximize precision; the Falsifier attacks the negation against evidence neither prior node could reach. The pipeline is the human four-stage insight sequence — impasse, restructuring, felt rightness, and the empirical confirmation humans usually skip — reconstructed as an explicit schedule, with the part humans cannot consciously control (incubation) replaced by a controllable sampling regime and the part humans most often omit (disconfirmation) made a required stage.

Separating the two gates follows from the conceptual foundation: geometry is an internal-coherence signal and cannot certify truth, so it can only ever be a spend router; truth requires the non-redundant world-crossing signal, so only the falsification outcome can govern belief. Handing the Falsifier a null rather than a hypothesis follows from verification value: a verifier pointed at confirmation produces redundant signal toward a foregone answer; a verifier pointed at disconfirmation produces the non-redundant update that can actually move the envelope.

### Positive consequences

- The brake is structural. Because the Falsifier's contract rewards "here is what would disconfirm this and whether I found it" over "here is support," the loop's resistance does not decay as candidates get more fluent — the failure mode named in Context is closed by construction rather than by vigilance.
- Compression is biased toward novelty. A well-formed report drops the restatement of what the node was told and keeps what it found, so each boundary spends its fidelity budget on the exogenous fraction.
- The geometry gate makes the expensive stage economical: world-crossing fires only on candidates whose trajectory already shows the recohere signature.

### Negative consequences

- Low yield is intrinsic. Most leaps die at the geometry gate or come back from the Falsifier as "compelling but unsupported." This is the system working.
- The cold null-formation stage and the directional measurement's null-calibration are mandatory overhead on every candidate, not optional polish.
- The Falsifier's contribution is unverifiable by its caller, since the caller never sees the world it touched. The pipeline's correctness rests on collapse fidelity at that boundary — the same trust the whole stack defers to, now concentrated at the one envelope-raising seam.
- Value is bounded by Falsifier quality. A Falsifier without genuine world access can confirm internal coherence only; it cannot certify truth, and a pure-reasoning verifier asked "is this true" reverts the pipeline to envelope-approaching.

## Failure Modes the Design Prevents

These are first-class, not an appendix, because each is a way the brake silently disengages.

- **Confabulation laundry.** Leap wired to world-crossing with no cold gate: warm sampling emits a plausible falsehood, the world-crosser retrieves the always-available corroboration, and a hallucination exits framed as a finding. Prevented by the ordering invariant and rule 2.
- **Confirmation-shaped dispatch.** Handing the Falsifier a hypothesis instead of a null. Prevented by rule 2.
- **Faked world-crossing.** A node presented as world-grounded whose tool calls are simulated is exogenous-signal-free and behaves like a pure-reasoning node wearing a costume; a single such node reverts the regime to accumulation/self-relay. Prevented only by the world boundary being real, which is a substrate-enforcement question (see below), not a contract clause.
- **Instrument circularity.** Using the same embedding-diversity measure to both generate/select candidate material and to validate the regime closes a loop in which the material confirms the regime because it was selected to. The measurement may gate the dataset or measure the window, never both on the same data.
- **Pretty-convergence inflation (the meta-alarm).** Reading the pipeline's output as discovery when a gate has gone slack. If the system ever feels like it is producing insights *reliably*, the cold gate or the disconfirmation discipline has weakened and its output is a laundry's, not a discovery's. The designed-low yield is the health signal; its disappearance is the warning.

## Enforcement Split (structural vs. prose)

Where each rule actually binds depends on substrate, and the document must not pretend otherwise.

| Rule | Structurally enforceable (e.g. graph layer with typed edges, tool-whitelisted forks) | Prose-enforced only (e.g. a frontier chat harness) |
|------|---|---|
| Three roles separated | Distinct nodes with scoped tool access | Sections of one context the model is asked to keep separate |
| Null-as-contract | Falsifier's input type is a null; no confirm path exists | Instruction the model must remember to honor |
| Ordering invariant | Edge topology forbids leap→world directly | Convention |
| World boundary is real | Tool-whitelist guarantees actual execution | Cannot be guaranteed; faked-crossing risk is live |
| Yield as health metric | Instrumented and logged | Operator attention |

On a substrate that can enforce the edges, the advantage is structural. On a prose-only substrate it holds by the model remembering to, and the faked-world-crossing failure mode in particular cannot be closed.

## Alternatives Considered

### Option A: World-crossing fired directly on raw leaps
**Why rejected:** This is the confabulation laundry. Without the cold gate, the expensive verifier spends itself corroborating warm noise.

### Option B: Hand the verifier a hypothesis to confirm
**Why rejected:** Confirmation invites motivated retrieval. The structure's epistemic value is the confirm/fail-to-falsify asymmetry, which only a null preserves.

### Option C: A single global warm temperature instead of a localized leap
**Why rejected:** Global warmth buys restructuring at the cost of coherence everywhere and cannot be hot for the leap and cold for the audit in the same pass. Localizing the excursion to one node and running its dependents cold is the only way to put temperature where restructuring belongs and keep it out of where checking belongs.

### Option D: Pure-reasoning verification, no world-crossing
**Why rejected:** A reasoning-only verifier can confirm a leap was latent in its premises but never that it is true. It leaves the pipeline envelope-approaching. The world-crossing stage is the only envelope-raiser and is not optional if the claim is "discovery" rather than "extraction."

### Option E: One combined gate (geometry and falsification fused)
**Why rejected:** Geometry certifies coherence, not truth; using it to govern belief admits geometrically clean confabulations. The two filters measure different things at different stages and must stay separate.

## Open Questions

- [ ] **Decomposability / decision-to-execute signal — the load-bearing unvalidated dependency.** The whole substrate, and therefore this pipeline, rests on a node reliably knowing when to stop orchestrating and act, and when to decompose. It is unmeasured. The pipeline is argument-stage until it is validated. **Resolution trigger:** measure the signal against the actual models in use — does a node elect a tool-call when warranted and decompose when warranted? This likely belongs upstream of this document, in a substrate requirements doc; this spec inherits the dependency and does not discharge it.
- [ ] **Geometry-gate anchor quality.** The directional measurement projects onto an axis defined by anchor texts; a poor anchor pair yields a confident projection onto a meaningless direction. The gate is only as good as its axis. **Resolution trigger:** the axis-validity work in the measurement limb (whether the target behavioral axes are one manifold or several; whether a separately-trained judge's score tracks the projected component). Until then the geometry gate is a heuristic spend-router, not a validated filter.
- [ ] **Falsifier-quality bound.** Value is capped by the Falsifier's genuine world access; a coherence-only verifier silently degrades the pipeline to envelope-approaching. **Resolution trigger:** confirm, per instantiation, that the world-crossing stage executes rather than reasons.
- [ ] **Yield-rate calibration.** What survival rate at each gate indicates the gates are working versus slack? Both an implausibly high yield and a zero yield are failures. **Resolution trigger:** establish a baseline on the first real corpus run; treat drift toward high yield as a slack-gate alarm.
- [ ] **External magnitudes.** Some supporting figures in the source literature are abstract-verified but body-unverified. **Resolution trigger:** verify any specific magnitude before it becomes load-bearing in an experiment design; prefer designs whose own instrument produces the effect size directly and need no imported number.
- [ ] **Series placement and family code.** `LNF-0001` is now confirmed (see promotion note above).

## Supersession Relationships

**Supersedes:** —
**Superseded by:** TBD — a future revision may promote this from a frame to a method once the decomposability signal and the geometry-gate axis are validated, at which point the first two open questions' resolutions become the body of a follow-on record.

## Recursive Self-Application

Every claim in this document is a leap whose null has not yet been attacked. The status is *proposed*, the genre is frame-not-method, and the convergence it describes is clean enough to warrant suspicion rather than confidence. The discipline the spec demands of the pipeline applies to the spec: the cheapest experiment that could embarrass the most attractive claim is the first falsification attempt the document owes itself. The leap-trajectory-with-and-without-warm-sampling measurement is that experiment — it can return a null (no distinct excursion-then-recohere geometry; warm sampling looks like noise), and that null would cleanly disconfirm the most seductive part of the design. Running the experiment that could break it, before building on it, is the externalized form of the same brake the pipeline is built around.

---

## Appendix A: Reference Instantiation (illustrative, not part of the portable spec)

The pipeline was derived against a concrete three-tool composition. It is recorded here as one instantiation, not as the design; any tools that fill the roles and honor the rules qualify.

- **Leap node ← a reasoning decomposer with a temperature control.** A decomposition-into-atomic-subquestions reasoner gives localized excursions: a single hypothesis atom can be sampled at elevated temperature (the incubation stand-in) while its dependent atoms run cold (the audit). Temperature is the controllable source of the non-dominant association that incubation supplies in humans. Note this tool is pure-reasoning and zero-exogenous by construction, which makes it a clean control as well as a leap engine.
- **Geometry gate ← a directional-projection measurement.** A read-only, black-box-embedding projection of a trajectory onto a named axis supplies the excursion-then-recohere routing signal. It carries its own discipline: a measured (not assumed) null for the anisotropic embedding space, and a single embedder per measurement. It is a measurement element, not a node — it does not orchestrate or escalate.
- **Falsifier ← a world-crossing research node.** The only envelope-raiser. It must execute (retrieve, test, observe), receive a null, and return a framed sub-panic that foregrounds disconfirmation: "evidence is mixed / sources conflict / I could not find a disconfirming test" must be a first-class return, because the failure mode of a researcher asked to confirm is motivated retrieval toward yes.

All three are composable MCP-style tools, which is what makes the composition cheap to assemble; it is also what makes the faked-world-crossing failure mode easy to introduce, so the world boundary's reality is the thing to verify first in this instantiation.

## Appendix B: Mapping to Source Architecture

- The uniform recursive node, resolution order, contract-property leaf-ness, and framed sub-panic are inherited from the orchestration limb of the surrounding architecture.
- The directional projection primitive (signed component, orthogonal residual, measured null, single-embedder constraint) is the measurement limb.
- The diversity instrument (chunk, embed, mean pairwise distance, canary survival) and the three context-collapse failure modes (resonance chamber, theory-of-mind drift, compaction closure / directive-becomes-narrative) come from the context-layer work.
- The null-hypothesis genre, the substrate-enforcement split, and the instrument-circularity caution come from the subagent-call-density note.
- The disposition (direction over magnitude; discipline over cleanup; the boundary as the unit of governance) and the decomposability ≡ dimensionality identity come from the story-shaped-stack synthesis.

---

## Bibliography

### Internal lineage
- *ADR-0007: The Uniform Recursive Orchestrator and the Local-First Inversion.* The node substrate, resolution order, contract-property leaf-ness, typed escalation, and the decomposability open question.
- *ADR-SKMCP-0001: Directional Projection Primitive for sk-mcp.* The geometry gate's measurement and its anchor-quality and null-calibration cautions.
- *ADR-CORE-079: Context Layer Architecture — Per-Inference-Call Curation as Infrastructure.* The diversity instrument, the three context-collapse failure modes, and the verification-value corollary.
- *Null Hypothesis: Subagent-First Decomposition Preserves Top-Level Call Density Across Long Sessions.* The H₀/H₁ form, the substrate-enforcement split, the instrument-circularity caution, and the faked-/leaked-child reversion condition.
- *The Story-Shaped Stack: A Synthesis.* The three-commitment disposition and the decomposability ≡ dimensionality identity.
- *git.md* (VCS leaf contract) and *decompose-problem.md* (decomposition contract). Reference contracts for the framed sub-panic return shape, the no-fabrication / blocked-result discipline, and the escalation-signals field.

### External
- Teng, F., Shi, Q., Yu, Z., Zhang, J., Luo, Y., Wu, C., & Guo, Z. (2025). *Atom of Thoughts for Markov LLM Test-Time Scaling.* arXiv:2502.12018. (Decomposition-contraction into atomic, self-contained subquestions; the reference Leap-node instantiation.)
- Ao, Gao & Simchi-Levi (2026). *On the Reliability Limits of LLM-Based Multi-Agent Planning.* arXiv:2603.26993. (Delegation limit, posterior-distortion, and verification-value results. Note: abstract verified; body figures reported but not independently verified — see Open Questions before leaning on specific magnitudes.)
- Hubinger et al. (2024). *Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training.* Anthropic. (On why lossy self-summary can teach concealment rather than preservation.)
- Jung-Beeman, M., Bowden, E. M., Haberman, J., Frymiare, J. L., Arambel-Liu, S., Greenblatt, R., Reber, P. J., & Kounios, J. (2004). *Neural Activity When People Solve Verbal Problems with Insight.* PLoS Biology, 2(4), e97. (The gamma-band burst over right anterior superior temporal gyrus ~0.3 s before insight solutions; the insight-vs-analytic contrast.)
- Bowden, E. M., Jung-Beeman, M., Fleck, J., & Kounios, J. (2005). *New approaches to demystifying insight.* Trends in Cognitive Sciences, 9(7), 322–328. (The four-stage account and the analytic/insight distinction.)
- Kounios, J., et al. (2008). *The origins of insight in resting-state brain activity.* Neuropsychologia. (Pre-stimulus neural state predicting subsequent solution by insight.)
