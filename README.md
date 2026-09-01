# SettleIQ

### AI Finance Controller for Payment Settlement Reconciliation

SettleIQ is an AI-powered finance controller that automatically reconciles merchant transactions across Orders, Payments, Settlements and Bank records.

It identifies mismatches, explains discrepancies using available transaction evidence, prioritizes exceptions for human review, and maintains an auditable record of reconciliation decisions.

🔗 **Live Demo:** https://settle-iq-flow.base44.app/

---

## 🎯 Problem

Payment businesses process large volumes of transactions across multiple systems.

A single transaction can pass through:

**Order → Payment → Settlement → Bank**

When these records do not match, finance teams need to determine:

- What happened?
- Where did the discrepancy occur?
- How much money is affected?
- Can the issue be resolved automatically?
- Does a human need to investigate?

Traditional reconciliation workflows can require significant manual investigation.

---

## 💡 Solution

SettleIQ provides an AI-assisted reconciliation workflow that:

1. Processes a batch of transaction records.
2. Matches records across the payment settlement chain.
3. Identifies exceptions and discrepancies.
4. Investigates individual transactions using available evidence.
5. Explains the likely cause of an exception.
6. Assigns confidence to the investigation.
7. Recommends the next action.
8. Escalates uncertain cases to human reviewers.
9. Records reconciliation activity in an audit trail.

The system is designed to be **explainable, bounded and human-supervised**.

---

## 📊 Batch Evaluation

SettleIQ was evaluated on a synthetic batch of **100 transaction records**.

| Metric | Result |
|---|---:|
| Batch Size | 100 |
| Records Processed | 100 |
| Matched | 78 |
| Match Rate | 78.0% |
| Exceptions | 22 |
| Unresolved Cases | 3 |
| Total Amount Processed | ₹10,09,506 |
| Total Reconciled | ₹9,40,961 |
| Unresolved Variance | ₹3,110 |
| Audit Events | 252 |

### Exception Breakdown

| Status | Count |
|---|---:|
| Matched | 78 |
| Amount Mismatch | 7 |
| Missing Record | 4 |
| Duplicate | 3 |
| Timing Mismatch | 5 |
| Unresolved | 3 |

**Important:** The 78.0% figure is the reconciliation match rate for this synthetic evaluation batch. It is not presented as general-purpose AI accuracy.

---

## 🤖 AI Finance Analyst

SettleIQ includes a grounded AI Finance Analyst that answers questions using the reconciliation dataset.

Example questions include:

- How many payments are missing settlement records?
- Which transactions have amount mismatches?
- What are the highest-value exceptions?
- Which transactions require human review?
- What happened to a specific transaction?

The analyst is designed to reason from available transaction evidence rather than provide generic financial answers.

---

## 🔎 Settlement Detective

Settlement Detective provides transaction-level investigation.

For each transaction, SettleIQ can trace:

**Order → Payment → Settlement → Bank**

The investigation provides:

- What happened
- Supporting evidence
- Likely cause
- Confidence level
- Whether human review is required
- Recommended next action

This makes the reconciliation process easier to understand and audit.

---

## 🚨 Exception Management

SettleIQ categorizes reconciliation exceptions including:

- Amount Mismatch
- Missing Record
- Duplicate
- Timing Mismatch
- Unresolved

Each exception can include:

- Financial variance
- Priority
- AI confidence
- Recommended action
- Review status

Low-confidence cases are deliberately routed for human investigation.

---

## 🧾 Audit Trail

SettleIQ maintains a traceable record of reconciliation activity.

The audit trail records events such as:

- Transaction imported
- Transaction matched
- Exception detected
- AI investigation performed
- Recommendation generated
- Human review required

The prototype contains **252 audit events** for the evaluation batch.

---

## 🏗️ Architecture

```text
                    ┌───────────────────────┐
                    │   Synthetic Dataset   │
                    │     100 Records       │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Reconciliation Engine │
                    │                       │
                    │ Order → Payment →     │
                    │ Settlement → Bank     │
                    └───────────┬───────────┘
                                │
                    ┌───────────┴───────────┐
                    ▼                       ▼
          ┌─────────────────┐     ┌─────────────────┐
          │ Matched Records │     │    Exceptions   │
          │                 │     │                 │
          │ 78 Records      │     │ 22 Records      │
          └────────┬────────┘     └────────┬────────┘
                   │                       │
                   │                       ▼
                   │             ┌──────────────────┐
                   │             │ AI Investigation │
                   │             └────────┬─────────┘
                   │                      │
                   │              ┌───────┴────────┐
                   │              ▼                ▼
                   │       Auto-resolvable    Human Review
                   │
                   └──────────────┬─────────────────┘
                                  ▼
                         ┌──────────────────┐
                         │   Audit Trail    │
                         └──────────────────┘
                                  │
                                  ▼
                         ┌──────────────────┐
                         │ Finance Dashboard│
                         └──────────────────┘
```
---

## 🛡️ Safety & Reliability

### Human-in-the-loop

Low-confidence and unresolved cases are explicitly escalated for human review.

### Evidence-based investigation

AI investigations are grounded in transaction evidence available to the system.

### Honest exceptions

The system reports unresolved cases instead of pretending that every transaction can be confidently resolved.

### No automatic movement of money

Recommendations are advisory only.

**No money is moved by the prototype.**

### Synthetic data

The prototype uses synthetic transaction records and does not process real customer financial information.

---

## 🖥️ Product Modules

### Finance Dashboard

Provides an overview of reconciliation health, processed records, exceptions and financial variance.

### Reconciliation Workspace

Compares transactions across Orders, Payments, Settlements and Bank records.

### Exception Queue

Provides a focused view of transactions requiring investigation.

### Settlement Detective

Traces individual transactions through the complete settlement chain.

### AI Finance Analyst

Answers finance questions using the reconciliation dataset.

### Batch Evaluation

Shows measured batch performance, match rate and exception distribution.

### Audit Trail

Provides a traceable record of reconciliation activity.

---

## ⚙️ Technology

- React
- TypeScript
- AI-powered investigation
- Structured synthetic transaction dataset
- Reconciliation workflow
- Exception classification
- Audit logging
- Responsive web interface

---

## 📈 Why SettleIQ?

The difficult part of financial reconciliation is not only finding that two records do not match.

The real operational questions are:

> **What happened? Why did it happen? Should someone intervene?**

SettleIQ combines reconciliation, evidence-based investigation, exception routing and auditability into one focused payment settlement workflow.

The project deliberately prioritizes reliable handling of uncertainty rather than forcing every transaction into a successful outcome.

---

## ⚠️ Limitations

SettleIQ is a buildathon prototype using synthetic data.

It does not:

- Move real money
- Connect to production banking systems
- Perform real settlements
- Replace production accounting systems
- Make unsupervised financial decisions

The evaluation results shown in the prototype are based on the synthetic batch used for this project.

---

## 🔭 Future Work

Potential extensions include:

- Payment gateway integrations
- Bank statement ingestion
- ERP and accounting system integrations
- Continuous reconciliation
- Historical anomaly detection
- Evaluation against larger labeled reconciliation datasets
- Role-based finance approvals
- Bounded automated exception workflows
- Production monitoring and model evaluation

---

## 🏆 Razorpay AI Buildathon

SettleIQ was built for the **AI Finance Controller** track.

The project focuses on closing one finance-operations loop across a 100-record synthetic batch while providing measurable reconciliation results, explainable investigation, human escalation and an honest unresolved exception list.

---

## 🚀 Try SettleIQ

### Live Demo

**https://settle-iq-flow.base44.app/**

### 5-Minute Demo

https://drive.google.com/file/d/1iLRopPHJrQHgZN-WCTnTDYEJBsTd9THH/view?usp=sharing

### Architecture

See the architecture section above.

---

### Built with a focus on reliability, explainability and human oversight.
