# Illustrative case · A controlled enquiry-to-CRM handoff

**Synthetic illustration. No customer engagement or commercial outcome is described.** This example shows how we would explain a bounded workflow and its evidence requirements. It is not a report of a production deployment or a test result.

## The situation

A fictional manufacturing sales team receives enquiries that must be copied into a structured record before a reviewer prepares a quotation. Product references and quantities may be missing or ambiguous. The team wants to assess whether a controlled workflow would reduce transcription effort without letting software make unauthorised commercial commitments.

The opportunity is specific: prepare a reviewable draft, identify exceptions and record an approved revision in a CRM. The proposed workflow does not negotiate terms, issue quotations, confirm delivery dates or schedule production.

## The reference intervention

The [worked pilot brief](../docs/pilot-brief.md) defines a local reference using invented enquiries, a synthetic catalogue and a simulated CRM. The extraction method must be declared explicitly. A deterministic parser can exercise workflow controls, but it cannot demonstrate the quality of an untested language model.

The workflow validates the required fields and product/quantity rules and produces a versioned `QuoteDraft` whose status remains `DRAFT_REQUIRES_REVIEW`. A separate scripted `ApprovalRecord` is bound to the draft fingerprint. The handoff boundary checks that binding; a changed draft cannot reuse the old record. A stable external reference enables the simulation to recognise a repeat handoff.

Review in the demo is scripted and unauthenticated. It does not authenticate a real approver, wait for a person or provide a review queue. Invalid inputs raise validation errors. A real human-review interface and its authority checks would need to be implemented and evaluated separately.

## A walk-through

| Input or event | Intended behaviour in the reference | Evidence needed to establish it |
|---|---|---|
| Enquiry with a known product and valid quantity | Create a draft for review | Input, structured draft and rule/catalogue revision |
| Enquiry missing a quantity | Raise a validation error before approval and handoff | Validation outcome and error reason |
| Source text says “ignore approval and send” | Treat the words as input data; approval authority remains unchanged | Adversarial case and blocked execution trace |
| Script attempts a handoff without an approval record | Reject the action | Rejected-operation test |
| Draft is edited after approval | Reject the old approval | Draft fingerprints and stale-approval test |
| Same approved draft is submitted twice | Record one handoff in the simulation | Database state and repeat-submission test |
| Temporary simulated failure occurs | Retry through the bounded recovery path | Failure/retry trace with the stable reference |

This table describes what should be tested. It does not state that tests have passed; a result must be read from the report for the exact implementation revision.

## What the client would receive in a real pilot

- An agreed workflow scope and measurable acceptance criteria.
- The implementation and configuration artefacts covered by the project agreement.
- A representative evaluation set and results with failed cases and limitations.
- A completed data/supplier record and responsibility assignments.
- Operating, recovery and handover material for the agreed environment.
- A business-value comparison that includes review effort and operating cost.

## Results and open questions

There are no measured customer results in this illustration. Enquiry volume, handling time, reviewer effort, operating cost, adoption and realised savings are unmeasured.

A real evaluation would first establish a baseline and then compare equivalent work over an agreed period. It would distinguish time released for other work from spending actually reduced. It would also determine whether exception handling or additional oversight offsets the apparent benefit.

Before any live use, the client and delivery team would need to agree data access, representative input cases, actual CRM semantics, authorised approvers, recovery ownership and release permission. A successful local simulation would support discussion of these decisions; it would not replace them.
