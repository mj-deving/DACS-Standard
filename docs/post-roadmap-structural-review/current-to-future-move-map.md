# Current-to-Future Move Map

## `CORE.md`

| Current material | Future home | Action |
| --- | --- | --- |
| Front-matter motivation and navigation | `PRIMER` + short `DACS-CORE` intro | Move |
| Problem / approach / five stages | `PRIMER` | Move |
| Per-stage summary table | `PRIMER` or overview appendix | Move |
| Substrate capability model | `DACS-CORE` | Keep |
| Shared canonicalization, signature, reference, nonce rules | `DACS-CORE` | Keep |
| Demos production mapping | `DACS-MAPPINGS` | Move |
| Composed-standards reference material | `PRIMER` or reference appendix | Shrink and move |
| Stewardship/versioning/follow-on | `DACS-GOVERNANCE` + `DACS-ROADMAP` | Split and move |
| Threat model | `DACS-THREAT-MODEL` | Move |
| Glossary | `DACS-GLOSSARY` | Move |
| Conformance plan | `DACS-CONFORMANCE` | Move |

## `DACS-1-IDENTIFY.md`

| Current material | Future home | Action |
| --- | --- | --- |
| Identity bundle | `DACS-1` | Keep |
| `presentedBy` and control proof rules | `DACS-1` | Keep |
| Listing shape and listing validity | `DACS-1` | Keep |
| Discovery surfaces | `DACS-1` | Keep |
| Claim scheme registry table | `DACS-REGISTRIES` | Move |
| Scheme-specific authority notes | `DACS-HOOKS` or registry notes | Move |
| Demos-specific write/address detail | `DACS-MAPPINGS` | Move |
| Excess rationale/back-compat prose | `PRIMER` or appendix | Shrink and move |

## `DACS-2-VET.md`

| Current material | Future home | Action |
| --- | --- | --- |
| `VerifyResult` | `DACS-2` | Keep |
| Composite verification record | `DACS-2` | Keep |
| Freshness/sufficiency contract | `DACS-2` | Keep |
| `vet-credentials` phase | `DACS-2` | Keep |
| Verification method details | `DACS-HOOKS` | Move |
| Recipe schemas and parser specs | `DACS-REGISTRIES` + `DACS-HOOKS` | Split |
| Availability states and operational gating | `DACS-REGISTRIES` | Move |
| Recipe governance/emergency update process | `DACS-GOVERNANCE` | Move |
| Authority-specific trust caveats | hook docs | Move |

## `DACS-3-NEGOTIATE.md`

| Current material | Future home | Action |
| --- | --- | --- |
| `AgreementDocument` | `DACS-3` | Keep |
| `commit-agreement` | `DACS-3` | Keep |
| Minimal channel trust properties | `DACS-3` with CORE references | Keep |
| Fixed-price pattern | `DACS-3` or base profile | Keep minimal version |
| RFQ / sealed-envelope full detail | `DACS-PROFILES` + pattern registry | Move most detail |
| Pattern-specific tie-break ladders | `DACS-REGISTRIES` or profiles | Move |
| Transcript disclosure policy | profile-level unless universal | Move most |
| Negotiation-specific rollout notes | `DACS-ROADMAP` or `DACS-MAPPINGS` | Move |

## `DACS-4-SETTLE.md`

| Current material | Future home | Action |
| --- | --- | --- |
| `SettlementEvidence` | `DACS-4` | Keep |
| Payment phase contracts | `DACS-4` | Keep |
| Delivery phase contracts | `DACS-4` | Keep |
| Shared commercial types used across stages | `DACS-CORE` or a shared types annex | Move shared pieces |
| Rail registry contents | `DACS-REGISTRIES` | Move |
| Rail authoring/availability process | `DACS-REGISTRIES` + `DACS-GOVERNANCE` | Split |
| Per-rail provider/bridge specifics | `DACS-HOOKS` | Move |
| Current route maturity / deployment status | `DACS-MAPPINGS` | Move |
| Streaming / escrow roadmap text | `DACS-ROADMAP` | Move |

## `DACS-5-VERIFY.md`

| Current material | Future home | Action |
| --- | --- | --- |
| `SessionRecord` | `DACS-5` | Keep |
| Attestation bundle shape | `DACS-5` | Keep |
| State machine and terminal outcomes | `DACS-5` | Keep |
| Reconciliation rules | `DACS-5` | Keep |
| Minimal canonical reputation summary | `DACS-5` | Keep |
| Richer reputation math | `DACS-HOOKS` or `DACS-PROFILES` | Move most |
| ERC-8004 publication mapping | `DACS-MAPPINGS` or optional publication profile | Move |
| Optional scoring/publication behavior | `DACS-HOOKS` | Move |
| Policy-heavy cancellation/dispute interpretation | profiles or roadmap unless universal | Move most |

## Cross-Cutting Editorial Rule

For every future document, ask:

- Is this needed by every conforming implementation?
- Is this universal or only current?
- Is this protocol law or operational practice?
- Is this stable enough to deserve normative placement?

If the answer is “current”, “operational”, “provider-specific”, or “use-case-specific”, it should not stay in the core stage path.
