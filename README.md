# SettleIQ

### AI Finance Controller for Payment Settlement Reconciliation

SettleIQ is an AI-powered finance controller that reconciles merchant transactions across the complete payment settlement chain:

**Order → Payment → Settlement → Bank**

It identifies matched transactions, detects discrepancies, investigates exceptions using transaction-level evidence, and routes uncertain cases for human review.

## 🚀 Live Demo

**[Launch SettleIQ](https://settle-iq-flow.base44.app/)**

---

## 🎯 Problem

Payment operations often require finance teams to reconcile the same transaction across multiple systems.

A single transaction can appear across:

- Orders
- Payments
- Settlements
- Bank records

When these records disagree, the real challenge is not just finding the mismatch. The finance team needs to understand:

**What happened? Why did it happen? Can it be safely resolved? Does a human need to intervene?**

SettleIQ is designed to close this reconciliation loop.

---

## 💡 Solution

SettleIQ traces every transaction through:

**Order → Payment → Settlement → Bank**

The system then:

1. Compares expected and observed financial values.
2. Detects matches and discrepancies.
3. Classifies exceptions.
4. Assigns a confidence level.
5. Investigates discrepancies using transaction evidence.
6. Provides a recommended next action.
7. Escalates uncertain cases for human review.
8. Records reconciliation activity in an audit trail.

The system is intentionally designed not to force an explanation when the available evidence is insufficient.

---

## 📊 Batch Evaluation

SettleIQ was evaluated on a synthetic batch of **100 transaction records**.

| Metric | Result |
|---|---:|
| Batch size | 100 |
| Records processed | 100 |
| Reconciled | 78 |
| Match rate | 78.0% |
| Exceptions | 22 |
| Unresolved cases | 3 |
| Total amount processed | ₹10,09,506 |
| Total reconciled | ₹9,40,961 |
| Unresolved variance | ₹3,110 |
| Audit events | 252 |

### Exception Breakdown

| Exception Type | Count |
|---|---:|
| Matched | 78 |
| Amount mismatch | 7 |
| Missing record | 4 |
| Duplicate | 3 |
| Timing mismatch | 5 |
| Unresolved | 3 |

The system does not force every transaction into a successful resolution.

Three cases remain explicitly unresolved and are routed for human review.

> **Note:** The 78.0% figure represents the reconciliation match rate on this synthetic evaluation batch. It is not presented as a general-purpose AI accuracy score.

---

## 🧠 AI Finance Analyst

SettleIQ includes a finance-specific AI analyst grounded in the reconciliation dataset.

Instead of acting as a generic chatbot, it answers questions using the actual transaction records available in the system.

Example questions:

- How many payments are missing settlement records?
- Which transactions have the largest variance?
- What are the most common exception types?
- Which transactions require human review?
- Why was this transaction not reconciled?

---

## 🔎 Settlement Detective

The Settlement Detective allows a finance user to investigate an individual transaction across:

**Order → Payment → Settlement → Bank**

Each investigation can present:

- What happened
- Transaction evidence
- Likely cause
- AI confidence
- Whether human review is required
- Recommended action

This turns reconciliation from simply detecting a mismatch into investigating why the mismatch occurred.

---

## ⚠️ Exception Management

SettleIQ categorizes problematic transactions into:

- Amount mismatch
- Missing record
- Duplicate
- Timing mismatch
- Unresolved

Each exception includes relevant information such as:

- Variance
- Priority
- AI confidence
- Recommended action
- Review status

This gives finance teams a focused exception queue instead of requiring them to manually inspect every transaction.

---

## 🧾 Audit Trail

SettleIQ maintains a traceable audit trail of reconciliation activity.

The current prototype records **252 audit events**, including:

- Record imported
- Match detected
- Exception detected
- AI investigation performed
- Recommendation generated
- Human review required

This provides visibility into how reconciliation decisions were reached.

---

## 🏗️ Architecture

```text
                 Synthetic Transaction Data
                           │
                           ▼
                Transaction Processing
                           │
                           ▼
                 Reconciliation Engine
                           │
                 ┌─────────┴─────────┐
                 ▼                   ▼
              Matched            Exception
                 │                   │
                 │                   ▼
                 │             AI Investigation
                 │                   │
                 │          ┌────────┴────────┐
                 │          ▼                 ▼
                 │     Resolvable        Unresolved
                 │          │                 │
                 │          ▼                 ▼
                 │   Recommendation      Human Review
                 │
                 └────────────┬────────────┘
                              ▼
                         Audit Trail
                              │
                              ▼
                      Finance Dashboard
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

**[Launch the Live Demo →](https://settle-iq-flow.base44.app/)**

**5-Minute Demo:** Coming soon

**Architecture:** See the architecture section above.

---

### Built with a focus on reliability, explainability and human oversight.
