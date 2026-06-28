# Migration Plan

## Goal

Restructure the DACS docs with minimal rewrite risk, then simplify once the boundaries are clean.

## Guiding Rule

Do not redesign semantics while moving paragraphs.

First separate layers. Then simplify.

## Pass 1: Structural Extraction

The first pass should preserve meaning as much as possible.

### Step 1. Freeze the Baseline

- identify the exact source snapshot being restructured
- freeze section numbering or publish a crosswalk policy
- avoid simultaneous semantic edits

### Step 2. Tag Every Existing Section

For each section, assign exactly one primary tag:

- `core invariant`
- `stage-local`
- `hook`
- `registry`
- `profile`
- `mapping`
- `governance`
- `roadmap`
- `reference`

This tagging exercise is the real boundary-setting step.

### Step 3. Extract Companion Material First

Move out of the normative path:

- Demos production mapping
- governance/stewardship
- versioning commentary that is process-heavy rather than validity-heavy
- deferred topics and roadmap material
- glossary and conformance support material

This produces an immediate readability improvement without changing the protocol itself.

### Step 4. Extract Registries

Move registry contents into separate docs:

- claim schemes
- vet methods
- recipes
- negotiation patterns
- rails

Do not simplify registry semantics yet. Just separate them from the stage contracts.

### Step 5. Rewrite `DACS-CORE`

Reduce `DACS-CORE` to shared invariants only:

- shared canonicalization/signature rules
- shared references and identity rules
- shared artifact primitives
- base outcomes
- minimal state-machine contract
- capability model

Anything not needed by every implementation should leave `DACS-CORE`.

### Step 6. Rewrite `DACS-1..5` for Local Readability

Each stage document should become locally readable:

- pull in any hidden stage-local obligations that currently live elsewhere
- reduce forward/backward jumping
- make input/output boundaries explicit

At the end of Pass 1, the structure should be cleaner even if the design is not yet simpler.

### Step 7. Publish an Old-to-New Crosswalk

For every old section:

- where it moved
- whether it stayed intact
- whether it was split
- whether it was demoted to registry/profile/roadmap

This prevents “the rewrite lost X” arguments.

## Pass 2: Simplification

Once the boundaries are clean, simplify.

### Step 8. Replace Prose Memory with Artifacts

Wherever possible, turn obligations into:

- schemas
- decision tables
- conformance fixtures
- generated matrices

If a rule matters, it should not live only as prose.

### Step 9. Push Volatility into Hooks

Move provider- or authority-specific behavior into hooks:

- parser quirks
- retry tuning
- endpoint behavior
- provider trust assumptions
- rail-specific operational logic

This keeps the main stage docs stable while hooks evolve.

### Step 10. Push Use-Case Bundles into Profiles

Move real-world bundles into profiles:

- regulated finance
- procurement
- micropayments
- cross-chain flows

This prevents stage modules from becoming taxonomies of market behavior.

### Step 11. Shrink `DACS-5`

Keep:

- bundle shape
- state machine
- reconciliation rules
- minimal canonical summary

Move:

- richer reputation policy
- publication strategies
- optional scoring systems

to hooks or profiles unless they are truly universal.

### Step 12. Regenerate Conformance Artifacts

After simplification:

- regenerate fixtures
- regenerate cross-reference tables
- re-run conformance against the new structure

## Suggested Execution Order

1. movement map and boundary decisions
2. companion-doc extraction
3. registry extraction
4. `DACS-CORE` rewrite
5. `DACS-1..5` readability rewrite
6. hook contract definition
7. profile extraction
8. simplification pass
9. conformance regeneration
10. publication of old-to-new crosswalk

## Risk Controls

- keep a strict source snapshot during Pass 1
- treat structural and semantic changes as separate review lanes
- require every moved normative rule to have a destination
- require every deleted paragraph to be labeled as duplicate, moved, or intentionally retired
- keep machine-readable crosswalk tables from day one

## Recommended Outcome

By the end of the migration, DACS should read like:

- a small core
- five clear stage contracts
- a separate extension layer
- separate registries
- separate domain profiles
- separate deployment/governance/roadmap documents

That is the structure most likely to survive growth without becoming harder to reason about every quarter.
