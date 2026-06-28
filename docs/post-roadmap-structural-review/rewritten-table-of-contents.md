# Proposed Rewritten Table of Contents

## A. `PRIMER`

- What DACS is
- What problem it solves
- Five-stage lifecycle
- One worked end-to-end example
- How to read the full standard

## B. `DACS-CORE`

- Scope and conformance boundary
- Canonicalization, hashing, signatures
- Shared identifiers and references
- Shared artifact base types
- Session/job identity
- Base outcomes and error vocabulary
- Minimal state-machine contract
- Capability model: SR-1..SR-5
- Extension model: hooks, profiles, registries

## C. `DACS-1 Identify`

- Stage purpose and contract
- Identity bundle
- Control proofs and `presentedBy`
- Listing shape
- Listing validity rules
- Discovery surfaces
- Identify outputs to later stages

## D. `DACS-2 Vet`

- Stage purpose and contract
- `VerifyResult`
- `CompositeVerificationRecord`
- Freshness and sufficiency rules
- `vet-credentials` phase
- Hook points for verification methods

## E. `DACS-3 Negotiate`

- Stage purpose and contract
- Minimal negotiation primitives
- `AgreementDocument`
- `commit-agreement`
- Hook points for negotiation patterns

## F. `DACS-4 Settle`

- Stage purpose and contract
- Shared commercial types
- `SettlementEvidence`
- Payment phase contracts
- Delivery phase contracts
- Hook points for rails and settlement adapters

## G. `DACS-5 Verify`

- Stage purpose and contract
- `SessionRecord`
- `AttestationBundle`
- Terminal outcomes and reconciliation
- Minimal canonical reputation summary
- Optional rate phase
- Hook points for richer scoring/publication

## H. `DACS-HOOKS`

- Hook contract shape
- Identity hooks
- Vet hooks
- Negotiation hooks
- Settlement hooks
- Reputation hooks
- Trust assumptions and failure semantics

## I. `DACS-REGISTRIES`

- Claim scheme registry
- Vet method registry
- Vet recipe registry
- Negotiation pattern registry
- Rail registry
- Optional rating/publication registries

## J. `DACS-PROFILES`

- Micropayment profile
- Bilateral RFQ profile
- Sealed procurement profile
- Institutional regulated-trade profile
- Cross-chain settlement profile

## K. Companion Documents

- `DACS-MAPPINGS`
- `DACS-GOVERNANCE`
- `DACS-ROADMAP`
- `DACS-THREAT-MODEL`
- `DACS-CONFORMANCE`
- `DACS-GLOSSARY`

## Reading Rule

The normative path should be:

1. `PRIMER`
2. `DACS-CORE`
3. one or more of `DACS-1..5`
4. hooks/registries/profiles only as needed

Governance, mappings, and roadmap material should not sit in the mandatory validity-reading path.
