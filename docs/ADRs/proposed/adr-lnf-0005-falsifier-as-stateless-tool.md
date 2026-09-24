# ADR-LNF-0005: The Falsifier Is a Category, Not a Peer Node — a Stateless H0-in Falsifier Tool

**Status:** ratified
**Date:** 2026-07-28 (US/Mountain)
**Author:** shanevcantwell, with Claude (orchestrator) as drafting collaborator
**Related:** ADR-LNF-0001 (amends its "three uniform recursive nodes" framing and Appendix-A Falsifier instantiation); ADR-LNF-0002 (adopts its `coefficient-correction` return and numeric-discriminator-first ordering; locates its iterative null re-formation *outside* the stateless tool); ADR-LNF-0004 (advances its "Extraction" open question — a concrete decoupling of F from the AoT fork; consistent with its Falsifier-as-read-only-dispatch instantiation); ADR-ARC-001 (supersedes its `falsify.md`-as-leaf-agent framing; F is not a leaf); ADR-LNF-0003 (the AoT scored-atom medium is the L/N-side substrate this record deliberately does *not* place F on)
**Supersedes:** —
**Superseded by:** —

---

## Context

ADR-LNF-0001 records the pipeline as *"three uniform recursive nodes and one measurement gate."* Its own conceptual foundation, in the same document, insists the Leap/Null-former and the Falsifier are *"different operations, not different amounts of one operation"* — the Falsifier is the only envelope-raiser, its contribution *"unbounded and unverifiable by a caller that never saw the world it touched,"* while L and N are pure-reasoning, bounded, and checkable. The two statements are in tension: a node type asserted to be a different *operation* cannot also be one of three *uniform* instances without flattening the distinction the rest of the document treats as load-bearing.

ADR-ARC-001 inherits the flattening one substrate down — it instantiates the Null-former and the Falsifier as sibling *leaf agents* (`null-form.md`, `falsify.md`). But a leaf, per ADR-LNF-0001, is *"a job with no interior to decompose."* A Falsifier that fans out, fetches, attacks a null against multiple exogenous sources, and synthesizes a cited result *has* interior — it is a deep-research operation, categorically not a leaf.

This record resolves the tension by promoting F to its own category and fixing its contract as a stateless tool.

## Decision

**The Falsifier is a category distinct from the Leap and Null-former, and its contract is a stateless tool that accepts a null (H0) and no generator context.**

1. **F is not a peer node.** L and N are pure-reasoning uniform nodes (envelope-approaching, bounded, checkable, leaf-shaped). F is an *asymmetrical, world-crossing, envelope-raising deep-research agent* whose interior is encapsulated behind a tool boundary. ADR-LNF-0001's "different operations, not different amounts" is promoted from prose to structure: the pipeline is **two uniform reasoning nodes plus one categorically distinct falsifier**, not three of a kind.

2. **F's contract is a stateless tool: `H0 → typed return`, no other context.** Working name `exogenous-falsifier-mcp`. It accepts a null and nothing about how that null was produced. This is `STATELESS-CORE` + `ONE-DOOR` + `PARSE-AT-THE-DOOR` stated as an interface: same H0 in → same falsification attempt, no cross-call accumulation, one contracted surface, input validated at ingress.

3. **Statelessness is the enforcement surface for generator-isolation, not a convenience.** ADR-LNF-0001 requires F to have *"zero visibility into the leap's generation"* and closes the catch-the-vibe contamination only by discipline / tool-whitelist (its enforcement-split "world boundary is real" row is prose-only on a chat substrate). A tool whose *signature accepts only an H0* closes it structurally: there is no parameter through which generator context can arrive. The guarantee moves from "the falsifier won't peek" to "the falsifier has nothing to peek through." This also forecloses faked-world-crossing from a second direction — a stateless H0-in tool has no in-context material to simulate a crossing *from*.

4. **F's return is `coefficient-correction` (per ADR-LNF-0002/0004), never a soft verdict.** The typed return is `{ kernel, direction, magnitude, coefficient, basis }` with the exogenous measurement in `basis`, ordered **cheapest numeric discriminator first**. Exactly two other typed returns: `non-discriminating — re-form` (the null resolved too trivially — an axis alarm, per ADR-LNF-0002) and a `BLOCKED` framed sub-panic (the world was unreachable). Bare "failed" is invalid (ADR-LNF-0001). The fail-loud invariant holds: **F never returns a soft yes, supporting evidence, or a trust-and-degrade result.**

5. **The iterative null re-formation loop lives outside F.** ADR-LNF-0002 makes null-formation iterative. That loop is the Null-former's / orchestrator's, not F's: F stays stateless by returning `non-discriminating — re-form` and letting the caller re-form and re-dispatch. Resource lifecycle lives outside the core (`STATELESS-CORE`).

6. **Instantiation is delegated to ARC, advancing Extraction.** The *decision* is recorded here in the LNF canon; the *build* — `exogenous-falsifier-mcp` — is pulled into `automation-reaction-chamber` (ARC) and is the first automated deliverable there. This is a concrete discharge of ADR-LNF-0004's "Extraction" open question: F is extracted from the `dioptx/mcp-atom-of-thoughts` fork into its own tool, decoupled from the AoT codebase entirely.

## Rationale

The category error was doing real damage: it invited F to be built like N — a leaf, a reasoning pass — and a reasoning-shaped Falsifier is ADR-LNF-0001's rejected Option D, which *"leaves the pipeline envelope-approaching,"* i.e. the brake silently disengages. Naming F a distinct category and fixing its contract as a stateless H0-in tool makes the envelope-raising property structural rather than aspirational.

The statelessness is the load-bearing move. Every prior LNF record leaves the "world boundary is real / zero generator visibility" guarantee on the prose side of its enforcement-split table. A single-input tool signature is the first instantiation that closes it in the type system.

### Positive Consequences
- Generator-isolation and faked-world-crossing guarantees become structural (type-enforced), not prose.
- F becomes a reusable, composable primitive: any pipeline — the LNF pipeline of 0001, the dispatch-gating of 0004 — calls the same tool with an H0.
- Concrete progress on Extraction: F leaves the AoT fork; the discipline stops being welded to upstream MIT code.
- The fail-loud return removes the soft-yes surface where confabulation laundering re-enters.

### Negative Consequences
- "No generator context" is in tension with F needing *somewhere to look*: numeric-first discriminators (0002) must count in a corpus. The H0 alone may be insufficient to locate the world — see Open Questions (keystone).
- A stateless tool re-pays any setup cost per call; nothing accumulates across a re-form loop.
- The terminal seam remains (0001): F's return is unverifiable by a caller that never saw the world. Statelessness sharpens the isolation but does not close that seam — it concentrates trust at the tool boundary.

## Alternatives Considered

### Option A: Keep F as a third uniform node / a `falsify.md` leaf (status quo, ADR-ARC-001)
**Why rejected:** Flattens the "different operations" distinction and invites the reasoning-shaped Falsifier (0001 Option D). A leaf has no interior; a deep-research falsifier does.

### Option B: F as a stateful research *agent* carrying session context
**Why rejected:** Any carried context is a channel for generator contamination and defeats the structural isolation; state also breaks reproducibility of the falsification attempt. The interior may be rich *within* a call, but must not persist *across* calls or ingest the generator's context.

### Option C: Build F inside the AoT fork alongside L
**Why rejected:** Re-welds F to upstream code it does not use (0004 already shows the dispatch instantiation uses none of it) and forfeits the Extraction opportunity. F's home is ARC.

## Open Questions

- [ ] **H0-alone vs. H0-plus-world-handle (keystone).** A stateless "H0 and no other context" tool still needs to know *where* to cross into the world (which corpus to count in, which tools to reach). Is the honest contract `H0` alone, or `H0 + a typed exogenous-source handle` provably distinct from generator context? **Resolution trigger:** the first real H0 run through the skeleton — if F cannot act without a source pointer, refine the signature to `{ h0, world_handle }` and record the type boundary that keeps `world_handle` from smuggling generator context (an `IDENTITY⊥ENVELOPE` split: the H0 is identity, the handle is envelope).
- [ ] **Is `coefficient-correction` the modal return?** Inherited from ADR-LNF-0002's central bet. **Resolution trigger:** first batch of real H0 dispatches through the tool; if kills/survivals dominate, narrow with 0002.
- [ ] **Does the re-form loop belong to the Null-former or the orchestrator?** Decision 5 places it "outside F" but does not assign it. **Resolution trigger:** wiring the tool into the LNF pipeline vs. the dispatch-gating workflow — the two substrates may answer differently.
- [ ] **Canonical name.** `exogenous-falsifier-mcp` is a working name; the canonical mint happens when ARC establishes the tool (ONE-MINT). **Resolution trigger:** ARC establishment.

## Supersession Relationships

**Supersedes:** — (amends ADR-LNF-0001's "three uniform recursive nodes" framing → two-uniform-plus-one-category; supersedes ADR-ARC-001's `falsify.md`-as-leaf framing. Back-references owed: ADR-LNF-0001 gains "Falsifier promoted to a distinct category and stateless-tool contract by ADR-LNF-0005"; ADR-ARC-001 gains "`falsify.md`-as-leaf superseded by ADR-LNF-0005 — F is a stateless tool, not a leaf agent.")
**Superseded by:** TBD — the H0-alone-vs-world-handle resolution (keystone open question) may produce a successor that fixes the final signature.

## Recursive Self-Application

This record is itself a leap whose null has not been attacked: *"F's contract can be a stateless tool that accepts an H0 and no other context."* The cheapest experiment that could embarrass it is Decision 2's own skeleton — build the stateless tool, hand it one real H0, and see whether it can cross into the world at all without a source handle. If it cannot, "no other context" is falsified on first contact and the keystone open question becomes the body of a successor. Running that before building F's interior on this contract is the externalized form of the brake the discipline is about.
