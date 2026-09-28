# ADR-LNF-0007: Accessibility Geometry and Topology — Measurement Layers, Superposition, and the Limits of the Manifold Metaphor

**Status:** proposed
**Date:** 2026-09-23 (US/Mountain)
**Author:** shanevcantwell, with model collaborator
**Related:** ADR-LNF-0001 (Leap–Null–Falsify pipeline and geometry/falsification gate separation);
ADR-LNF-0002 (wrong-axis re-formation and coefficient correction);
ADR-LNF-0003 (scored-atom conceptual medium and resistance to premature collapse);
ADR-LNF-0004 (dispatch gating and the distinction between behavioral/prose control and structural enforcement);
ADR-LNF-0005 (Falsifier as a distinct stateless world-crossing category);
ADR-LNF-0006 (Leap as accessibility perturbation; bridge/pinch hypotheses);
sk-mcp funnel/reinforcing-alignment measurement work
**Supersedes:** —
**Superseded by:** —

---

## Context

ADR-LNF-0006 refines Leap from "sample off the dominant path" toward a more
specific hypothesis:

> A useful Leap may change the accessibility of coherent non-dominant semantic
> structure.

That refinement introduces geometric vocabulary:

- regions;
- trajectories;
- bridges;
- manifolds;
- pinches;
- distance;
- neighborhood;
- contraction;
- accessibility.

Parallel work on directive funnels introduces additional vocabulary:

- displacement fields;
- reinforcingly aligned effects;
- superadditivity;
- attractor-like behavior;
- recursive gain.

And an adjacent mechanistic hypothesis introduces:

- superposition;
- correlated features;
- shared feature mixtures;
- low-dimensional structure;
- representational manifolds;
- topology.

These terms are useful only if their abstraction boundaries remain explicit.

The danger is not merely imprecise language.

A measurement made in **emission space** can easily be narrated as a fact about
**activation space**.

A local geometric observation can be narrated as a **topological** change.

A shared output direction can be narrated as a literal internal **feature**.

A prompt-conditioned accessibility change can be narrated as a neural manifold
physically "pinching."

That would recreate exactly the failure mode LNF exists to prevent:
an attractive leap becomes architecture before its null is attacked.

This ADR therefore records a clarification:

> Geometry, topology, superposition, and accessibility are related hypotheses at
> distinct measurement layers. They must not be collapsed into one ontology.

---

## Decision

Adopt an explicit **four-layer measurement ontology** for LNF geometry work.

The layers are:

1. **Feature geometry**
2. **State / trajectory geometry**
3. **Learned transition dynamics**
4. **Topology / connectivity**

Claims may move upward through these layers only with additional evidence.

The initial LNF/sk-mcp experiments remain primarily at layer 2.

Superposition is a candidate explanatory mechanism at layer 1.

Recursive funnels and accessibility dynamics occupy layer 3.

Bridge/pinch language becomes genuinely topological only when layer-4
connectivity is measured rather than inferred from distance.

The Falsifier remains outside all four layers as the exogenous truth boundary.

---

## 1. Feature geometry

Feature geometry concerns the representational ingredients available to the model.

Conceptually:

    x = Σ z_i v_i

where:

    v_i = feature-like direction or component
    z_i = context-dependent coefficient

Under superposition, more useful features may be represented than there are
independent representational dimensions.

Features therefore need not occupy mutually orthogonal directions.

Their interference may be:

- destructive;
- approximately independent;
- correlated;
- constructively aligned.

The important clarification is:

> Superposition does not require that semantic structure be represented as one
> concept per axis.

Nor does observing a behavioral direction establish the existence of one internal
feature direction.

---

### Correlated superposition

If latent features co-occur systematically, the occupied coefficient space is not
all of:

    R^m

but some constrained subset:

    Z ⊂ R^m

The representation map:

    x = Vz

therefore maps a structured subset of latent combinations into activation space.

If `Z` has lower intrinsic dimensionality than the ambient coefficient space, its
image:

    M = V(Z)

may exhibit manifold-like structure even before considering later nonlinear
transformations.

Subsequent nonlinear layers may:

- bend;
- partition;
- gate;
- fold;
- separate;
- merge locally;
- change effective dimensionality

of the occupied representation.

Therefore this ADR admits the mechanistic hypothesis:

> **Manifold-like representational geometry may emerge partly from the structured
> set of permissible mixtures of superposed features.**

This is a hypothesis about how manifold structure *could arise*.

It is not yet an LNF architectural dependency.

---

## 2. State / trajectory geometry

State geometry concerns the representations actually occupied during inference.

Even if a model has many available features, actual prompts and contexts occupy
only a constrained subset of the possible combinations.

A generated reasoning process may therefore be represented observationally as a
trajectory:

    x_0 → x_1 → x_2 → ... → x_n

At the emission layer, sk-mcp approximates these states with external embeddings
of generated text or structured trajectory artifacts.

This is not the transformer's residual stream.

It is a behavioral measurement surface.

Questions at this layer include:

- How far did an intervention move the population?
- Which neighborhoods became more frequently occupied?
- Did trajectories converge?
- Did they diverge?
- Did an otherwise rare semantic region become reachable?
- Did multiple interventions produce aligned displacement?
- Did apparent path length change?

ADR-LNF-0006 primarily belongs here.

So do the first funnel experiments.

---

## 3. Learned transition dynamics

Static geometry is insufficient to describe inference.

The model also implements learned transition tendencies:

    x_t → x_(t+1)

These transitions are conditioned by:

- current representation;
- context;
- attention;
- decoding;
- learned weights;
- prior generated output.

The relevant object is therefore not merely a set of points but an effective
transition field:

    P(x_(t+1) | x_t, C)

or some empirical approximation of it.

This layer contains:

- accessibility;
- persistence;
- attractor-like behavior;
- recursive reinforcement;
- transition gain;
- basin stability;
- path preference.

A funnel that recursively reinforces its own effect is a dynamical claim.

A Leap that makes a previously rare transition common is also a dynamical claim.

Neither is fully described by endpoint cosine.

---

### Recursive reinforcement

For a measured behavioral mode `v`:

    d_(t+1) ≈ A d_t

If:

    A v ≈ λv

then:

    0 < λ < 1
        decaying persistence

    λ ≈ 1
        stable persistence

    λ > 1
        reinforcing mode

    λ < 0
        compensatory / oscillatory behavior

    A v off-axis
        drift

This remains an emission-space dynamical approximation until independently
matched to internal model state.

---

## 4. Topology / connectivity

Geometry asks questions such as:

- how far apart?
- at what angle?
- along what curvature?
- how concentrated?
- what direction?

Topology asks a different class of question:

> **What is connected to what at all?**

Relevant objects include:

- connected components;
- bridges;
- loops;
- holes;
- persistent connectivity across scale;
- structures that survive deformation.

This distinction is load-bearing for the word **pinch**.

If an intervention merely reduces measured distance between regions A and B:

    distance(A, B) decreases

that is a geometric effect.

If it changes whether trajectories can move between A and B through the
accessible state space:

    connected(A, B): false → true

or materially changes the persistence of that connection across measurement
scales, then a topological description becomes more appropriate.

Therefore:

> **"Pinch" must not be promoted from metaphor to mechanism solely because two
> regions move closer in an embedding.**

---

## Bridge, pinch, and superposition

The new vocabulary is clarified as follows.

### Bridge

A **bridge** is an empirically observed low-probability transition structure
connecting two otherwise weakly connected behavioral regions.

Conceptually:

    A → R → B

where `R` is an intermediate region or family of trajectories.

A Leap may increase occupancy of `R`.

If rare baseline trajectories already use substantially the same route, the
result supports **bridge amplification**.

---

### Pinch-like accessibility change

A **pinch-like accessibility change** is an intervention-conditioned change in
effective transition structure such that previously difficult cross-region
movement becomes substantially easier and cannot be explained merely by increased
sampling of one pre-existing route.

Possible signatures:

- shorter effective paths;
- multiple new transition routes;
- altered neighborhood adjacency;
- increased cross-region visitation;
- changed persistent connectivity.

At the emission layer the permitted phrase is:

> pinch-like accessibility change

not:

> the neural manifold pinched

---

### Shared-superposition bridge

A third hypothesis connects feature geometry to accessibility.

Suppose two semantic regimes use different feature bundles but share some
superposed components:

    A = {a1, a2, s1, s2}
    B = {b1, b2, s1, s2}

Ordinary contexts may emphasize:

    A → a-components

or:

    B → b-components

making the regimes behaviorally distant.

A contextual intervention may selectively increase the contribution of:

    s1, s2

making transitions between A and B easier.

The resulting behavior could resemble a bridge or pinch without requiring a
literal deformation of a fixed manifold.

This yields the candidate mechanism:

> **Apparent accessibility changes may arise when context increases activation of
> superposed structure shared by otherwise weakly connected semantic regimes.**

This is a mechanistic hypothesis.

It must not be inferred solely from emission-space similarity.

---

## Manifolds are not an alternative to feature directions

Do not frame:

    feature direction
        versus
    manifold

as mutually exclusive representational theories.

A useful provisional model is:

    latent factors
        ↓
    feature coefficients
        ↓
    superposition / shared dimensions
        ↓
    constrained combinations
        ↓
    occupied representational geometry
        ↓
    nonlinear transformation
        ↓
    manifold / stratified / polytope-like structure
        ↓
    learned transition dynamics

Under this view:

- directions can be local ingredients;
- superposition determines how ingredients share capacity;
- correlations constrain which mixtures occur;
- occupied mixtures trace structured subsets;
- nonlinear transformations reshape those subsets;
- trajectories move through them;
- topology describes their connectivity.

The representation need not be globally manifold-like.

It may instead be:

- piecewise linear;
- stratified;
- polyhedral;
- branching;
- locally manifold-like;
- different-dimensional in different regions.

"Manifold" is therefore shorthand pending measurement, not a guaranteed global
ontology.

---

## Funnel and Leap relationship

Funnels and Leaps operate on the same provisional accessibility substrate but
serve different purposes.

### Funnel

A funnel restricts or reinforces a family of downstream trajectories.

Conceptually:

    broad reachable set
        ↓
    smaller / more strongly weighted behavioral region

Candidate measurements:

- contraction;
- target-direction efficacy;
- reinforcing constituent alignment;
- persistence;
- recursive gain.

### Leap

A Leap increases access to a coherent region that ordinary inference
under-reaches.

Conceptually:

    dominant reachable region
        ↓
    accessibility perturbation
        ↓
    coherent non-dominant region

Candidate measurements:

- region visitation;
- transition probability;
- bridge occupancy;
- path structure;
- connectivity change.

These are not strict mathematical inverses.

A funnel may itself create access to a region by suppressing competing
trajectories.

A Leap may use a carefully chosen constraint — effectively a local funnel — to
reach a non-dominant region.

Therefore the experimentally useful distinction is functional:

    Funnel:
        selectively reduces / reinforces downstream possibility

    Leap:
        selectively increases access to under-reached candidate structure

---

## Relationship to ADR-LNF-0003

ADR-LNF-0003 addresses a complementary problem:

> How can conceptual material remain explicitly open without the model
> prematurely collapsing it into a high-probability occupant?

Its seal/open state belongs to the **interaction medium**, not directly to the
geometry.

But there is a plausible relationship:

    open axis
        may preserve multiple reachable continuations

    sealed axis
        may deliberately reduce reachable continuations

This resembles accessibility control.

That resemblance does not establish that seal-state literally changes manifold
geometry.

However, future experiments may ask whether mixed-register presentation produces
measurable changes in:

- trajectory entropy;
- neighborhood occupancy;
- contraction;
- cross-region accessibility.

This is a new cross-reference, not an amendment to ADR-LNF-0003.

---

## Relationship to ADR-LNF-0004

ADR-LNF-0004 demonstrates that LNF's brake must not depend on the model remembering
prose.

It replaces the unvalidated geometry gate with a structural **stakes router** in
a substrate where geometry is unavailable.

Therefore:

> **Behavioral geometry is a measurement and routing aid, never a substitute for
> structural enforcement.**

A highly effective funnel remains a contextual behavioral constraint.

It is not equivalent to:

- capability isolation;
- permission boundaries;
- typed graph edges;
- tool restrictions;
- mandatory dispatch gates.

Likewise, a measured Leap does not create a trusted workflow transition.

0004's structural lesson remains intact regardless of how powerful the geometric
effects become.

---

## Relationship to ADR-LNF-0005

ADR-LNF-0005 makes the Falsifier categorically distinct from the reasoning side of
LNF.

This boundary becomes even more important under autonomous geometry optimization.

A synthesized Leap or funnel may be selected through thousands of iterations
against sk-mcp measurements.

That optimization history is highly contaminating context for truth evaluation.

Therefore:

> **The accessibility / geometry program terminates before the Falsifier
> boundary.**

The Falsifier must not receive:

- displacement scores;
- Gram matrices;
- topology scores;
- optimizer history;
- the bridge/pinch narrative;
- reasons the candidate looks geometrically compelling;
- search fitness;
- candidate-generation traces.

It receives only:

    H0

plus whatever typed exogenous-source handle ADR-LNF-0005 ultimately permits.

This makes the 0005 stateless boundary function as an anti-overfitting barrier:

    optimized internal evidence
        ⟂
    external falsification

The geometry may determine which candidate is worth spending falsification cost
on.

It must not influence how the world is asked to judge that candidate.

---

## Geometry gate clarification

ADR-LNF-0006 must not be read as changing the epistemic role of the geometry gate.

The gate still:

    routes spend

and does not:

    govern belief

What changes is the set of candidate measurements available to it.

Earlier candidate signal:

    excursion → recoherence

New candidate signals may include:

    accessibility gain
    transition selectivity
    bridge occupancy
    path consistency
    constituent alignment
    persistent connectivity
    topology-derived bridge structure

These remain routing evidence.

None certify truth.

---

## Measurement ladder

The following claim ladder is adopted for new LNF geometry work.

### M0 — Output difference

The intervention changed generated text.

Almost non-discriminating.

### M1 — Reproducible emission-space displacement

Matched populations show stable directional or distributional change.

### M2 — Structured trajectory change

The intervention changes visitation, transition, path, or convergence behavior.

### M3 — Accessibility change

A coherent region becomes selectively more or less reachable.

### M4 — Connectivity / topological change

The effective accessible-state structure shows a reproducible connectivity change
under an appropriate topology-sensitive instrument.

### M5 — Internal representational correlate

Independent activation-space measurement identifies corresponding internal
structure.

### M6 — Mechanistic explanation

Intervention on the proposed internal mechanism changes the behavioral phenomenon
as predicted.

Claims may stop at any level.

A result at M3 must not be narrated as M5.

A result at M5 is still not M6.

---

## Superposition hypothesis ladder

Similarly:

### S0 — No special shared structure

A/B accessibility changes are explainable by ordinary prompt effects.

### S1 — Shared behavioral region

An intermediate response-space region is associated with both A and B.

### S2 — Shared internal features

Independent mechanistic measurement identifies features/components active in both
regimes.

### S3 — Context-sensitive shared-feature amplification

The Leap/funnel intervention increases those shared components.

### S4 — Causal role

Direct intervention on the shared components alters A↔B accessibility in the
predicted direction.

Only S4 supports a strong claim that shared superposition is part of the
mechanism.

---

## Topological measurement program

If ADR-LNF-0006's accessibility effects survive basic tests, add a topology branch
rather than extending cosine indefinitely.

Candidate techniques include:

- k-nearest-neighbor graph connectivity;
- graph geodesic distance;
- connected-component stability;
- persistent homology;
- zigzag persistence across ordered states/layers/turns;
- bridge / bottleneck detection;
- mapper-like coarse topology.

The first requirement is not sophisticated topology.

It is to stop treating Euclidean proximity as equivalent to connectivity.

A minimal first experiment may be:

1. construct matched trajectory populations;
2. embed states using a registered instrument;
3. form neighborhood graphs under several defensible scales;
4. measure whether A/B connectivity differs between baseline and Leap conditions;
5. test persistence of that difference across scale;
6. repeat under an independent embedding instrument.

If the "connection" exists only at one arbitrary neighborhood radius, it is weak
evidence.

If it persists across scales and instruments, topology language becomes more
defensible.

---

## Metric discipline

All geometry depends on a metric.

Cosine similarity in an embedding space is not self-authenticating.

Therefore every load-bearing geometric claim must specify:

- embedding instrument;
- centering;
- normalization;
- whitening, if any;
- distance / similarity function;
- neighborhood construction;
- empirical null;
- sensitivity to alternate valid metrics.

A result that disappears under reasonable metric choices is:

    metric-dependent

not:

    false

and not:

    established.

The disagreement is itself a measurement result.

---

## Autonomous construction

Autonomous synthesis of funnels or Leaps may eventually search this space.

But the optimizer must not receive one scalar objective encoding the entire
ontology.

Retain separate quantities for:

- target displacement;
- accessibility;
- alignment;
- collateral displacement;
- contraction;
- path structure;
- connectivity;
- robustness;
- holdout transfer.

Topology should not simply become another weighted term in a master score.

A search system that optimizes one scalar will eventually discover the scalar.

The research target is the phenomenon.

---

## New failure modes

### Manifold reification

Treating a useful geometric metaphor as a literal persistent neural object.

**Guard:** always name the measurement layer.

---

### Distance-connectivity collapse

Assuming closer points are therefore more connected.

**Guard:** use explicit transition/connectivity measurements.

---

### Emission-to-activation laundering

Treating external embedding geometry as evidence of internal residual-space
geometry.

**Guard:** M0–M6 claim ladder.

---

### Superposition story completion

Observing a shared behavioral direction and narrating shared internal features.

**Guard:** S0–S4 ladder.

---

### Geometry-as-truth

Allowing elegant accessibility/topology to promote a candidate epistemically.

**Guard:** ADR-LNF-0001 and ADR-LNF-0005 boundary.

---

### Prompt-control / structural-control conflation

Treating a strong funnel as equivalent to a hard workflow boundary.

**Guard:** ADR-LNF-0004.

---

### Topology theater

Applying persistent homology or other sophisticated methods because the vocabulary
is attractive rather than because the simpler connectivity null failed.

**Guard:** cheapest discriminator first, inherited from ADR-LNF-0002.

---

## Initial cross-repository experiment sequence

The new work should proceed in increasing order of claim strength.

### Experiment A — Emission accessibility

Use ADR-LNF-0006 Experiment 0A/0B.

Establish whether a candidate Leap reproducibly changes access to a predefined
semantic region.

Stop if not.

---

### Experiment B — Connectivity

Construct local neighborhood graphs over trajectories.

Test whether the intervention changes A↔B connectivity robustly across reasonable
scales.

Stop topology claims if not.

---

### Experiment C — Funnel / Leap interaction

Apply a known funnel before a known Leap.

Measure whether the funnel:

- suppresses the Leap;
- strengthens it;
- redirects it;
- selectively removes competing routes.

Then reverse ordering.

This tests whether the two operations actually interact through a shared
accessibility substrate.

---

### Experiment D — Superposition correlate

Only after a stable external effect exists, move to a model where internal
activations or SAE features are accessible.

Search for feature populations jointly associated with both sides of the measured
bridge.

Do not derive the behavioral regions from those same features.

---

### Experiment E — Causal intervention

Intervene on candidate shared internal features.

Measure whether the externally established accessibility effect changes as
predicted.

This is the first experiment capable of promoting the superposition explanation
from correlation toward mechanism.

---

## Architectural summary

The LNF family now separates into the following concerns:

    ADR-LNF-0001
        epistemic pipeline
        Leap → Null → geometry gate → world-crossing falsification

    ADR-LNF-0002
        wrong-axis correction
        iterative nulls
        coefficient correction
        cheapest discriminator first

    ADR-LNF-0003
        conceptual medium
        preserve open regions without premature closure

    ADR-LNF-0004
        operational enforcement
        structural dispatch gating beats prose discipline

    ADR-LNF-0005
        exogenous truth boundary
        Falsifier is a distinct stateless category

    ADR-LNF-0006
        Leap generation semantics
        accessibility perturbation
        bridge / pinch hypotheses

    ADR-LNF-0007
        measurement ontology
        geometry vs topology
        superposition hypothesis
        cross-layer claim discipline

The records are complementary.

0007 does not promote the new geometric hypotheses.

It constrains how they may be interpreted.

---

## Positive consequences

- Prevents several new attractive metaphors from silently becoming mechanisms.
- Gives sk-mcp experiments an explicit claim ladder.
- Makes topology a distinct measurement program rather than a synonym for
  geometry.
- Provides a principled place for superposition in the LNF research program.
- Clarifies the relation among funnels, Leaps, manifolds, and attractors.
- Preserves 0004's structural-enforcement distinction.
- Strengthens 0005's generator-isolation boundary under autonomous optimization.
- Gives future activation-space work a clear promotion path from correlation to
  mechanism.
- Creates explicit stopping points where an interesting weaker result can survive
  a stronger failed hypothesis.

---

## Negative consequences

- Adds terminology and experimental layers before the basic 0006 phenomenon has
  been demonstrated.
- Some distinctions may prove empirically impossible to resolve at the emission
  layer.
- Topological instruments add substantial analysis complexity.
- The four-layer ontology may itself be too clean for actual transformer
  representations.
- "Superposition," "manifold," and "topology" each have existing technical
  meanings that constrain how casually they may be used.
- Cross-instrument replication increases experimental cost.
- The claim ladders make promotion deliberately slow.

---

## Alternatives Considered

### Fold all of this into ADR-LNF-0006

Rejected.

0006 should remain focused on the Leap contract and its bridge/pinch experiments.
Mixing representational ontology, topology, superposition, funnel relations, and
cross-ADR constraints into it would turn a falsifiable Leap refinement into a
general theory document.

### Treat manifold as the canonical representation ontology

Rejected.

The actual structure may be manifold-like only locally, or may be stratified,
polyhedral, branching, or otherwise non-manifold.

### Treat superposition as the explanation for pinch-like behavior

Rejected.

It is a plausible mechanism that requires independent internal evidence.

### Keep using cosine/distance until something obviously fails

Rejected.

Distance and connectivity answer different questions; waiting for failure would
make the instrument decide the ontology implicitly.

### Move topology directly into the geometry gate

Rejected for now.

Topology measurement is experimental and more expensive. It should earn its place
by discriminating cases that simpler accessibility measurements cannot.

---

## Open Questions

- [ ] **Is the four-layer ontology sufficient?**
  **Resolution:** use it on the first 0006 experiments; record phenomena that do
  not fit cleanly rather than expanding the taxonomy preemptively.

- [ ] **Can connectivity be robustly estimated from emission embeddings?**
  **Resolution:** compare neighborhood/persistence results across embeddings,
  scales, and direct labels.

- [ ] **Does persistent homology add discriminating value over graph connectivity?**
  **Resolution:** only adopt it after a simpler graph analysis leaves a live
  ambiguity it can resolve.

- [ ] **Are manifold-like descriptions locally stable across model layers?**
  **Resolution:** deferred to an internal-activation experiment on an accessible
  model.

- [ ] **Can shared-superposition structure be detected independently of the
  behavioral experiment?**
  **Resolution:** use SAE/activation tooling only after external regions are
  frozen.

- [ ] **Do funnels and Leaps actually share one accessibility substrate?**
  **Resolution:** Experiment C; interaction must be measured, not assumed from
  complementary vocabulary.

- [ ] **Does seal/open register from ADR-LNF-0003 measurably affect accessibility?**
  **Resolution:** after the 0003 hand-authored mixed-register experiment exists,
  reuse its conditions in sk-mcp.

- [ ] **What becomes the stable sk-mcp primitive?**
  **Resolution:** do not decide before experiments A/B expose whether the useful
  object is displacement, transition, connectivity, persistence, or something
  else.

---

## Supersession Relationships

**Supersedes:** —

**Proposes clarification to:**
- ADR-LNF-0001 geometry gate: measurement routes spend, never truth.
- ADR-LNF-0003: seal/open state may be tested geometrically but is not defined by
  geometry.
- ADR-LNF-0004: contextual behavioral control remains weaker than structural
  workflow enforcement.
- ADR-LNF-0005: geometric optimization history terminates before the Falsifier
  interface.
- ADR-LNF-0006: bridge/pinch language is restricted to the measurement layer
  actually demonstrated.

**Superseded by:** TBD.

Back-references should be added when these ADRs are next edited rather than
silently rewriting their original decisions.

---

## Recursive Self-Application

This ADR is especially vulnerable to the failure it names.

A sequence of nearby literatures — superposition, representation manifolds,
dynamical systems, persistent homology, steering geometry — can produce a highly
coherent explanatory picture merely because their vocabulary composes well.

That coherence is not evidence that the combined ontology is correct.

The cheapest experiment that could embarrass the central synthesis is:

> Establish one reproducible ADR-LNF-0006 accessibility effect, then test whether
> its apparent bridge/pinch structure survives a change of embedding instrument,
> metric, neighborhood scale, and direct behavioral labeling.

If it does not, most of this ADR remains useful only as a catalog of possible
instrument failure.

If accessibility survives but topology does not, retain geometry and discard
topological language.

If external topology survives but no shared internal feature structure appears,
discard the superposition mechanism.

If shared features appear but intervention on them does not alter accessibility,
retain correlation and discard causality.

The architecture should become *less* ornate as its attractive hypotheses die.
