# Handover checklist · Template

**Use:** choose the applicable items and record evidence. This blank checklist does not assert that a delivery has been completed.

Project / environment: ⟦values⟧ · Release: ⟦revision⟧ · Receiving owner: ⟦role⟧ · Date: ⟦date⟧.

## Scope and acceptance

- [ ] Agreed requirements, exclusions and later scope decisions are available.
- [ ] Acceptance results identify the exact revision, configuration and evaluation dataset.
- [ ] Known limitations, failed cases and deferred items have named owners.
- [ ] Business acceptance and permission to run in the relevant environment are recorded separately.

## Implementation and access

- [ ] Source, configuration templates, dependency versions and build/start instructions are delivered as agreed.
- [ ] Architecture and interface contracts match the delivered revision.
- [ ] Repository, hosting and integration ownership are explicit.
- [ ] Credentials are transferred through an agreed secure channel; they are absent from source, examples and logs.
- [ ] The client can grant and revoke the required access without depending on an undocumented personal account.
- [ ] Intellectual-property, third-party licence and reuse terms are covered by the project agreement.

## Operation and recovery

- [ ] A receiving operator can start, pause and resume the workflow using the documented steps.
- [ ] Monitoring signals, recipients, thresholds and coverage are agreed.
- [ ] Review queues and unprocessed items have a named owner.
- [ ] Retry, outcome-unknown reconciliation and manual fallback have been demonstrated in the agreed environment.
- [ ] A recovery point and compatible rollback procedure are documented and rehearsed where in scope.
- [ ] External actions requiring separate reversal or reconciliation are identified.

## Data and suppliers

- [ ] The [data/supplier record](data-and-suppliers.md) lists approved destinations, access roles and subprocessors where applicable.
- [ ] Retention, deletion, export and backup handling have explicit owners and agreed settings.
- [ ] Provider configuration and any model/data-use settings have been checked against the agreed requirements.
- [ ] Test data, temporary access and development copies are removed or retained according to the agreed decision.

## Training and support

- [ ] Reviewers understand what they are approving and what invalidates approval.
- [ ] Operators know how to identify and escalate an exception.
- [ ] Training materials and the walkthrough recording, if agreed, are delivered.
- [ ] Support boundaries, coverage, contacts and exclusions are written down.
- [ ] Open work is classified as included correction, agreed improvement or separately scoped change.
- [ ] Exit steps cover access revocation, data export/deletion and ownership of final artefacts.

## Completion record

| Item / document | Location / revision | Receiving owner | Status / unresolved action |
|---|---|---|---|
| ⟦artefact⟧ | ⟦location and revision⟧ | ⟦role⟧ | ⟦received, pending or not applicable with reason⟧ |

Handover decision: ⟦complete / complete with conditions / incomplete⟧.

Receiving owner acknowledgement: ⟦role, revision and date⟧. Delivery owner: ⟦role and date⟧.
