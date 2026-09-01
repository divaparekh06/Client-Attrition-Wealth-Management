# Why This Project? — Full Reasoning

## The problem, in plain terms

Wealth and investment management firms make money by managing clients' assets
(charging fees based on Assets Under Management, or AUM). When a client
leaves, or moves a large share of their assets elsewhere, the firm doesn't
just lose "a customer" — it loses ongoing fee revenue proportional to how
much that client had invested, and often loses referral relationships too.

This project predicts **who** is at risk of leaving, **how much value** is at
stake if they do, and **who to prioritize** for retention effort given that
relationship managers have limited time and budget.

## Why this problem matters (the business case)

- Acquiring a new client is significantly more expensive than retaining an
  existing one — this is a well-established pattern across financial
  services generally, not unique to wealth management.
- Industry analysis of wealth managers specifically has estimated that
  proactively addressing client attrition can protect several percentage
  points of revenue (through retained clients) and unlock further revenue
  upside (through better-served, more satisfied clients) — together
  representing a meaningful share of total revenue potential for a firm that
  tackles this well. *(Source: Alpha FMC wealth management attrition
  playbook — see `papers/` folder for full summary.)*
- Because AUM varies enormously between clients, a firm cannot treat all
  attrition risk equally — losing one large client can matter more than
  losing dozens of small ones. This is why the project explicitly models
  **value at risk**, not just a binary "will they leave" label.

## Why this problem is a strong technical choice for a portfolio project

1. **Class imbalance** — in any given period, most clients do not leave.
   This requires deliberate technique (not just default classifier settings)
   to avoid a model that trivially predicts "no one leaves."
2. **Asymmetric costs** — missing a high-AUM at-risk client is far more
   costly than a false alarm on a small account. This pushes the project
   beyond standard accuracy/F1 thinking into cost-sensitive evaluation.
3. **Ranking under a budget constraint** — the real business decision isn't
   "who will leave," it's "given limited retention resources, who do we
   prioritize." This requires combining a probability estimate with a value
   estimate (expected value = P(attrition) × AUM at risk), which is a more
   sophisticated framing than a typical classification project.
4. **Interpretability** — financial services is a regulated industry;
   being able to explain *why* a client was flagged (via SHAP or similar) is
   both a technical best practice and something real firms genuinely need.

## Why this fits my target employers/roles

Custody and asset-servicing banks, universal banks with wealth management
divisions, and Big 4 advisory practices that serve asset/wealth managers all
work with exactly this kind of problem — the vocabulary (AUM, assets-at-risk,
relationship value, client segmentation) matches how these teams actually
describe their work.

## Honest limitations (stated upfront, not discovered later)

- **Data access**: real wealth-management client data is proprietary and
  sensitive; no firm publishes it. This project uses a **proxy dataset**
  (documented in `data/README.md`) adapted to simulate wealth-management-style
  features (e.g., treating account balance as a stand-in for AUM). This
  limitation is disclosed openly rather than implied away.
- **Behavioral features** (e.g., advisor communication frequency, sentiment
  of client interactions) that real wealth managers use are often not present
  in public datasets — where this is the case, it is noted explicitly rather
  than silently omitted.

## What "success" looks like for this project

Not just a high accuracy score — but a defensible, explainable pipeline that:
- Correctly identifies a majority of high-value at-risk clients (recall on
  the highest AUM-at-risk segment, not just overall accuracy)
- Produces a ranked, budget-constrained retention priority list
- Can explain, per client, *why* they were flagged
- Is documented honestly, including where the data is a proxy and why
