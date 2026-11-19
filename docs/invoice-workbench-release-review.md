---
title: Invoice Match Workbench release review
description: An exercised release decision for a synthetic invoice review, with the input correction, approval boundary and replay results.
---

# Invoice Match Workbench release review

**20 November 2026 · v0.1.0 · Decision: suitable for an offline demonstration with synthetic records.** The review covered the tagged Python application, three CSV inputs, SQLite decision history, HTML report and JSON draft. It grants no organizational approval for production accounting. The implementation is deterministic. It uses no model, bank credentials, connector or external accounting service. [Tagged source and downloads](https://github.com/dextee/invoice-match-workbench/releases/tag/v0.1.0)

## Why one invoice stayed out of the draft

INV-1002 bills twelve desk trays at S$18.50 each. Two receipts document six and four trays. The quantities leave two unreceived and S$222 held. A high-confidence extraction or a price approval would leave that quantity discrepancy unresolved. The reviewer can follow each value back to the original row. [Invoice](https://github.com/dextee/invoice-match-workbench/blob/v0.1.0/examples/demo/invoices.csv#L4) · [Order](https://github.com/dextee/invoice-match-workbench/blob/v0.1.0/examples/demo/orders.csv#L4) · [Receipts](https://github.com/dextee/invoice-match-workbench/blob/v0.1.0/examples/demo/receipts.csv#L4-L5)

## Release checks and observed results

These observations came from an independent checkout of release commit `35c00be4f74d8a774c94ca871c205ba96fe10c70`. The reviewer used a synthetic label for CLI actions. A person at a client organization has not signed this example.

| Check | Expected boundary | Observed |
|---|---|---|
| Import all four invoices | Only a matched invoice enters the initial draft | S$587 submitted. INV-1001 alone entered the S$215 draft. Three invoices totaling S$372 stayed outside. |
| Try to approve the quantity shortage as a price difference | The attempt must fail without changing eligible invoices | CLI returned exit 1. Re-export still produced S$215. |
| Accept the price-only exception on INV-1003, then reopen it | Approval and reversal must affect only that invoice | Draft changed from S$215 to S$275, then returned to S$215. |
| Correct the failed receipt check in a copy of the inputs | Sufficient receipt evidence must clear the hold in the new batch | Adding a synthetic receipt for the two remaining units made INV-1002 eligible. The new draft contained two invoices totaling S$437. |
| Reimport the corrected input and re-export the original | A repeat must preserve the result and keep the earlier snapshot independent | Corrected input again produced S$437. Exporting the original still produced S$215. |

To reproduce the correction, copy the three files in `examples/demo` into a new directory. Append the row below to the copy of `receipts.csv`. Run `python workbench.py import --input path/to/copy` twice, then `python workbench.py export` against the original sample workspace. This changes only synthetic source evidence. [Workbench commands](https://github.com/dextee/invoice-match-workbench/blob/v0.1.0/README.md)

```csv
GR-QA/1,PO-52/1,2
```

## Who can act and what can be recovered

The demo operator owns the local workspace. The program validates matching rules, requires a reviewer label and reason for decisions, and records them against the batch. A price exception has a deliberately narrow override. Changes to source files create a separate batch. Reopening an approval retains its earlier decision in the local database. Re-export regenerates report files. [Review and export implementation](https://github.com/dextee/invoice-match-workbench/blob/v0.1.0/workbench.py) · [Regression tests](https://github.com/dextee/invoice-match-workbench/blob/v0.1.0/tests/test_workbench.py)

## Conditions for using the example

Use synthetic inputs and treat the outputs as drafts. Anyone with write access to the local workspace can supply a reviewer label or alter the database. This design cannot establish an authenticated approver or tamper-resistant audit history. A proposed deployment with real records needs a named finance owner, authenticated roles, retention and recovery tests, and a separately authorized posting boundary. Re-open this review if the rules, data sensitivity, approval model or integrations change. An operator can stop the local CLI and continue from the original documents.

[Blank release-review template](ai-agent-release-review-template.md) · [Singapore governance checklist](https://github.com/dextee/singapore-ai-governance-checklist/blob/main/CHECKLIST.md)
