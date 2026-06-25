# ADR-LNF-0002: Falsifier Amendments — Iterative Null Re-formation, Coefficient-Correction Return, Numeric-Discriminator-First Ordering

**Status:** proposed
**Date:** 2026-06-24 (US/Mountain)
**Author:** shanevcantwell, with Claude (orchestrator) as drafting collaborator
**Related:** ADR-LNF-0001 (refines its Null-former node role, its Falsifier return shape, and the Appendix-A Falsifier instantiation); ADR-LNF-0003 (coefficient-correction / non-discriminating return shapes reused there as score-role shapes)
**Supersedes:** —
**Superseded by:** —

> **Promotion note (2026-06-24):** Promoted from design-docs/incoming-ideas/ into leap-null-falsify, the canon home for the LNF discipline. ADR-LNF-0003 was re-coded from ADR-AOT-0001.

---

## Context

ADR-LNF-0001 specified the pipeline almost entirely against **fabrication-class** failure: confabulation laundry, confirmation-shaped dispatch, faked world-crossing, instrument circularity, pretty-convergence inflation. A single empirical run exercised the pipeline against a real claim and showed the dominant failure for memory- and estimate-grade claims is *not* fabrication.

The run: audit a memory-grade claim of the form "term X was applied to me repeatedly by source Y" against a local corpus, world-crossing via `grep`/word-count rather than semantic research. The outcome was that the claim's **kernel was sound** (the term existed; attribution to source Y was correct, every time) but its **magnitude was inflated** — one authored arc, re-circulated by the claimant across surfaces, felt from inside as "many occasions." The felt error was a *quantity* error wearing a *quality* claim's clothes ("repeatedly," "became its own thing").

ADR-LNF-0001 has no contract for "directionally right, quantitatively wrong," and the run only reached the finding by departing from the spec in three specific ways. This record promotes those departures to contract.

## Decision

Three amendments to the LNF node contracts.

### 1. The Null-former is iterative; a cheaply-surviving null is a wrong-axis signal, not evidence.

ADR-LNF-0001 treats null-formation as one cold pass producing *the* sharp negation. In the run, the first plausible null — "the term does not appear in the data" — survived trivially (it appears). Read naively that survival *confirms the felt story and halts the inquiry*. The discriminating null was on a different axis entirely: not *does it exist* but *what is its provenance and volume*. The finding existed only because the null was re-formed after the first came back cheaply true.

- **New, distinct failure mode — motivated null-selection.** Choosing the negation easiest to attack rather than the one that discriminates. This is *not* the existing "confirmation-shaped dispatch" (rule 2), which concerns handing the Falsifier a hypothesis; motivated null-selection happens one node earlier, inside the Null-former, and is invisible to a downstream Falsifier doing its job correctly on the null it was given.
- **Contract change.** The Null-former MAY emit multiple candidate nulls ranked by expected discriminating power, and a null that the Falsifier resolves (kills *or* confirms) at trivial cost returns as **`non-discriminating — re-form`**, not as a verdict. A trivially-surviving null is an alarm that the wrong axis was negated, on the same footing as ADR-LNF-0001's "high yield is the alarm."

### 2. Add a coefficient-correction return type to the Falsifier.

ADR-LNF-0001's return shapes are survived / falsified / framed-sub-panic. None expresses the run's actual — and most useful — outcome: *direction right, magnitude wrong*.

- **Contract change.** Add **`coefficient-correction`**: `{ kernel: sound, direction: <verdict>, magnitude: corrected, coefficient: <value/factor>, basis: <the exogenous measurement> }`. A kill/survive-only Falsifier discards the correction, which was this run's entire yield. The return carries both the direction verdict and the magnitude correction, because the common real result is neither full kill nor clean survival.

### 3. Bias world-crossing toward the cheapest numeric discriminator first.

ADR-LNF-0001's reference Falsifier (Appendix A) is framed as a "world-crossing research node" — retrieval and reasoning. The run's highest-yield world-crossing was **arithmetic**: a count, a provenance tally, a who-said-it breakdown.

- **Contract change.** Falsifier instantiation orders its attempts: **cheapest exogenous numeric discriminator first** (count, frequency, provenance tally, date span), semantic retrieval only if the numeric pass is non-discriminating. Numeric discriminators are cheap, hard to confabulate, and catch the **over-weighted-salience** error class that semantic verification sails past, because they directly measure the quantity a magnitude-inflated claim misstates.
- **SKMCP discipline carried forward.** A numeric discriminator that is itself an embedding/projection *magnitude* still needs ADR-SKMCP-0001's measured null. A raw `grep | wc -l` or provenance tally does not — which is part of *why* it ranks first: it is both cheaper and free of the anisotropy-calibration overhead.

## Rationale

The unifying correction: ADR-LNF-0001 is built for **catching lies**; the everyday job of a personal Falsifier is **fixing the volume knob on things that are basically true**. Memory- and estimate-grade claims fail far more often by miscalibrated magnitude on a sound kernel than by fabrication. The three amendments each address a stage where the fabrication-only framing under-served that case — null selection (1), return shape (2), and discriminator choice (3).

### Positive Consequences

- The pipeline now yields its most common high-information result (corrected magnitude) instead of forcing it into a binary that discards it.
- Motivated null-selection becomes a named, catchable failure at the Null-former rather than an invisible one masked by a correctly-functioning Falsifier.
- Numeric-first ordering lowers per-claim cost and raises confabulation resistance simultaneously; the cheap path is also the more honest one, which inverts the usual cost/rigor trade-off.

### Negative Consequences

- The `coefficient-correction` return and the multi-null re-form loop add branches the orchestrator must handle; the contract is no longer a clean tri-state.
- Numeric-first risks a *new* motivated-selection at the discriminator level (picking the count that flatters), which the re-form discipline (1) must also police — the alarm is a discriminator that resolves the null too cheaply.
- Ranking nulls by "expected discriminating power" is itself an estimate; a poorly-ranked null set re-introduces the wrong-axis problem one level up. No measured guard for this yet (see Open Questions).

## Alternatives Considered

### Option A: Keep the tri-state return; express magnitude corrections as a fresh claim fed back through the pipeline.
**Why rejected:** Loses the link between the original kernel and its correction, and re-pays the full pipeline cost to record a result already in hand. The correction is a property of *this* falsification, not a new candidate.

### Option B: Single-pass Null-former with a "sharpness" check instead of a re-form loop.
**Why rejected:** A sharpness heuristic on the null in isolation cannot see that it is on the wrong *axis* — "term does not exist" is a perfectly sharp null that happens not to discriminate. Only attempting it and observing trivial resolution reveals the axis error, which is exactly the re-form loop.

## Open Questions

- [ ] **Null-ranking metric.** Is "expected discriminating power" measurable before the world-crossing, or only observable as trivial-vs-costly resolution after? **Resolution trigger:** first batch of real runs — log first-null-survival-cost against whether a re-form was needed; if trivial-survival reliably predicts wrong-axis, the post-hoc signal suffices and no pre-ranking metric is needed.
- [ ] **Coefficient basis typing.** Should `coefficient` be constrained to a typed basis (ratio, count-delta, date-span) or free-form? **Resolution trigger:** decide when wiring the return into the orchestrator's branch handling.
- [ ] **Discriminator-selection guard.** What prevents motivated *discriminator* selection (the count that flatters) beyond the re-form alarm? **Resolution trigger:** if the alarm proves insufficient in practice, consider requiring the Null-former to pre-commit the discriminating axis before the Falsifier picks the count.

## Supersession Relationships

**Supersedes:** — (refines ADR-LNF-0001's §1 Null-former role, its Falsifier return shape, and Appendix A; ADR-LNF-0001 should gain a back-reference: "Null-former role and Falsifier return shape refined by ADR-LNF-0002.")
**Superseded by:** TBD — folds into the ADR-LNF-0001 follow-on "frame → method" promotion once the decomposability signal and geometry-gate axis are validated.

## Notes

The amendments are derived from a single run and are themselves a leap whose null has not been attacked. The cheapest experiment that could embarrass them: replay several memory-grade claims through the amended contracts and check whether `coefficient-correction` is in fact the modal outcome (the design's central empirical bet) rather than a rare one. If kills/survivals dominate in practice, amendment (2) is over-fitted to one vivid case and should narrow.
