---
title: Singapore AI Governance Evidence Pack
description: A free evidence-oriented template for reviewing AI systems and agents before production in Singapore.
---

# Singapore AI Governance Evidence Pack

Production governance becomes useful when a review team can inspect evidence, identify an accountable owner, and decide what must change before release. This free companion guide helps Singapore teams organise that evidence for an AI system or agent.

For the complete interactive assessment, use VYR's [Singapore AI Governance Readiness Checklist](https://vyrwork.com/tools/singapore-ai-governance-readiness-checklist). It contains 24 prompts organised around risk and autonomy, human accountability, lifecycle technical controls, and end-user responsibility.

## Start with a system record

Create one review record for each materially different workflow. Record its business purpose, business owner, technical owner, affected users, models, data sources, tools, permissions, hosting, vendors, and review date. Keep links to the current system-context diagram and data-flow diagram rather than copying details that will become stale.

## Collect inspectable evidence

A policy statement is not the same as an operating control. Reviewers should be able to inspect examples such as:

- an action-and-permission matrix separating read-only, reversible, consequential, prohibited, and externally visible actions;
- versioned evaluation results covering normal, edge, adversarial, stale-data, unavailable-system, and prompt-injection cases;
- approval rules showing who can authorise a consequential action and how execution is blocked without approval;
- sample event records linking the relevant system version, proposed action, approval, outcome, error, and actor;
- escalation, incident, rollback, continuity, data-deletion, provider-exit, and retirement procedures; and
- notices and operator instructions explaining AI involvement, limits, verification duties, human-review routes, and complaint handling.

Avoid placing secrets or unnecessary personal data in the evidence pack. Link to access-controlled records when the material should not be public.

## Record the decision

Close each review with open evidence gaps, required remediation, residual risks, the release decision, the accountable approver, and the next review trigger. Model, prompt, connector, permission, dependency, data-source, and policy changes should trigger proportionate retesting rather than waiting for an annual review.

## Free formats

- [Printable Markdown checklist](https://github.com/dextee/singapore-ai-governance-checklist/blob/main/CHECKLIST.md)
- [AI agent production release-review template](ai-agent-release-review-template.html)
- [Repository and source references](https://github.com/dextee/singapore-ai-governance-checklist)
- [Singapore AI governance implementation guide](https://vyrwork.com/blog/ai-governance-framework-singapore-enterprises)

## Important limitation

This evidence pack is a planning aid. It is not a compliance score, certification, audit, legal opinion, or guarantee. The prompts are a practical interpretation, not official IMDA wording. Accountable reviewers must assess the facts, sector obligations, risks, and current official guidance for the actual deployment.

Last source review: 12 August 2026.
