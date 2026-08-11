# Singapore AI Governance Evidence Checklist

Interactive version: [vyrwork.com/tools/singapore-ai-governance-readiness-checklist](https://vyrwork.com/tools/singapore-ai-governance-readiness-checklist)

Mark an item only when the review team can inspect current evidence. This is a planning aid, not a compliance score, certification, audit, legal opinion, or guarantee.

## 1. Bound risk and autonomy

Assess and bound risks before an agent receives production access.

- [ ] The use case has a specific purpose, owner, affected users, and measurable operating baseline.
  - Evidence: use-case register and approved problem statement.
- [ ] The team has mapped inputs, outputs, models, hosting, telemetry, backups, connectors, subprocessors, and transfers.
  - Evidence: current data-flow and system-context diagrams.
- [ ] Allowed, prohibited, read-only, reversible, consequential, and externally visible actions are explicitly classified.
  - Evidence: tool and action permission matrix.
- [ ] Autonomy and human-review thresholds follow business impact rather than a generic confidence score.
  - Evidence: risk-tier and approval-threshold record.
- [ ] Representative, edge, adversarial, stale-data, unavailable-system, and prompt-injection cases are documented.
  - Evidence: versioned evaluation and abuse-case set.
- [ ] Pilot limits, stop conditions, rollback, duplicate-action prevention, and safe manual fallback are agreed.
  - Evidence: release, rollback, and continuity plan.

## 2. Meaningful human accountability

Name the people who may approve, change, monitor, investigate, accept risk, and stop the system.

- [ ] A business owner is accountable for purpose, operating outcome, affected users, and residual business risk.
  - Evidence: named owner and decision-rights record.
- [ ] A technical owner is accountable for configuration, access, dependencies, monitoring, recovery, and retirement.
  - Evidence: RACI and operating runbook.
- [ ] Privacy, data, security, legal, and sector reviewers are involved according to the actual use case.
  - Evidence: completed review and advice records.
- [ ] Each consequential action has an authorised approver, evidence view, expiry rule, and tested execution block.
  - Evidence: approval design and bypass-test results.
- [ ] Uncertainty, policy exceptions, user complaints, security events, and failed writes have named escalation paths.
  - Evidence: escalation matrix and incident playbook.
- [ ] The accountable authority signs off acceptance criteria and residual risk before production release.
  - Evidence: dated release and risk-acceptance decision.

## 3. Lifecycle technical controls

Treat governance as an operating process spanning permissions, tests, event records, monitoring, change control, incident response, and retirement.

- [ ] Models, prompts, tools, retrieval sources, policies, datasets, dependencies, and owners are versioned and inventoried.
  - Evidence: system inventory and version register.
- [ ] The release is tested against agreed task, safety, security, fairness, privacy, and escalation criteria where applicable.
  - Evidence: test plan, results, failures, remediation, and sign-off.
- [ ] Identities, secrets, data access, filesystem access, network egress, and tool permissions use least privilege.
  - Evidence: access review and enforced permission configuration.
- [ ] Approved sources, provenance, validation, abstention, uncertainty, and output-handling rules are defined and tested.
  - Evidence: grounding policy and source-quality test results.
- [ ] Events record the relevant input reference, version, tool, proposed action, approval, outcome, error, and actor without unnecessary secrets or personal data.
  - Evidence: sample event records, retention, access, and export tests.
- [ ] Model, prompt, connector, permission, dependency, and policy changes trigger proportionate retesting, approval, monitoring, and retirement decisions.
  - Evidence: change, patch, incident, and retirement procedures.

## 4. End-user responsibility

Give operators and affected users enough information, control, and support to use the system appropriately and challenge an outcome when needed.

- [ ] Users receive appropriate notice about AI involvement, purpose, data use, material limitations, and human contact routes.
  - Evidence: approved notices, interface copy, and communication plan.
- [ ] Operators know permitted uses, prohibited uses, verification duties, escalation thresholds, and failure indicators.
  - Evidence: role-specific instructions and training record.
- [ ] Reviewers can see the evidence needed to decide and are not pressured to rubber-stamp high-volume approvals.
  - Evidence: reviewer-interface test and workload assessment.
- [ ] Users can report a problem, request human review, contest an outcome, and reach a responsible team.
  - Evidence: feedback, appeal, and response workflow.
- [ ] Applicable access, correction, retention, withdrawal, deletion, and complaint processes include AI-system records.
  - Evidence: privacy-operation procedure and retrieval test.
- [ ] The organisation can export necessary records, revoke access, remove data, replace providers, and retire the system safely.
  - Evidence: exit, deletion, portability, and decommissioning plan.

## Review record

- System or workflow:
- Business owner:
- Technical owner:
- Review date:
- Guidance versions used:
- Open evidence gaps:
- Release decision and approver:

Read the supporting [Singapore AI governance implementation guide](https://vyrwork.com/blog/ai-governance-framework-singapore-enterprises).
