# Acceptance checklist · Template

**Use:** record the result and evidence for the agreed project revision. An unticked box means “not yet evidenced,” not an assertion that the control exists. Agree thresholds with the business owner before evaluating.

Project: ⟦name⟧ · Code/configuration revision: ⟦revision⟧ · Dataset revision: ⟦revision⟧ · Environment: ⟦environment⟧ · Review date: ⟦date⟧.

## Functional and control checks

- [ ] Required fields and permitted values are defined and validated.
- [ ] Missing or ambiguous input reaches the agreed review route.
- [ ] Boundary values, unknown products and invalid quantities are tested.
- [ ] Unapproved actions are blocked at the execution boundary.
- [ ] Approval is bound to the specific reviewed draft; changing it requires reapproval.
- [ ] Source text cannot modify tool permissions, pricing authority or approval state.
- [ ] Repeated delivery of the same request has the agreed deduplication behaviour.
- [ ] Temporary failures and retries preserve state and do not repeat a business action.
- [ ] A timeout after a possible downstream write is resolved by checking the downstream reference before retry.
- [ ] Permanent failures stop safely and reach the named owner.
- [ ] Logs identify the relevant input, revision and decision without exposing unnecessary sensitive fields.
- [ ] Prohibited actions and out-of-scope systems remain inaccessible to the workflow.

## Evaluation and value checks

- [ ] The evaluation set represents agreed common cases and material exceptions.
- [ ] Metrics include a denominator, sample size, evaluation period and definitions.
- [ ] Human review and exception effort are included in handling-time measurements.
- [ ] Operating cost includes agreed model, infrastructure, monitoring and maintenance costs.
- [ ] Recovered hours and realised cash savings are reported separately.
- [ ] Remaining limitations and failed cases are documented alongside successful results.
- [ ] Synthetic results are labelled and are not presented as customer outcomes.

## Operational readiness

- [ ] Required data permissions and the [data/supplier record](data-and-suppliers.md) are complete.
- [ ] Client ownership of systems, credentials and access revocation is documented.
- [ ] Monitoring signals, recipients and response arrangements are agreed.
- [ ] Pause, restart, recovery and manual fallback steps have been rehearsed in the agreed environment.
- [ ] A release can be tied to a known configuration and a recovery point.
- [ ] The [handover checklist](handover-checklist.md) is complete for the applicable stage.
- [ ] Support scope and any additional work are documented.

## Result record

| Check / metric | Agreed threshold | Actual result | Evidence location | Reviewer / decision |
|---|---|---|---|---|
| ⟦case or metric ID⟧ | ⟦threshold⟧ | ⟦result or not evaluated⟧ | ⟦report, revision and case ID⟧ | ⟦reviewer and decision⟧ |

Open issues: ⟦issue, severity, impact, owner and required action⟧.

Decision: ⟦accepted / accepted with recorded conditions / deferred / rejected⟧.

Business acceptance: ⟦owner, revision and date⟧. Operational release approval: ⟦owner, environment and date, or not granted⟧. These are separate decisions; accepting a local demonstration does not authorise production access.
