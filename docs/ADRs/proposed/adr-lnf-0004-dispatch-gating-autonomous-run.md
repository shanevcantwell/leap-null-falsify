# ADR-LNF-0004: Dispatch-Gating — LNF Applied to an Orchestrator's Forward Pass (a substrate-independent instantiation, with a magnitude-miscalibration field case)

**Status:** proposed
**Date:** 2026-06-26 (US/Mountain)
**Author:** shanevcantwell, with Claude (orchestrator) as drafting collaborator
**Related:** ADR-LNF-0001 (the pipeline this instantiates); ADR-LNF-0002 (coefficient-correction return and the magnitude-over-fabrication finding, used directly here); ADR-LNF-0003 (scored-atom medium — the substrate this application deliberately does *not* require)
**Supersedes:** —
**Superseded by:** —

> **Provenance note (2026-06-26):** This repo is a fork of `dioptx/mcp-atom-of-thoughts` (MIT, © 2025 dioptx); the LNF discipline (ADRs 0001–0004) is the only divergence from upstream. This ADR uses **none** of the upstream Atom-of-Thoughts code — only the LNF discipline's prose. That is itself the claim it records: LNF is portable off the atom substrate it was sketched against.

---

## Context

ADR-LNF-0001 derived the pipeline against a concrete substrate (the Atom-of-Thoughts decomposer as Leap node; a directional-projection measurement as geometry gate; a research node as Falsifier) and asserted — but did not yet demonstrate — that the discipline is portable: "any tools that fill the roles and honor the rules qualify." A claim of portability is unfalsified until a *second, structurally different* substrate runs the same discipline. This ADR records that second instantiation.

The second substrate is an **orchestrator clearing a triaged bug backlog** (the `shanes-autonomous-run` operating skill). There are no atoms, no embedding measurement, no MCP reasoning server. The "candidate insight" is the orchestrator's own confident forward pass — a framing, a plan, a dispatch decision, a "done" declaration. The world-crossing Falsifier is a dispatched **read-only subagent** (an Explore fan-out, the git/`gh` lane, or a runtime verifier). The dashboard, the run-ledger, and the git worktrees are the medium. If LNF holds here, it holds because it is the discipline ADR-0001 claimed and not a feature of the atom-store.

The application is not hypothetical. It surfaced because the orchestrator's forward pass failed in a specific, repeated way during a live session, and the discipline is the named fix.

## The field case (a live attack on ADR-0002's null)

ADR-LNF-0002 records that the dominant observed failure is not fabrication but **miscalibrated magnitude on a sound kernel** — "direction right, magnitude wrong." A single session, 2026-06-26, clearing llauncher bugs, produced three consecutive instances of exactly that, each corrected by a *cheap exogenous discriminator*:

1. **"The two PRs don't conflict."** Asserted from a remembered file-set (forward pass). Kernel sound (they were in fact disjoint); magnitude wrong (asserted with more confidence than the evidence licensed). Corrected by a **git file-set intersection** — a count, not a reading.
2. **"This baseline fix is an operator decision."** A pre-existing red test (#206), verified diagnosis, one-line mechanical fix, nil blast radius — surfaced to the operator as if it needed ratification. Kernel sound (real defect); magnitude wrong (inflated an *instance* into a *decision*). Corrected by a **reframe** — instance-vs-policy — needing no new facts, only the cold null.
3. **"LNF is a working system."** Relayed an Explore synthesis that let the upstream atom-store's maturity read as LNF's. Kernel sound (the repo does hold a working substrate + LNF design); magnitude wrong (the working part is dioptx's; the LNF part is one commit of prose). Corrected by a **`git remote -v` + one-line `git log`** — provenance, the cheapest discriminator there is.

Three for three: sound kernel, inflated magnitude, corrected by numeric/provenance/reframe — never by more reasoning. This is corroboration of ADR-0002's central claim from an independent substrate, and it is also the motivating failure for this ADR: **the orchestrator held the LNF discipline in prose the entire session and still missed all three in the forward pass.** That is ADR-0001's enforcement-split made concrete — prose "holds by the model remembering to," and it didn't.

*Recursive self-application (see also the closing section):* n = 1, the session was looking for the pattern, and three confirmations of a hypothesis you are hunting is the yield level ADR-0001 names as the alarm, not the goal. This case **motivates**; it does not **certify**.

## Decision

Adopt LNF as the **dispatch-gating discipline** for consequential orchestrator commitments in the autonomous-run workflow, instantiated as follows.

**1. Node mapping.**

| LNF node | Dispatch-gating instantiation |
|----------|-------------------------------|
| **Leap** (warm) | The orchestrator's forward-pass framing / plan / judgment / "done." Produced confidently; never self-audited in the same pass. |
| **Null-former** (cold) | A cold restatement of the commitment's *load-bearing assumption* as a sharp, falsifiable null ("¬: these branches share no file"; "¬: this is an instance, not a policy decision"). Deliberate, separate from the leap. |
| **Falsifier** (world-crossing) | A dispatched **read-only** subagent handed the *null* — Explore for codebase/framing assumptions, the git/`gh` lane for VCS-state assumptions, a verifier for "does it actually run." It attempts to *kill* the null and returns a framed sub-panic, not a verdict. |

**2. The null is the dispatch contract (inherited, rule 2 of 0001).** The Falsifier subagent is never told "confirm X." It is handed "¬X — try to break it; report what would have broken it and whether you looked." A confirmation-shaped dispatch to a world-crosser is the laundry, here as there.

**3. Enforcement is graph topology, not prose.** The cold null-former and the real Falsifier dispatch are **workflow phase-edges** in the autonomous-run pipeline, not instructions in a skill markdown. The field case is the evidence for why: the prose form failed three times in one session. Per ADR-0001's enforcement split, only the substrate that forbids the leap→commit edge directly actually binds.

**4. Geometry gate → stakes router (explicit substitution).** The embedding-geometry measurement of ADR-0001 is unvalidated and absent on this substrate. It is replaced by a **stakes router**: only *consequential, hard-to-reverse, assumption-dense* commitments earn the Falsifier's cost (the fan-out framing, the fix approach, the self-handle/surface call, the "done" claim). Trivial mechanical steps pass ungated. This is a heuristic spend-router, marked as such — it routes spend, it does not certify belief, exactly the geometry/falsification distinction of 0001 rule 3.

**5. Falsifier return is coefficient-correction (inherited, ADR-0002).** The return separates direction from magnitude: `{ kernel: sound|unsound, direction: <verdict>, magnitude: <correction>, basis: <the exogenous measurement> }`. The session's failures were all `kernel: sound, magnitude: wrong`; a pass/fail return would have hidden exactly the signal that mattered. **Numeric/provenance discriminators are ordered first** (counts, intersections, `git remote`, date-spans) before any semantic retrieval — cheaper and harder to confabulate.

**6. Composition with the self-handle gate.** The skill's existing self-handle gate consumes the Falsifier's return: null *attacked and survived* + contained blast radius → self-handle (fix, record durably, report); null *killed*, or `kernel: unsound`, or large magnitude, or a *first-of-class policy* → surface to the operator. The two gates are the geometry/falsification pair re-expressed: stakes routes *what to verify*; falsification governs *what to act on unsupervised*.

## Consequences

**Positive.** The brake becomes structural at the orchestration layer — the resistance does not decay as the orchestrator's forward pass gets more fluent, because the cold null and the real dispatch are edges, not vigilance. The coefficient-correction return makes the *actual* failure class (magnitude) visible instead of laundering it through a pass/fail. Numeric-first keeps the gate cheap.

**Negative.** A mandatory cold-null + real read-only dispatch on every *gated* commitment is overhead, justified only by the stakes router keeping the gated set small. Over-gating (falsifying trivial steps) stalls delivery — the router's calibration is load-bearing and unvalidated. And the Falsifier's contribution is unverifiable by the orchestrator that never saw the world the subagent touched: the trust concentrates at that one seam, as in 0001.

## Failure modes specific to this application

- **Simulated falsification (the costume node).** The orchestrator "reconsiders" in-context — a second forward pass wearing a Falsifier costume — instead of dispatching a real read-only agent. This is ADR-0001's faked-world-crossing, and it is the live risk here precisely because the orchestrator *can* fake it cheaply. Closed only by the dispatch being real: an actual Explore/git/verifier call, with output the orchestrator did not generate.
- **Magnitude-blindness.** Collapsing the coefficient-correction back to pass/fail and re-hiding the dominant failure mode.
- **Over-gating / under-gating.** The stakes router admitting trivia (stall) or missing a consequential commitment (the leap ships ungated).
- **Instance/policy conflation.** Surfacing an *instance* to the operator when only the *policy* class was ever theirs — the #206 failure. The null-former question "is this an instance or a decision?" is the specific guard.

## Enforcement Split (this substrate)

| Rule | Structurally enforceable (workflow phase-edges) | Prose-only (the skill markdown) |
|------|---|---|
| Cold null before any dispatch | Pipeline edge: no leap→commit; a null-forming stage gates it | The skill asking the orchestrator to "interrogate assumptions" |
| Null-as-contract | The Falsifier subagent's prompt is a null with no confirm path | An instruction the dispatcher must remember to phrase as attack |
| World boundary is real | The Falsifier is an actual read-only subagent dispatch | "Consider checking" — fakeable as in-context reconsideration |
| Stakes routing | Workflow decides which transitions gate | Operator/dispatcher judgment |
| Coefficient-correction return | StructuredOutput schema enforces the shape | Convention |

The autonomous-run workflow is the structural column; the `shanes-autonomous-run` skill markdown is the prose column. This ADR's recommendation is to push every row left — into the workflow — wherever the session showed the prose form failing.

## Alternatives Considered

- **Keep LNF prose-only in the skill (no workflow edges).** Rejected: the field case is three failures of exactly this form in one session. Prose "holds by remembering to," and it didn't.
- **Reuse the AoT atom-store as the substrate here.** Rejected: the dispatch application has no atoms; importing the MCP server would be incidental coupling to upstream code this discipline does not need. The point of this ADR is that LNF runs *without* it.
- **A single fused gate (verify-before-acting, no stakes router).** Rejected for ADR-0001 rule 3's reason: routing spend and governing belief are different jobs; fusing them either gates everything (stall) or trusts a geometrically clean over-confident leap.

## Open Questions

- [ ] **Stakes-router calibration — the load-bearing unvalidated dependency here.** What threshold of "consequential / hard-to-reverse / assumption-dense" admits the right commitments without gating trivia? Unmeasured. **Resolution trigger:** run the autonomous-run gate on a real batch and record, per gated commitment, whether the Falsifier *changed the decision* or rubber-stamped it. A Falsifier that never changes a decision is either a costume node or an over-gate.
- [ ] **Does the Falsifier earn its cost?** The cheapest embarrassing experiment: measure decision-change rate. If near zero, this ADR is a frame that built a ritual.
- [ ] **Extraction.** LNF's discipline is currently welded to the dioptx fork. The dispatch application proves it is substrate-independent; whether to extract LNF into its own canon (decoupled from the AoT codebase) is deferred, not decided here. This ADR's existence is the argument *for* extraction; the decision is the operator's.
- [ ] **Upstream relationship.** No upstream code is used by this application; if LNF stays in the fork, the AoT substrate (ADR-0003) and the dispatch application (this ADR) are two consumers of one discipline living beside unrelated MIT code. Tolerable, but worth naming.

## Recursive Self-Application

This ADR is a leap: its null is "LNF is substrate-independent," and that null has been attacked by exactly **one** new substrate, which failed to falsify it — weak survival, n = 1, by an author motivated to confirm. The clean-looking three-for-three field case is the yield level ADR-0001 flags as suspicious. The disconfirming experiment the document owes itself is the decision-change-rate measurement above: a gate whose Falsifier never overturns a leap has not validated LNF on this substrate — it has dressed the forward pass in a second costume. Running that measurement before building the full workflow on this ADR is the externalized form of the brake the discipline is about.
