# Requirements record · Template

**Use:** replace every `⟦...⟧` field before approval. This is a project template, not a record of agreed requirements.

| Field | Project entry |
|---|---|
| Project / workflow | ⟦name and business unit⟧ |
| Document revision / date | ⟦revision and date⟧ |
| Business owner / engineering owner | ⟦roles or names⟧ |
| Decision this workflow supports | ⟦specific operational decision⟧ |
| Start / end of workflow | ⟦trigger and completion event⟧ |
| Explicit exclusions | ⟦actions and systems outside scope⟧ |
| Source of authority | ⟦who may approve prices, orders, changes and release⟧ |

## Baseline and success

| Measure | Definition and collection method | Baseline | Target / decision rule |
|---|---|---|---|
| Handling time | ⟦include review and exception work; define sample⟧ | ⟦value, period, sample size⟧ | ⟦agreed threshold⟧ |
| Quality | ⟦required fields and acceptable error types⟧ | ⟦measured baseline⟧ | ⟦agreed threshold⟧ |
| Eligible volume | ⟦which transactions qualify and why⟧ | ⟦volume and period⟧ | ⟦coverage requirement⟧ |
| Operating cost | ⟦model, infrastructure, support and added oversight⟧ | ⟦cost and period⟧ | ⟦agreed ceiling / budget⟧ |

Record capacity gained separately from actual reductions in spending. Explain any estimate rather than presenting it as observed data.

## Functional requirements

Add one row per observable behaviour. Avoid requirements such as “be intelligent” or “be enterprise-ready.”

| ID | Trigger and input | Required behaviour | Failure / review route | Acceptance evidence |
|---|---|---|---|---|
| REQ-001 | ⟦specific input condition⟧ | ⟦output or state transition⟧ | ⟦stop, retry or named reviewer⟧ | ⟦test case IDs and expected results⟧ |
| REQ-002 | ⟦specific input condition⟧ | ⟦output or state transition⟧ | ⟦stop, retry or named reviewer⟧ | ⟦test case IDs and expected results⟧ |

## Data and interfaces

For each interface, record: owner; permitted environment; data fields and sensitivity; authentication owner; timeout behaviour; retry and deduplication rules; rate limits; failure signal; downstream effects; and how a write can be verified or reversed. Attach the completed [data and supplier record](data-and-suppliers.md).

## Approval and control rules

- Actions needing explicit human approval: ⟦list⟧.
- Identity or role authorised to approve: ⟦role and authentication method⟧.
- What approval binds to: ⟦draft version / fingerprint and relevant rules version⟧.
- What invalidates approval: ⟦changed fields, catalogue changes, expiry or other conditions⟧.
- Prohibited actions: ⟦list and enforcement point⟧.
- Manual fallback if the system is unavailable: ⟦process and owner⟧.

## Acceptance and change control

Evaluation dataset: ⟦location, provenance, permission, revision and representativeness⟧.

Acceptance criteria: ⟦link to completed checklist and any numeric thresholds⟧.

Open questions and decisions: ⟦question, owner, due date and decision required⟧.

Approvals: ⟦business owner, data/system owner, engineering owner, revision and date⟧.

A later change to scope, data, model, integration or acceptance criteria needs an impact assessment and a recorded decision using the [change scope](support-and-change.md).
