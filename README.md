# Predicting Client Attrition & Assets-at-Risk in Wealth & Investment Management

## 1. What is this project?

This project predicts which clients of a wealth/investment management firm are
likely to leave (attrition) or significantly reduce their assets with the firm,
and quantifies **how much value is at risk** if they do — measured in terms of
Assets Under Management (AUM), not just headcount.

It goes one step further than a standard churn classifier by adding a
**decision layer**: given a limited relationship-management budget (advisor
time, retention offers), which clients should the firm prioritize retaining,
based on both *likelihood of leaving* and *AUM at risk*?

> Status: 🚧 In progress — this README will be updated as the project evolves.

## 2. Why this project? (the reasoning)

- **Real, expensive, ongoing business problem.** Acquiring a new client in
  financial services costs far more than retaining an existing one, and
  wealth managers can lose meaningful revenue (both directly, and through lost
  referrals) when a client leaves. See `docs/reasoning.md` for the full
  breakdown with sources.
- **Technically rich enough to defend in depth**, not just a single
  classifier: it involves class imbalance, cost-sensitive/asymmetric error
  handling, ranking clients by expected value at risk (probability × AUM),
  and interpretability (SHAP) so the "why" behind each prediction is
  explainable — a real requirement in regulated financial services.
- **Domain-aligned with target employers** (custody/asset-servicing banks,
  Big 4 advisory, universal banks with wealth divisions) — the vocabulary
  (AUM, assets-at-risk, relationship value) matches how these teams actually
  talk about the problem.
- **Extensible** — designed so it can be taken further next semester (e.g.
  sequence models on transaction history, NLP on advisor notes, or
  reinforcement learning for optimal intervention policy).

Full detailed reasoning, including the honest limitations (e.g. proxy data
use, since real wealth-management client data is proprietary), lives in
[`docs/reasoning.md`](docs/reasoning.md).

## 3. Repo structure

```
├── README.md                 <- you are here
├── docs/
│   ├── reasoning.md           <- full "why this project" writeup
│   ├── glossary.md             <- finance terms & concepts, explained as I learn them
│   └── decision-log/           <- dated log of every real decision made, and why
├── papers/                    <- summaries of papers I reverse-engineered, in my own words
├── notebooks/                 <- exploratory & modeling notebooks
├── src/                       <- reusable code (data prep, features, models)
├── data/                      <- data sourcing notes (raw data not committed)
└── reports/                   <- final write-ups / memo-style business reports
```

## 4. How to read this repo

If you're a reviewer/interviewer skimming this: start with `docs/reasoning.md`
for the "why," then `papers/` to see how the approach was grounded in
existing research, then `docs/decision-log/` to see the actual judgment calls
made along the way (this is the part most student projects skip).

## 5. Author's note on AI tool usage

This project was built with the help of AI tools (Claude) used as a **tutor
and sounding board** — for explaining concepts, critiquing decisions I made
myself, and debugging code I wrote — not as a generator of the analysis,
code, or conclusions. The decision log exists specifically to make this
transparent and to demonstrate that the reasoning is my own.
