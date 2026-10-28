# Worked pilot brief · Enquiry to approved CRM handoff

**Classification: synthetic worked example.** This is a completed specimen of a pilot brief, not a client proposal or evidence that a pilot has taken place. The commercial and operational terms of an actual engagement must be agreed separately.

## 1. Decision and hypothesis

**Business decision:** should a manufacturing sales team invest in a controlled enquiry-processing workflow?

**Hypothesis to test:** converting an enquiry into a structured, reviewable record could reduce repeated transcription while preserving human control over price and customer commitments. The hypothesis is unmeasured in this example.

**Workflow boundary:** one English-language enquiry format, one synthetic product catalogue and one local CRM simulation. The reference run ends when a draft with a matching scripted approval record has been recorded in that simulation.

## 2. Included and excluded work

| Included | Excluded |
|---|---|
| Load a synthetic enquiry and assign a stable reference | Read a real mailbox or contact a customer |
| Produce a structured draft using the declared extraction method | Claim that a rules-based example measures a language model |
| Check required fields, known products and permitted quantities | Decide custom pricing, credit terms, tax or delivery commitments |
| Calculate a draft using a versioned synthetic price list | Issue an invoice, accept an order or send a quotation |
| Bind a scripted, unauthenticated review record to the draft version | Authenticate a real reviewer or provide an interactive approval interface |
| Write once to a local CRM simulation and record the result | Connect to a real CRM, ERP, payment system or production schedule |
| Raise validation errors and demonstrate retry behaviour | Provide a review-queue interface or automatically resolve ambiguous specifications |

## 3. Actors and authority

| Role | Decision owned |
|---|---|
| Business owner | Scope, baseline, acceptable business behaviour and acceptance |
| Sales reviewer | Confirms the draft and authorises the specific revision |
| Engineering owner | Implementation, test evidence, recovery and handover |
| Data/system owner | Permission for data sources, environments, access and retention |
| Operations owner | Agreed monitoring and post-release handling |

One person may hold several roles in a small pilot. Record each assignment rather than assuming an unassigned responsibility is covered.

## 4. Data and proposed interface contract

All pilot inputs are invented. A record contains an enquiry reference, product reference, quantity and source text. The catalogue contains permitted product references, draft unit prices in EUR and a quantity limit for each product. A `QuoteDraft` keeps the fixed status `DRAFT_REQUIRES_REVIEW`, catalogue version and source fingerprint; a content fingerprint identifies the draft revision. An `ApprovalRecord` is a separate object containing the reviewed draft fingerprint, reviewer label and decision. The simulation records the external reference and the approved fingerprint so a retry can be recognised.

In the reference catalogue, an acceptable quantity is a whole number from 1 to the selected product's `maximum_quantity`: 10,000 for `BRKT-100` and 5,000 for `PANEL-200`. Unknown products, missing quantities, ambiguous variants and out-of-range values stop processing for review. These are illustrative business rules, not universal manufacturing rules.

The local approval record is scripted and unauthenticated. It exercises a version-bound execution gate, not a live human-review process. A reviewer label is not authentication of a real employee; a live approval channel and its authority checks require a separate implementation and evaluation. Invalid input raises a validation error; the reference does not implement a review queue.

| Source | Purpose | Permitted destination |
|---|---|---|
| Synthetic enquiries | Demonstrate extraction and validation | Local test runner and local report |
| Synthetic catalogue | Create a draft estimate | Local workflow only |
| Scripted, unauthenticated demo approval | Exercise the version-bound approval gate | Separate local review object |
| Approved draft | Exercise idempotent handoff | Local CRM simulation |

No model provider is required by this specimen. Adding a model, a hosted service or live data is a scope change requiring a new data-flow review and fresh evaluation.

## 5. Proposed evidence and release gates

These are **proposed pilot criteria**, to be agreed before a real build. The table does not report passed tests.

| Gate | Proposed check | Evidence to retain |
|---|---|---|
| Required data | Missing, invalid or unknown values never reach handoff | Case list and machine-readable outcomes |
| Approval | An unapproved draft cannot be handed off | Rejected-operation test |
| Revision control | A changed draft invalidates its earlier approval | Mutation-after-approval test |
| Repeat submission | Repeating the same approved handoff produces one record | Before/after database inspection |
| Recoverable failure | A simulated temporary failure can be retried without losing the approval binding or duplicating the record | Failure/retry trace |
| Input isolation | Source text is not used as approval or catalogue configuration | Adversarial input case |
| Traceability | A handoff can be tied to input, draft version and approval event | Redacted event trace |
| Scope control | No network request or customer message is made by the reference runner | Implementation review and execution environment record |

For the local reference, all designated control cases should pass before a revision is presented as complete. Passing them establishes only the tested behaviour in the local simulation. A real pilot needs representative client cases, environment checks and business-owner acceptance as additional gates.

## 6. Delivery stages and outputs

| Stage | Work | Exit evidence |
|---|---|---|
| Baseline and scope | Observe the existing process; agree boundaries and data access | Approved brief, baseline definitions and responsibility record |
| Build and demonstrate | Implement the workflow with synthetic or approved samples | Versioned code, architecture and sample outputs |
| Evaluate | Run agreed normal, boundary and failure cases | Dataset description, result report and limitations |
| Decide | Review business value, operational readiness and remaining risk | Accepted/rejected/deferred decision with reasons |
| Handover if accepted | Transfer agreed artefacts and rehearse recovery | Completed handover checklist and support record |

Elapsed delivery time is intentionally not fixed by this specimen. Data access, interface quality and the agreed scope determine the project schedule.

## 7. Principal risks and responses

| Risk | Planned response | Decision owner |
|---|---|---|
| Unclear product specifications | Stop and request clarification; do not infer a commercial commitment | Sales reviewer |
| A price list is outdated | Version the catalogue; block or re-review affected drafts | Business owner |
| A third-party write times out | Inspect the handoff reference before retrying; require idempotency support | Engineering owner |
| Approval is applied to an old draft | Check the current fingerprint at the handoff gate | Engineering owner |
| Recovered time does not become cash savings | Report capacity and cash effects separately | Business owner |
| Live data is introduced without an agreed record | Pause that data path until permissions and handling are recorded | Data/system owner |

## 8. Business-value assessment

Record monthly eligible enquiry volume and observed handling time before the pilot. During evaluation, include reviewer time, exception handling and maintenance effort. Compare like-for-like work over a stated period and report uncertainty. Report recovered hours separately from realised reductions in spending.

No baseline, handling-time improvement, revenue change or cost saving is asserted by this example.

Related: [requirements](../templates/requirements.md), [acceptance](../templates/acceptance-checklist.md), [data record](../templates/data-and-suppliers.md), [runbook](../templates/operations-runbook.md).
