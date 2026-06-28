# Double-Check Audit

This note records what was checked and how confident the proposal is.

## What Was Re-checked

### 1. The bounded-cognition essay

Re-checked against:

- Matt Williams, `Engineering for Bounded Cognition`
- reviewed directly on 2026-06-28

High-confidence takeaways from the essay:

- the mind holds very few independent facts at once
- attention is narrow and failure-prone
- human error is often a system-design failure, not a character failure
- good engineering moves burden out of memory and into structure
- names, boundaries, tests, and reversibility are all ways of externalizing cognition
- the same boundedness now applies to language models and long-context code work
- systems built for a mythical operator who can hold the whole machine in their head are already broken

Those claims directly support the structural recommendations in this bundle.

### 2. The current DACS spec set

Re-checked against the current public docs reviewed on 2026-06-28:

- `CORE.md`
- `DACS-1-IDENTIFY.md`
- `DACS-2-VET.md`
- `DACS-3-NEGOTIATE.md`
- `DACS-4-SETTLE.md`
- `DACS-5-VERIFY.md`

High-confidence observations from the docs:

- `CORE` currently mixes protocol invariants with mapping/governance/roadmap/reference material
- `DACS-2` carries the heaviest provider- and authority-specific cognitive burden
- `DACS-3` and `DACS-4` contain substantial pattern and rail taxonomy that does not all need to live in the stage spine
- `DACS-5` contains a solid state-machine core plus a thicker policy layer around reputation and interpretation
- many obligations currently require multi-document reading to understand correctly

## High-Confidence Conclusions

These are the parts of the proposal I am most confident in:

1. `DACS-CORE` should be smaller.
2. `DACS-1..5` should be more locally readable.
3. registries should be separated from stage contracts.
4. Demos mapping/governance/roadmap material should leave the normative reading path.
5. most authority- or provider-specific details should move out of the main stage docs.
6. the rewrite should be done in two passes: structural extraction first, simplification second.

## Editorial Judgments

These are still strong recommendations, but they are design choices rather than protocol facts:

1. the exact naming of `DACS-HOOKS` versus another extension-doc label
2. the exact boundary between `profiles` and `hooks` for some content
3. how much reputation logic remains canonical in `DACS-5`
4. whether some shared types should live in `DACS-CORE` or in a shared annex under `DACS-4`
5. whether fixed-price negotiation stays as a minimal built-in pattern or also becomes profile-driven

None of these judgments weaken the main conclusion. They only affect the final editorial shape.

## Internal Consistency Check

The bundle is internally consistent on these points:

- `CORE` holds invariants
- stage docs hold stage contracts
- hooks hold pluggable logic
- profiles hold use-case bundles
- registries hold enumerations and machine-readable definition sets
- mappings/governance/roadmap stay outside the mandatory validity-reading path

That consistency matters more than the precise file names.

## What This Bundle Does Not Claim

It does not claim:

- that every current DACS rule is wrong
- that all pattern/rail/reputation detail should disappear
- that the protocol should become vague
- that the current maintainers should redesign semantics before separating structure

The proposal is structural first, semantic second.

## Bottom Line

After re-checking both the essay and the current DACS docs, the main recommendation still stands:

The right move is a thinner core, clearer stage contracts, and a deliberate escape of volatile detail into hooks, profiles, registries, and companion docs.
