# ADR-LNF-0003: Investigation-Scored Atoms as a Human–LLM Conceptual-Expansion Medium

**Status:** proposed
**Date:** 2026-06-25 (US/Mountain)
**Author:** shanevcantwell, with Claude (Opus 4.8) as drafting collaborator
**Related:** ADR-LNF-0001 (supplies the gate discipline and the fabrication-class failure modes this medium must police); ADR-LNF-0002 (coefficient-correction / non-discriminating return shapes, reused here as score-role shapes); the contract-vs-system encapsulation discipline developed in the originating conversation (no ADR yet — see Open Questions)
**Supersedes:** —
**Superseded by:** —

> **Promotion note (2026-06-25):** Promoted from design-docs/incoming-ideas/ into leap-null-falsify; re-coded from ADR-AOT-0001 since AOT folds into the LNF discipline.

---

## Context

The originating work is a recurring failure in LLM-assisted conceptual work: the model up-projects a *concept* well (resolves a region to its highest-probability occupant) but cannot up-project conceptual *space* (hold a region under-determined for inspection), because the completion objective is convergent by construction — every emitted token is a commitment, and there is no token that means "decline to converge." The observable symptom is that the model fills open regions with vivid labeled nodes that read as progress while actually collapsing the degree of freedom that was the point. Within the originating conversation this fired repeatedly and was caught each time (an endocrine→hyperparameter identity claim, a "clamp" primitive collapse, a fabricated user-held-belief used to manufacture pushback, an unattacked leap stated as a survived finding).

A candidate substrate exists — the Atom of Thoughts pattern (decompose into typed atoms, dependency graph, per-node confidence, auto-terminate on high confidence; reference impl `dioptx/mcp-atom-of-thoughts`, early-stage). Its *substrate* (typed atoms + graph + externalized ledger) is sound; its *control policy* (confidence-monotonic termination) is the collapse gradient with a number on it and must be stripped.

The motivating reframe — supplied by the user and load-bearing for this whole record — is that "weight" is **not** a system operation on the model (no conditioning-tensor adjustment). It is **metadata carried in the prose presentation** that the model reasons *from*, the same way it reasons from any context. This collapses an entire class of instrument-circularity worry that applies only to system-computed-and-applied scores.

## Decision

Adopt the following as the committed (gelled) shape of the medium. These are the claims that survived probing in the originating conversation.

1. **The atom's primitive axis is seal-state, not confidence.** Each atom carries a state on a *sealed-as-contract ↔ opened-as-system* axis (the encapsulation discipline), which is orthogonal-and-bidirectional, **replacing** AoT's confidence scalar, which is monotone-toward-collapse. Confidence scores how closed a node is and therefore drives settling; seal-state can move either direction on warrant.

2. **Investigation-score is orthogonal to truth-value and is not a scalar.** What an atom carries is *how much investigation it has absorbed* and *in what role its result is admissible* — explicitly decoupled from whether it is true. A heavily-investigated *falsified* atom and an unattacked *leap* can share a truth-value and differ entirely in investigation-state. The score's first job is to defeat the flat-context pathology where a just-generated leap carries the same weight as an earned finding (a Whispering-Gallery-Effect in miniature: under-investigated self-generated tokens re-attended as if ground).

3. **Weight is role-admissibility, not magnitude.** The score does not gate *how much* a concept is weighted; it gates *in what role* the concept is admissible: `citable-as-warning` / `buildable-as-foundation` / `live-question-explorable-not-standable`. This is the key correction to the naïve "down-weight bad atoms" framing: a falsified atom (e.g. the endocrine mapping) is load-bearing *as a cautionary boundary* and must be loud-as-warning while silent-as-premise.

4. **The score is carried in presentation register, per axis, not applied by the system.** An atom is rendered into the prose stream in a register chosen by its state: a *solved* axis arrives **formalized/sealed** (here is the contract, build on it); an *open* axis arrives **de-formalized** (prose that holds the region loose), because formalizing an open axis hands the model a closed node it will complete on. Register *is* the seal/open operation, performed at render-time rather than as a mid-reasoning flip. Crucially this is **per-axis within a single atom** — one concept may be sealed on one axis and held open on another and must be rendered in mixed register accordingly.

5. **The exogenous anomaly source is the human; scoring is co-produced / human-auditable, never solely LLM-minted.** Because the model both proposes atoms and would judge their seal integrity, self-scoring is instrument circularity (ADR-LNF-0001's named failure). The human supplies the interface-anomaly that warrants a flip ("that atom's external behavior doesn't match its contract — open it" / "you've opened three levels and found nothing new — re-seal"). This is what the human-communicating-through-atoms channel is *structurally for*, not a UI nicety.

## Rationale

The unifying move: AoT's atom has one degree of freedom (confidence) that is monotone toward collapse, so any system built on it inherits the settle-gradient as its control policy. Replacing that DoF with an orthogonal, bidirectional seal-state, and carrying investigation-state as reasoned-from presentation metadata rather than an applied weight, gives a medium whose primitives do not themselves pull toward premature convergence. ADR-LNF-0001 supplies the policy that AoT lacks (gates on surviving falsification, not on rising confidence); this ADR supplies the *medium* that lets a human and an LLM co-hold the graph where neither party's completion gradient can quietly collapse it.

### Positive Consequences
- Defeats flat-context status-flattening: provenance/investigation travels with each concept, so a leap cannot be silently built upon as if earned.
- The "metadata reasoned-from, not weight applied" framing removes the system-scored circularity problem at the root rather than guarding against it.
- Role-admissibility preserves the *value* of falsified atoms (cautionary boundaries) that a magnitude dial would discard — directly reusing ADR-LNF-0002's coefficient-correction insight (direction and magnitude separate) at the score level.
- Per-axis register lets a single concept be simultaneously stood-upon (sealed axis) and explored (open axis) without the model collapsing the open part.

### Negative Consequences
- Per-axis mixed-register rendering is unproven and may be infeasible: formalized portions of an atom may drag adjacent loose portions closed by proximity (see Open Questions — this is the keystone risk).
- Co-produced scoring requires sustained human attention as the anomaly source; the medium does not function autonomously and is not meant to.
- The whole construct is composed, not validated. None of it has been run, even by hand.

## Alternatives Considered

### Option A: Adopt Atom-of-Thoughts wholesale (confidence scalar + auto-terminate-on-high-confidence).
**Why rejected:** Re-imports the exact convergence gradient the medium exists to resist. Confidence-monotonic termination is an inward-collapse rule dressed as rigor; AoT-Verification is confirmation-shaped dispatch (ADR-LNF-0001 failure mode), not falsification. Substrate kept, control policy discarded. This is the alternative that *fits cleanly*, which is precisely why it is dangerous and why it is recorded.

### Option B: Score as a system-applied weight (e.g. influencing sampling / conditioning).
**Why rejected:** Mis-locates the lever. "Weight applied to the model" makes "who assigns the score" load-bearing and self-scoring poisonous. The user's reframe — weight as prose-carried metadata the model reasons from — dissolves this; the score becomes ordinary context whose only open question is accuracy, not a measurement the instrument takes of itself.

### Option C: Single seal-state per atom (not per-axis).
**Why rejected:** A real concept routinely has one axis gelled and another live (e.g. "investigation-score is orthogonal to confidence" is settled; "what the axes are" is open). Whole-atom seal-state forces a concept to be presented as either fully sealed or fully open, collapsing live axes or loosening solid ones. Per-axis register is required even though it is the riskiest part to implement.

## Open Questions

- [ ] **Per-axis register proximity-bleed (keystone).** Can one atom be rendered with some axes formalized and others deliberately loose *without the formalized parts dragging the loose ones closed*? **Resolution trigger:** the first hand-authored atom — render a mixed-register concept and check whether the model treats the loose axis as genuinely open or completes on it anyway.
- [ ] **What are the actual axes?** The medium commits that investigation-state is multi-axis and non-scalar, but the axes themselves are deliberately undefined here (defining them now would be inventing a schema — the failure mode this medium describes). **Resolution trigger:** derive axes empirically from hand-scoring the atoms of the originating conversation; do not specify a priori.
- [ ] **Score-accuracy auditing.** With scoring co-produced, what catches an *inaccurate* score (human or model mis-grading investigation-state)? **Resolution trigger:** if mis-scoring shows up in the first hand runs, consider whether the human-as-anomaly-source loop is sufficient or needs an explicit re-score trigger.
- [ ] **Relationship to the contract/system encapsulation discipline.** That discipline has no ADR of its own yet but is a dependency of decision (1). **Resolution trigger:** capture it as its own ADR before this one is promoted past `proposed`, so (1) rests on a recorded primitive rather than a conversational one.
- [ ] **LNF prioritization gap (carried, *not* established).** A claim arose that LNF ranks by verdict and lacks a scalar to prioritize which open region to spend on next, and that an investigation-score might fill it. **This was a leap stated as a finding and caught as such — it is recorded here as an unattacked null, not a motivation.** **Resolution trigger:** only becomes load-bearing if (a) AoT is actually inspected and ranks the way guessed, *and* (b) LNF prioritization is found genuinely underspecified in practice.

## Supersession Relationships

**Supersedes:** —
**Superseded by:** TBD — expected to fold into a follow-on once axes are empirically derived (Open Question 2) and the per-axis rendering question (Open Question 1) is resolved, at which point "proposed medium" promotes to "specified medium."

## Notes

The central empirical bet — and the cheapest experiment that could embarrass this entire record — is to **hand-score the atoms of the originating conversation** (the endocrine mapping as falsified/cautionary, memory-as-one-engine as survived/foundational, the contract-system flip as composed/gelled-in-shape-open-in-protocol, the LNF-prioritization claim as unattacked-leap) and check whether the role-admissibility that falls out matches what the user's own judgment already does with them silently. If hand-scoring produces role assignments that diverge from lived judgment, decision (3) is wrong and the score is doing something other than what it claims.

A note on this document's own hazard: an ADR format pulls toward stating decisions, and several axes here are deliberately open. The draft has been written to keep gelled commitments in Decision and push live axes into Open Questions with honest investigation-grades — including flagging which atoms from the source thread are leaps versus survivors — so the record does not commit the formalize-an-open-axis failure it describes. Whether it fully succeeds at that is itself an open question the reader should probe in clean context.
