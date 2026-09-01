# SettleIQ Architecture

## System Flow

```text
Synthetic Transaction Dataset
            │
            ▼
   Reconciliation Engine
            │
     ┌──────┴──────┐
     ▼             ▼
  Matched       Exceptions
  Records           │
                    ▼
           AI Investigation
                    │
             ┌──────┴──────┐
             ▼             ▼
      Auto-resolvable   Human Review
             │             │
             └──────┬──────┘
                    ▼
               Audit Trail
                    │
                    ▼
            Finance Dashboard
```
## Transaction Flow

```text
Order
  |
  v
Payment
  |
  v
Settlement
  |
  v
Bank
```
# Core Components
1. Transaction Dataset

Contains synthetic Orders, Payments, Settlements and Bank records.

2. Reconciliation Engine

Compares transaction records and identifies matching records and exceptions.

3. Exception Classification

Classifies discrepancies into amount mismatch, missing record, duplicate, timing mismatch and unresolved cases.

4. AI Investigation

Analyzes available transaction evidence and provides an explanation, confidence level and recommended action.

5. Human Review

Low-confidence and unresolved cases are escalated instead of being automatically resolved.

6. Audit Trail

Records reconciliation activity and investigation decisions for traceability.

7. Finance Dashboard

Provides an overview of reconciliation performance, exceptions and financial variance.
