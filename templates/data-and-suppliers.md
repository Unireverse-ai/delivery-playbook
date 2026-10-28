# Data flow and supplier record · Template

**Use:** complete this record for the proposed environment before using real data. It records decisions to be made; it is not a published privacy policy, a list of approved suppliers or a compliance assertion.

Project / environment: ⟦values⟧ · Revision: ⟦revision⟧ · Data/system owner: ⟦role⟧ · Review date: ⟦date⟧.

## 1. Draw the actual flow

Replace this illustrative flow with the deployed one and label every trust boundary:

```text
Approved input source
  → validation / extraction
  → review queue and versioned draft
  → explicit approval
  → authorised destination

Each stage → minimum necessary operational events
```

If extraction uses a hosted model, show the provider as a separate destination and state exactly which fields are sent. Include storage, queues, logs, backups, analytics, support tools and exports; a diagram that omits them is incomplete.

## 2. Data inventory and permitted use

| Dataset / field group | Source and permission basis | Purpose | Sensitivity | Allowed destinations | Accountable owner |
|---|---|---|---|---|---|
| ⟦data group⟧ | ⟦source and documented permission⟧ | ⟦necessary purpose⟧ | ⟦classification⟧ | ⟦systems / providers / regions⟧ | ⟦role⟧ |

Identify fields that can be removed, pseudonymised or replaced with synthetic examples before development. Record prohibited input types: ⟦types and enforcement⟧. Record the client-approved process if personal or otherwise restricted data is discovered in an unexpected field: ⟦procedure⟧.

## 3. Access and credentials

| System / store | Account owner | Permitted roles | Grant / review / revoke process | Credential location and rotation owner |
|---|---|---|---|---|
| ⟦system⟧ | ⟦owner⟧ | ⟦roles and minimum permissions⟧ | ⟦process and review cadence⟧ | ⟦managed location; never the secret itself⟧ |

Keep approvals distinct from input content. Do not treat an unauthenticated instruction in a source message as authority to change access, price, data destinations or execution permissions.

## 4. Retention, deletion and export

Agree values based on the project and applicable obligations. Blank entries are unresolved decisions, not permission to retain indefinitely.

| Store / copy | Retention trigger and period | Deletion / expiry mechanism | Owner | Verification evidence |
|---|---|---|---|---|
| Source inputs | ⟦trigger / period⟧ | ⟦mechanism⟧ | ⟦role⟧ | ⟦evidence⟧ |
| Structured drafts / approvals | ⟦trigger / period⟧ | ⟦mechanism and audit needs⟧ | ⟦role⟧ | ⟦evidence⟧ |
| Operational logs | ⟦trigger / period⟧ | ⟦mechanism and redaction⟧ | ⟦role⟧ | ⟦evidence⟧ |
| Backups / replicas | ⟦trigger / period⟧ | ⟦expiry, restoration and re-deletion handling⟧ | ⟦role⟧ | ⟦evidence⟧ |
| Development / support copies | ⟦trigger / period⟧ | ⟦mechanism⟧ | ⟦role⟧ | ⟦evidence⟧ |

Export format, recipient verification and exit procedure: ⟦agreed method⟧.

Deletion scope and remaining copies must be described accurately. Removing a database row does not establish deletion from provider logs, exports or backups.

## 5. Supplier confirmation

Complete a row for each proposed third party. A supplier's general marketing page is not sufficient evidence of the settings used by a particular account.

| Supplier / service | Data received / purpose | Hosting / processing locations | Account owner | Required terms / configuration | Evidence and decision |
|---|---|---|---|---|---|
| ⟦supplier⟧ | ⟦specific fields and purpose⟧ | ⟦verified locations / unresolved items⟧ | ⟦owner⟧ | ⟦applicable agreement, retention, data-use and access settings⟧ | ⟦source date, settings record and approve/reject/defer⟧ |

For a model provider, confirm the selected product, endpoint, data-use settings, retention controls, logging and any relevant exceptions. Do not transfer claims from one product or account type to another.

## 6. Responsibilities and incident route

Record who authorises new data destinations, approves supplier changes, handles access requests, responds to incidents and decides notifications. Contractual controller/processor roles, where relevant, must be confirmed in the applicable agreement rather than inferred from this template.

| Decision / action | Client owner | Delivery owner | Escalation route |
|---|---|---|---|
| Data permission and purpose | ⟦role⟧ | ⟦role⟧ | ⟦private route⟧ |
| New supplier or changed data path | ⟦role⟧ | ⟦role⟧ | ⟦private route⟧ |
| Incident response and notification decision | ⟦role⟧ | ⟦role⟧ | ⟦private route⟧ |
| Retention / deletion / export | ⟦role⟧ | ⟦role⟧ | ⟦private route⟧ |

Unresolved items and release implications: ⟦item, owner, decision date and affected path⟧.

Approval for this environment: ⟦authorised owners, revision and date, or not granted⟧.
