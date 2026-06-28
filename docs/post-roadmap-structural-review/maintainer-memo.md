# Proposal: Restructure DACS for Bounded Cognition

## Executive Summary

The DACS standard is strongest where it turns trust, coordination, and audit into explicit artifacts with clear validation rules. It is weakest where it asks readers, implementers, and agents to keep too many interacting layers in their heads at once.

The cleanest structural fix is:

- make `DACS-CORE` materially smaller
- keep `DACS-1..5` as locally readable stage contracts
- move volatile or domain-specific logic into `DACS-HOOKS`
- move real-world use-case bundles into `DACS-PROFILES`
- move enumerations and operational registries into `DACS-REGISTRIES`
- move substrate reality, governance, and future work out of the normative reading path

This is not a call to weaken the standard. It is a call to reduce the amount of meaning that currently lives only in cross-references, rollout notes, and authority-specific prose.

## Problem

The current structure mixes six different things in the same reading lane:

1. protocol invariants
2. stage-local contracts
3. registry contents
4. current Demos implementation reality
5. governance/process material
6. roadmap/deferred topics

That has three costs:

- local readability drops because a reader must jump across modules to know what is actually required
- change safety drops because edits can accidentally disturb rules that live somewhere else
- implementation quality drops because humans and coding agents both lose the thread in long, cross-coupled prose

The bounded-cognition framing is simple: good engineering moves burden out of fragile attention and into structure. The current DACS document set often does the opposite.

## Target Structure

### 1. `DACS-CORE`

Only the invariants every conforming implementation must share:

- canonicalization, hashing, signatures
- shared identifiers and references
- shared artifact base types
- session/job identity
- base outcome vocabulary
- minimal state-machine contract
- substrate capability model at the trust-property level
- extension model: hooks, profiles, registries

`DACS-CORE` should answer one question only:

What bytes, references, and state transitions must two implementations agree on?

### 2. `DACS-1..5`

Each stage module should contain only:

- stage purpose
- stage-local artifact shapes
- stage-local validity rules
- stage-local phase contracts
- explicit inputs from the prior stage
- explicit outputs to the next stage

Each stage should be readable mostly on its own, with `DACS-CORE` used only for shared primitives.

### 3. `DACS-HOOKS`

This is the extension layer for pluggable, evolving, or authority-specific logic.

Examples:

- identity hooks
- vet method hooks
- negotiation pattern hooks
- settlement adapter hooks
- reputation/publication hooks

Each hook should define:

- required input shape
- required output shape
- trust assumptions
- failure semantics
- conformance status: normative, optional, or experimental

### 4. `DACS-PROFILES`

Profiles should hold real-world bundles of constraints and choices.

Examples:

- micropayment HTTP profile
- bilateral RFQ profile
- sealed procurement profile
- institutional regulated-trade profile
- cross-chain settlement profile

Profiles are where business/domain complexity belongs. They should not sit inside the protocol spine unless the rule is truly universal.

### 5. `DACS-REGISTRIES`

Registries should become separate, data-oriented artifacts:

- claim scheme registry
- vet method registry
- vet recipe registry
- negotiation pattern registry
- rail registry

These should be machine-consumable first and prose second.

### 6. Companion Documents

Move non-core material into separate docs:

- `DACS-MAPPINGS`
- `DACS-GOVERNANCE`
- `DACS-ROADMAP`
- `DACS-THREAT-MODEL`
- `DACS-CONFORMANCE`
- `DACS-GLOSSARY`

## Structural Rules

Use these as editorial rules during the rewrite:

1. If a rule is universal and stable, it belongs in `DACS-CORE`.
2. If a rule is stage-specific and load-bearing, it belongs in exactly one of `DACS-1..5`.
3. If a rule is provider-, authority-, or rail-specific, it belongs in hooks or registries.
4. If a rule is use-case-specific, it belongs in a profile.
5. If text explains current rollout reality rather than protocol validity, it does not belong in the normative path.
6. If correctness depends on reading three sections together, the structure is wrong.

## What Should Move First

Immediate extraction targets:

- Demos production mapping
- stewardship/governance material
- roadmap and deferred topics
- registry contents
- authority-specific verification behavior
- rail-by-rail operational detail
- richer reputation policy

This shrinks the mental surface area before any semantic redesign begins.

## Why This Is Better

This structure improves the standard on three fronts:

- for maintainers: fewer cross-coupled edits and a cleaner change surface
- for implementers: clearer boundaries between mandatory invariants and optional integrations
- for AI/codegen/review workflows: less context fragility and fewer hidden obligations

The goal is not to make DACS smaller by deleting important ideas. The goal is to put each idea in the narrowest place where it still makes sense.

## Recommendation

Do the rewrite in two passes:

1. separate layers without changing semantics
2. simplify after the new boundaries are in place

Trying to redesign semantics while also moving structure is the highest-risk path. The safer path is:

- first make the document set legible
- then make the design leaner

That sequencing matters.
