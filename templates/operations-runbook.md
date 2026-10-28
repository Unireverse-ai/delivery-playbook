# Operations runbook · Template

**Use:** adapt and rehearse these procedures in the agreed environment. The steps describe a proposed operating pattern, not a currently staffed service. Replace all `⟦...⟧` fields and remove inapplicable steps before release.

## Ownership and controls

| Item | Project entry |
|---|---|
| Workflow / environment / current revision | ⟦values⟧ |
| Business owner / operations owner | ⟦roles and private contact route⟧ |
| Engineering escalation | ⟦private contact route and agreed coverage⟧ |
| Pause / resume control | ⟦location, permission and exact procedure⟧ |
| Queue and failed-item view | ⟦location and access owner⟧ |
| Manual fallback | ⟦process, owner and reconciliation steps⟧ |
| Previous known-good revision | ⟦revision, configuration and recovery artefacts⟧ |

## Signals to monitor

Agree collection, access, thresholds and recipients for each applicable signal.

| Signal | Why it matters | Threshold / action |
|---|---|---|
| Processing failures and age of oldest pending item | Work may be stalled | ⟦threshold, owner and action⟧ |
| Validation/review queue volume | Input quality or business rules may have changed | ⟦threshold, owner and action⟧ |
| Downstream timeouts or rejected writes | State may be uncertain | ⟦threshold, owner and action⟧ |
| Duplicate or conflicting references | Repeated or inconsistent business actions may occur | ⟦threshold, owner and action⟧ |
| Approval mismatches | An edited draft or stale approval may be in use | ⟦threshold, owner and action⟧ |
| Usage and operating cost | Spend may differ from the agreed model | ⟦threshold, owner and action⟧ |

Do not place raw customer messages, full personal identifiers, access tokens or approval credentials in routine logs. Decide the necessary event fields and retention in the [data record](data-and-suppliers.md).

## First response

1. Identify the environment, workflow revision, incident time and affected references.
2. Decide whether continuing could repeat a write, disclose data or make an unauthorised commitment. If so, pause the relevant execution path using the agreed control.
3. Preserve the minimum necessary event evidence. Do not copy customer data into public Issues.
4. Assign an owner and classify the state: validation failure, temporary dependency failure, uncertain downstream write, permanent failure or suspected data/security incident.
5. Follow the matching procedure below and record the resolution.

## Procedure A · Missing or ambiguous input

- Mark the item for the agreed reviewer and keep it outside the execution queue.
- Record which field or rule prevented processing.
- Obtain the correction through the approved process.
- Rebuild the draft and rerun validation. If a draft changed, obtain a fresh approval for its new revision.

Never replace a missing commercial fact with a guessed value merely to unblock the queue.

## Procedure B · Temporary dependency failure

- Confirm that the failure is retryable under the interface contract.
- Check the stable request reference and downstream state before another write.
- Use the agreed bounded retry policy: ⟦maximum attempts, delay/backoff and total time limit⟧.
- Preserve the same business reference and current approved draft binding across retries.
- After the limit, stop automatic attempts and route to ⟦owner⟧.

An indefinite loop is not a recovery policy. A new revision or new business request must not be disguised as a retry.

## Procedure C · Timeout after a possible write

1. Mark the item as **outcome unknown** and prevent automatic creation of a second request.
2. Query the downstream system using its stable external reference or idempotency key.
3. If exactly one matching, correct record exists, reconcile its identifier to the local state.
4. If no record exists and the interface contract permits a safe retry, retry with the same reference.
5. If the result cannot be established, or conflicting records exist, escalate for manual reconciliation.

This procedure requires a downstream verification mechanism. If the real interface cannot provide one, agree an alternative before enabling automated writes.

## Procedure D · Stale approval or changed business rules

- Stop the affected handoff.
- Compare the reviewed draft, current draft and relevant rule/catalogue versions.
- Explain the changed fields to the reviewer.
- Revalidate and request new approval. Never edit the stored approval to make a mismatch disappear.

## Procedure E · Pause and recover a release

1. Pause new execution and capture the outstanding queue and references.
2. Determine which external actions have already happened. A code rollback does not undo sent messages, orders or external writes.
3. Select the known-good code and compatible configuration/data state. Check any migration before restoring.
4. Restore or redeploy using ⟦environment-specific procedure⟧. Restore backups only after the data/system owner approves the recovery point and potential data loss.
5. Rehearse the agreed smoke and control checks.
6. Reconcile pending and completed work against downstream records before resuming.
7. Obtain ⟦release owner's⟧ decision, resume in the agreed sequence and monitor the first transactions.

## Procedure F · Suspected data or credential incident

- Pause the affected path and limit access using the agreed permissions.
- Contact the nominated data/system owner through the private escalation route.
- Preserve relevant evidence without broadening access or publishing incident details.
- Rotate or revoke affected credentials through their owner where appropriate.
- Follow the project's agreed incident and notification process. Notification decisions and legal obligations require the responsible owner; this template does not set a universal deadline.

## Incident record and closure

Record: affected references; impact and duration; first signal; revision; actions and decision owners; evidence locations; reconciliation outcome; restoration checks; and follow-up work with owners. Capture observed facts separately from hypotheses.

Closure requires confirmation that work is reconciled, the workflow is in a known state and the business owner understands any unresolved consequences. Update the runbook if the recovery exposed a missing step.
