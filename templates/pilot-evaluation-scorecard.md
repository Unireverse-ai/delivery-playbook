# Pilot evaluation scorecard · Template

**Use:** agree the decision and thresholds before evaluating the pilot. This blank scorecard reports no passed tests and grants no production authority. Replace every `⟦...⟧` field and retain evidence privately where appropriate.

Project / unit of work: ⟦values⟧ · Stage: ⟦local reference / shadow pilot / reviewed live pilot / wider release⟧.

Code + configuration revision: ⟦revision⟧ · Dataset revision / sample dates: ⟦record⟧ · Environment: ⟦environment⟧ · Evaluation period: ⟦dates⟧.

Business decision owner: ⟦role/name⟧ · Technical owner: ⟦role/name⟧ · Data/system owner: ⟦role/name⟧ · Evaluation reviewer: ⟦role/name⟧.

## Describe the evidence, then judge it

These labels describe the source of an observation; they are not certifications or a maturity score. Retain revision, method, sample and limitations at every level.

| Label | Evidence supplied | What it can support |
|---|---|---|
| E0 · Proposed | Design, hypothesis or unexecuted template | A scoping discussion; no observed performance claim |
| E1 · Synthetic | Reproducible checks on identified invented cases in a declared environment | The behaviour observed on those cases |
| E2 · Representative | Agreed customer examples and approved test/shadow environment, including failures and material exceptions | A bounded pilot decision for the tested use and population |
| E3 · Operational | Measurements from an authorised live workflow over a stated period | The observed operating result in that scope; causal and cash claims still need their own method |

## Decision record

Set a denominator and threshold for every applicable measure. Record `not evaluated` rather than guessing. An exclusion needs a reason, owner and effect on the proposed release stage.

| Area | Measure / denominator | Threshold agreed before evaluation | Required evidence / level | Actual result and evidence link | Owner / decision |
|---|---|---|---|---|---|
| Scope | Supported formats, products, systems and prohibited actions | ⟦boundary⟧ | ⟦approved scope and execution evidence⟧ | ⟦not evaluated⟧ | ⟦owner; pass/fail/defer⟧ |
| Extraction quality | Correct required fields and clarification decisions / specified case groups | ⟦by field, group and consequence⟧ | ⟦dataset, independent labels, report; E1/E2 as appropriate⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |
| Action controls | Unapproved, stale, out-of-scope or inconsistent actions attempted / blocked | ⟦control cases and invariant⟧ | ⟦execution traces in the target environment⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |
| Recovery | Duplicate, partial-failure and unknown-outcome cases reconciled / tested | ⟦expected state and recovery limit⟧ | ⟦record inspection and recovery rehearsal⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |
| Human work | Handling, review, corrections and exception time / same unit of work | ⟦baseline and remaining burden⟧ | ⟦measurement plan and samples; E2/E3⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |
| Economics | Incremental costs, net cash and released capacity | ⟦budget, cash mechanism, horizon⟧ | ⟦inputs, spending evidence, scenario/cash-flow model⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |
| Data and access | Required destinations, suppliers, access and retention decisions completed | ⟦configuration and unresolved-item rule⟧ | ⟦completed data record and verification⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |
| Operation | Monitoring, pause, recovery, ownership and handover readiness | ⟦coverage and rehearsed procedures⟧ | ⟦runbook/handover and owner acceptance⟧ | ⟦not evaluated⟧ | ⟦owner; decision⟧ |

Do not use a weighted average that allows a high quality score to compensate for missing execution authority or unknown data destinations.

## Conditions that prevent a production decision

Until resolved, defer production authority when any of the following applies:

- Only synthetic evidence has been executed, while the proposed workflow depends on untested customer inputs or live interfaces.
- A critical control case fails, an action's downstream outcome is unknown, or recovery can duplicate or overwrite a business record.
- Review authority is unauthenticated, unassigned or not bound to the exact proposed action.
- Required data/supplier/access decisions remain unresolved, or the tested configuration differs materially from the proposed release.
- The team cannot pause the workflow, restore an agreed state, or identify its operating owner and escalation route.
- An agreed quality or budget condition is not met and the decision owner has not agreed a narrower, evidenced scope.

Zero observed failures in a small sample does not establish a zero failure rate. Record coverage, sample uncertainty and what remains untested.

## Separate the decisions

| Decision | Outcome | Evidence / unresolved conditions | Authorised owner and date |
|---|---|---|---|
| Technical acceptance for the stated stage | ⟦accept / narrow / defer / reject⟧ | ⟦record⟧ | ⟦owner/date⟧ |
| Business investment decision | ⟦proceed / narrow / defer / stop⟧ | ⟦record⟧ | ⟦owner/date⟧ |
| Permission for specified production actions | ⟦granted for listed actions / not granted⟧ | ⟦environment, limits, rollback, review date⟧ | ⟦owner/date⟧ |

Related: [acceptance checklist](acceptance-checklist.md), [measurement plan](measurement-plan.md), [data record](data-and-suppliers.md), [handover](handover-checklist.md).

Method reference: NIST's [AI RMF 1.0 discussion of validity and reliability](https://airc.nist.gov/airmf-resources/airmf/3-sec-characteristics/) calls for realistic test sets and documented evaluation methods. This project template is our own decision aid, not a NIST assessment or certification.
