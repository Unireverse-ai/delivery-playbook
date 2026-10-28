# UniReverseAI · Delivery Playbook

Practical documents for scoping, evaluating and handing over applied AI workflows.

UniReverseAI works on AI opportunity assessment, sales operations, sales-to-production coordination and the operation of agreed workflows. This repository shows how a bounded engagement can be specified and reviewed: what will be built, where people approve decisions, how failures are handled and what a client receives at handover.

**Repository status:** public reference material. The worked examples are synthetic. Templates require project-specific decisions and client agreement; they are not an executed contract, a service-level commitment or a statement that these controls are already operating in a client environment.

## Start here

For an initial review, take the [five-minute buyer route](docs/buyer-guide.md) for procurement, business or technical reviewers. For a pilot decision, pair the [evaluation scorecard](templates/pilot-evaluation-scorecard.md) with a [measurement plan](templates/measurement-plan.md).

| Your question | Read |
|---|---|
| What would a pilot actually cover? | [Worked pilot brief](docs/pilot-brief.md) |
| How do we define a buildable requirement? | [Requirements template](templates/requirements.md) |
| How do we decide whether it is ready? | [Pilot scorecard](templates/pilot-evaluation-scorecard.md) and [acceptance checklist](templates/acceptance-checklist.md) |
| What happens when something fails? | [Operations runbook](templates/operations-runbook.md) |
| What will our team receive? | [Handover checklist](templates/handover-checklist.md) |
| Where does data go, and who decides? | [Data and supplier record](templates/data-and-suppliers.md) |
| What is covered after delivery? | [Support and change scope](templates/support-and-change.md) |
| How are outcomes substantiated? | [Measurement plan](templates/measurement-plan.md), [case study template](templates/case-study.md) and [illustrative example](examples/illustrative-case-study.md) |
| What evidence should we request in due diligence? | [Buyer evidence index](docs/due-diligence-index.md) |

## The delivery approach

1. **Establish the baseline.** Describe the current process, volumes, handling time, failure modes and the cost of operating it.
2. **Bound the intervention.** Agree one workflow, its interfaces, excluded actions, approval points and a named business owner.
3. **Demonstrate with representative cases.** Evaluate ordinary work and exceptions before connecting an approved production environment.
4. **Accept against written evidence.** Keep test results, unresolved limitations and the business owner's decision together.
5. **Hand over an operable system.** Document credentials ownership, monitoring, recovery, support boundaries and exit steps.

Business benefits, technical acceptance and permission to go live are separate decisions. A workflow can pass functional checks while still lacking sufficient business value or operational approval.

## How to use the material

Read the worked brief first. For a real engagement, copy the templates into the project's agreed document system, replace every `⟦...⟧` field, choose the applicable controls and obtain the required approvals. Keep customer records and approvals in that private project record rather than opening public Issues with them.

The documents can also structure a technical review of our reference implementation. Any actual evaluation result should link to the exact code revision, input dataset and report used; this playbook does not substitute for that evidence.

## About the examples

The examples use a fictional manufacturing enquiry process, synthetic inputs and a simulated CRM. They do not describe a named customer, a commercial deployment or measured savings. No production integration, independent audit or certification is asserted.

For business enquiries or a private evidence review, contact [Eric@unireverseai.com](mailto:Eric@unireverseai.com). The [website is in preparation](https://unireverseai.com).

## Rights

Source and documents are provided for inspection. No open-source licence is granted. See [RIGHTS.md](RIGHTS.md).
