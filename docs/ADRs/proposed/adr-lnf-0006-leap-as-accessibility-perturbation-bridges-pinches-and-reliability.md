# ADR-LNF-0006: Leap as Accessibility Perturbation — Bridges, Pinches, and Reachability

**Status:** proposed
**Date:** 2026-09-23 (US/Mountain)
**Author:** shanevcantwell, with model collaborator
**Related:** ADR-LNF-0001; ADR-LNF-0002; ADR-LNF-0003; ADR-LNF-0005 (Falsifier as a distinct stateless world-crossing category); ADR-LNF-0007 (proposed clarification of bridge/pinch measurement layers); sk-mcp funnel / reinforcing-alignment measurement work
**Supersedes:** —
**Superseded by:** —

---

## Context

ADR-LNF-0001 defines the Leap node as sampling off the dominant path to produce a
candidate claim.

That definition is operationally useful but underspecified about what a successful
leap actually does.

"Off the dominant path" can describe several very different phenomena:

- ordinary sampling variance;
- lexical novelty;
- random semantic displacement;
- movement into a nearby but under-sampled region;
- traversal through a narrow connection between otherwise weakly connected
  semantic regions;
- a contextual intervention that temporarily changes which regions are easily
  reachable from one another.

Only some of these are useful.

Increasing temperature, diversity, or embedding distance is therefore not itself
a successful Leap. Those interventions can produce larger excursions while
reducing the probability of finding coherent latent structure.

A more useful first-principles interpretation is:

> **Leap is a controlled perturbation of semantic accessibility.**

Its purpose is not merely to move farther from the dominant trajectory.

Its purpose is to increase access to coherent candidate structure that was latent
in the available information but unlikely to be reached under the ordinary
inference trajectory.

This suggests a distinction among three statements:

    a region exists
    a region is reachable
    a region is likely to be reached

These are not equivalent.

A model may contain or be capable of expressing a relation that ordinary
inference almost never traverses.

The Leap may therefore work by changing **reachability** rather than by creating
new information.

This interpretation is consistent with the LNF substrate invariant:

> Leap remains envelope-approaching.

It may expose a latent relation that ordinary inference fails to recover, but it
does not establish that the relation corresponds to the external world. Only the
Falsifier may raise the evidentiary envelope.

---

## Decision

Refine the LNF Leap contract:

> **The Leap node is a controlled accessibility perturbation whose objective is
> to increase the probability of reaching coherent, non-dominant candidate
> structure without treating geometric novelty as evidence of truth.**

The Leap should therefore be evaluated primarily by changes in **trajectory
accessibility**, not by raw diversity, temperature, distance, or novelty.

This ADR introduces two geometric hypotheses for how a Leap may produce such a
change:

1. **Bridge discovery**
2. **Pinch-like accessibility deformation**

These are competing/measurably distinguishable hypotheses, not assumptions about
literal hidden-state topology.

The terms initially refer to **observed behavioral / emission-space geometry**.

No claim about actual internal neural manifolds is permitted without independent
internal-state measurement.

---

## Existing pipeline remains unchanged

The pipeline ordering remains:

    Leap
        ↓
    Null-former
        ↓
    geometry gate
        ↓
    Falsifier / world crossing

This ADR refines what the Leap and geometry gate may measure.

It does not weaken the existing rule:

> Geometry routes spend. Falsification governs belief.

A beautiful bridge in semantic space can still connect two false ideas.

A successful pinch can still produce an elegant confabulation.

World crossing remains mandatory before promotion from candidate to credited
claim.

---

## Accessibility rather than distance

Let a baseline context be `C`.

Let `L` be a Leap intervention.

Let `T` denote the model-and-decoding process producing a trajectory through
observable semantic states:

    τ0 = T(C)

and under the Leap intervention:

    τL = T(C + L)

The central measurement question is not:

    distance(τ0, τL) > 0 ?

That only establishes that the prompt changed behavior.

Instead ask:

> Does `L` make coherent regions reachable that are rarely reached under matched
> baseline inference?

For two observable semantic regions `A` and `B`, define a behavioral accessibility
quantity:

    R(B | A, C)

representing the empirical probability that trajectories beginning in or passing
through region `A` subsequently enter region `B` under context `C`.

The Leap effect is then:

    ΔR = R(B | A, C + L) - R(B | A, C)

The exact estimator is an implementation question.

The conceptual object is the change in reachability.

---

## Bridge hypothesis

A **bridge** exists when ordinary inference already contains a coherent but
low-probability route between two regions.

Conceptually:

    A → r1 → r2 → ... → B

where the intermediate trajectory exists under baseline conditions but is rarely
sampled.

The Leap increases the probability of entering that route.

Expected signatures include:

- the same or closely related intermediate regions occasionally appear in
  baseline samples;
- the Leap substantially increases their visitation frequency;
- trajectory length/path structure remains broadly recognizable;
- removing the Leap returns access probability toward baseline;
- the Leap does not require broad contraction of unrelated semantic regions.

Under this hypothesis, the Leap does not create a connection.

It makes an existing low-probability connection easier to traverse.

---

## Pinch hypothesis

A stronger possibility is that contextual conditioning changes effective
accessibility enough that regions which are distant under ordinary inference
become locally easier to traverse between.

Call this a **pinch-like accessibility deformation**.

Conceptually:

Baseline:

    A ----------- difficult / low-probability transition ----------- B

Under Leap:

    A ---- B

The term "pinch" is intentionally geometric but operationally conservative.

It does **not** mean this ADR asserts that an internal neural manifold literally
folds or pinches.

The measurable claim is:

> Under the Leap condition, transitions between previously weakly connected
> behavioral regions become substantially shorter, more frequent, or available
> through multiple newly favored trajectories.

A pinch-like result differs from bridge discovery because it need not reveal one
pre-existing narrow corridor.

Instead the intervention changes the effective transition structure itself.

---

## Bridge versus pinch discriminator

The two hypotheses should be distinguished experimentally.

### Bridge prediction

The intervention amplifies a rare baseline route.

Therefore:

    route_L ≈ rare(route_baseline)

Evidence would include baseline samples that occasionally traverse substantially
the same intermediate neighborhood.

### Pinch prediction

The intervention changes transition accessibility in a way not well explained by
amplifying one rare baseline path.

Therefore:

    route_L != simply more frequent baseline route

Possible signatures include:

- shorter semantic path length;
- multiple distinct trajectories now connecting A and B;
- changed neighborhood relations;
- increased cross-region transition rate without one dominant intermediate path;
- altered local transition probabilities around both A and B.

### Null

Both apparent effects may reduce to:

- increased temperature;
- generic semantic dispersion;
- verbosity;
- lexical novelty;
- embedding anisotropy;
- selection of unusually vivid trajectories after the fact.

These must be explicit controls.

---

## Leap success criteria

A successful Leap must satisfy more than novelty.

### 1. Accessibility gain

A coherent candidate region becomes measurably more reachable than under matched
baseline conditions.

### 2. Candidate coherence

The reached material recoheres into a candidate that can be stated precisely
enough for the Null-former.

A trajectory that merely continues wandering is not a successful Leap.

### 3. Non-triviality

The candidate is not already a dominant baseline completion.

### 4. Reproducibility at population level

The accessibility effect appears across enough matched samples to distinguish it
from one lucky generation.

### 5. Selectivity

The intervention does not merely increase access to *everything*.

Generic dispersion is not controlled accessibility.

### 6. Independence from truth certification

No geometric success criterion may promote the candidate to belief.

That remains the Falsifier's job.

---

## The geometry gate changes role slightly

ADR-LNF-0001 describes the geometry gate primarily in terms of an
excursion-then-recohere signature.

Retain that signal, but extend the gate to ask:

    Was this merely an excursion?

or:

    Did the excursion expose a reproducible accessibility change?

The gate may therefore retain several separate measurements:

    excursion magnitude
    recoherence
    accessibility gain
    path consistency
    residual/global dispersion
    candidate-region visitation frequency

Do not collapse these immediately into one Leap score.

A large excursion with no accessibility structure should die cheaply.

A small displacement that opens a reproducible bridge may deserve more attention.

---

## Relationship to funnel geometry

The emerging funnel work suggests a useful duality.

A **funnel** constrains or contracts the space of likely downstream trajectories:

    many plausible continuations
        ↓
    smaller coherent behavioral basin

A **Leap** attempts to increase access across an otherwise difficult boundary:

    ordinary basin
        ↓
    accessibility perturbation
        ↓
    non-dominant coherent basin

These need not be mathematical inverses.

But they may be experimentally complementary operations:

    Funnel:
        change probability mass by constraining trajectories

    Leap:
        change probability mass by opening trajectories

This creates a shared measurement vocabulary around:

- displacement;
- transition probability;
- contraction;
- accessibility;
- persistence;
- alignment;
- residual effects.

The relationship is a hypothesis worth testing, not an architectural dependency.

---

## Reinforcing alignment and Leap

The funnel work raises another possibility.

A Leap may itself be produced by several contextual interventions whose effects
are reinforcingly aligned.

For components:

    L = {L1, L2, ... Ln}

measure their independent trajectory effects.

If several components each increase accessibility toward the same candidate
region, then:

    ΔR_1 > 0
    ΔR_2 > 0
    ...
    ΔR_n > 0

and their displacement / transition effects may be mutually aligned.

The combined intervention may then be:

- redundant;
- additive;
- antagonistic;
- superadditive.

This gives an eventual autonomous Leap constructor a richer objective than
"maximize novelty."

It may search for small sets of perturbations that coherently increase access to
otherwise under-reached semantic structure.

---

## Hypothesis ladder

Experiments should distinguish progressively stronger claims.

### H0 — Ordinary sampling variation

The intervention does not produce reproducible accessibility change beyond
matched baseline variation.

### H1 — Non-dominant directional access

The intervention reproducibly increases visits to a coherent non-dominant region.

### H2 — Bridge

The intervention amplifies traversal through a route that can also be detected,
at lower frequency, under baseline conditions.

### H3 — Pinch-like accessibility deformation

The intervention changes effective transition geometry in a way not explained by
amplification of a single baseline route.

### H4 — Reinforcing accessibility intervention

Multiple independently useful Leap components produce mutually compatible
accessibility changes and their composition strengthens the effect.

### H5 — Transferable accessibility structure

The measured accessibility effect survives paraphrase, prompt-family changes,
and/or model changes sufficiently to suggest something broader than one prompt
incantation.

Failure of H(n) does not invalidate H(n-1).

Do not promote claims upward automatically.

---

## Measurement design

The first experiments should be paired and population-based.

For source context `C_i`, sample:

    baseline:
        τ_ij = T(C_i, seed_j)

    leap:
        τL_ij = T(C_i + L, seed_j)

Where practical, use matched seeds or otherwise preserve reproducible sampling
metadata.

Store the full trajectory or turn structure rather than only the final answer.

Possible sk-mcp measurements include:

    trajectory embeddings
    paired displacement
    candidate-region visitation
    transition counts
    neighborhood changes
    path-length estimates
    excursion/recoherence geometry
    dispersion
    constituent alignment

The experiment layer owns the hypothesis and sampling schedule.

sk-mcp owns measurement primitives.

Neither should infer internal neural topology from emission-space geometry.

---

## Controls

At minimum compare:

- no Leap;
- Leap;
- temperature-only increase;
- token/length-matched neutral directive;
- paraphrases of Leap;
- semantically bleached Leap;
- unrelated creativity/divergence instruction.

Where testing a proposed bridge:

- deliberately sample baseline heavily enough to search for rare natural
  traversals;
- compare intermediate regions rather than only endpoints.

Where testing pinch-like behavior:

- test whether path shortening is just target priming;
- test unrelated A/B region pairs;
- measure global geometry to detect nonspecific collapse;
- repeat under an independent embedding instrument.

---

## Wrong-axis discipline

Carry ADR-LNF-0002's re-form principle into the geometry measurement.

A Leap hypothesis that "succeeds" trivially may be measuring the wrong thing.

Examples:

    "The Leap changes the embedding."

Almost every meaningful instruction will.

Non-discriminating — re-form.

    "The Leap increases semantic diversity."

A generic high-temperature instruction may do the same.

Non-discriminating — re-form.

    "The Leap makes B appear more often after explicitly naming B."

That may measure priming rather than accessibility.

Non-discriminating — re-form.

The measurement axis must discriminate the proposed mechanism, not merely detect
that intervention occurred.

---

## Instrument circularity

Do not use the same geometric instrument to:

1. search for the candidate bridge/pinch;
2. define the region;
3. optimize the Leap;
4. certify that the Leap worked.

At least one stage must be independently specified.

Possible splits include:

- discover with one embedder, validate with another;
- discover geometrically, validate with human/direct behavioral labels;
- define candidate regions before optimization;
- hold out entire prompt families;
- use path structure for search and target-independent labels for validation.

An autonomous Leap constructor is especially vulnerable to exploiting the
measurement instrument.

---

## Autonomous Leap construction

Only after a reproducible accessibility effect exists should an optimizer be
introduced.

The loop may then be:

    propose perturbation
        ↓
    sample trajectories
        ↓
    measure accessibility
        ↓
    null / geometry gate
        ↓
    retain or reject
        ↓
    mutate / recombine
        ↓
    repeat

Candidate operations may include:

- wording changes;
- constraint addition/removal;
- contextual perspective shifts;
- analogy requests;
- counterfactual framing;
- decomposition changes;
- controlled temperature changes;
- combinations of independently effective perturbations.

The optimizer should not receive unrestricted access to holdout measurements.

The purpose is to discover accessibility interventions, not train against the
judge.

---

## Initial experiment

Start with a case where a human already experienced a plausible Leap.

Do not begin with autonomous search.

### Experiment 0A — Replay

Take an archived reasoning sequence containing:

1. a dominant framing;
2. a specific intervention or contextual shift;
3. an unexpected but coherent association.

Construct matched contexts immediately before the intervention.

Generate populations:

    baseline
    original Leap
    paraphrased Leap
    neutral control
    generic creativity control

Ask:

- Does the candidate region appear more frequently?
- Is the candidate reached through similar intermediate states?
- Does generic creativity reproduce the result?
- Does the effect survive paraphrase?
- Does it recohere into the same candidate class?

---

### Experiment 0B — Bridge search

Sample baseline heavily.

Determine whether rare baseline trajectories independently reach the same
intermediate region.

If yes, estimate whether the Leap primarily increases use of that route.

A positive result supports **bridge discovery**.

---

### Experiment 0C — Pinch discriminator

If no stable baseline route explains the result, compare transition geometry.

Ask whether Leap-conditioned trajectories show:

- reduced semantic path length;
- changed nearest-neighbor relationships;
- multiple new paths between the source and candidate regions;
- selective transition-rate increases.

A positive result permits the phrase:

> pinch-like accessibility change in measured response space

It does not permit:

> the model's internal manifold pinched

without separate internal evidence.

---

## Minimal code-layer artifacts

An experimental trajectory record should retain enough provenance to recompute
measurements:

```json
{
  "experiment_id": "...",
  "model": "...",
  "context_id": "...",
  "condition": "baseline|leap|neutral|divergence-control",
  "leap_id": "...",
  "seed": "...",
  "step": 0,
  "text_ref": "...",
  "embedding_ref": "...",
  "candidate_region": null,
  "provenance": {}
}
```
