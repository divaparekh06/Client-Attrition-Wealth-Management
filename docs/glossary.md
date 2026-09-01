# Glossary of Financial & Technical Terms

A living document. Every time I encounter a term I didn't already know —
while reading papers, articles, or documentation — it gets added here, in my
own words, along with the source I learned it from. This is both a study aid
and proof that the domain knowledge in this project was built up genuinely,
not assumed.

**Format for new entries:**
```
### Term
**Plain-English definition:**
**Why it matters for this project:**
**Source:** (paper / article / where I first saw it)
```

---

## Finance terms

### AUM (Assets Under Management)
**Plain-English definition:** The total market value of the investments a
wealth/asset management firm manages on behalf of its clients.
**Why it matters for this project:** It's the core "value" metric — losing a
client with high AUM matters far more to the firm than losing one with low
AUM. This is why the project ranks clients by *AUM at risk*, not just
attrition probability.
**Source:** BNY / wealth management industry context (see reasoning.md)

### Churn / Attrition
**Plain-English definition:** When a customer or client stops using a
company's services, or (in wealth management specifically) withdraws most or
all of their assets and moves them elsewhere.
**Why it matters for this project:** This is the core event we're predicting.
**Source:** General finance/business terminology

### CLV (Customer Lifetime Value)
**Plain-English definition:** The total revenue a business expects to earn
from a customer over the entire time they remain a customer.
**Why it matters for this project:** Related to AUM-at-risk — a client's
"value" to the firm isn't just their current balance, but their expected
future relationship value.
**Source:** General business/CRM terminology

### CAC (Customer Acquisition Cost)
**Plain-English definition:** How much it costs a business, on average, to
acquire one new customer (marketing, sales, onboarding costs).
**Why it matters for this project:** The "why retention matters" argument
rests on CAC being higher than retention cost — this is the economic
justification for the whole project.
**Source:** General business terminology

### Net Interest Margin (NIM)
**Plain-English definition:** A measure of how much profit a bank makes on
its lending activity, relative to its interest-earning assets.
**Why it matters for this project:** More relevant to traditional/retail
banking than wealth management — included here as background context since
it came up while comparing banking sub-domains.
**Source:** General banking terminology

### Neglect phase (of client attrition)
**Plain-English definition:** A period before a client formally leaves,
during which subtle behavioral changes occur (reduced engagement, fewer
communications) — attrition is rarely sudden.
**Why it matters for this project:** This is the theoretical basis for why
behavioral/engagement features (not just account balance) are useful
predictors — the model is trying to catch clients during this phase.
**Source:** Alpha FMC — "Offsetting Client Attrition: A Playbook for Wealth
Managers"

---

## ML / technical terms

### Class imbalance
**Plain-English definition:** When one outcome (e.g., "did not churn") is far
more common in the data than the other (e.g., "did churn"), which can cause
naive models to just predict the majority class every time.
**Why it matters for this project:** Attrition/churn is a textbook example of
this — most clients don't leave in any given period.
**Source:** General ML concept

### SHAP values
**Plain-English definition:** A technique for explaining individual
predictions from a machine learning model — showing which input features
pushed a specific prediction up or down, and by how much.
**Why it matters for this project:** Needed to explain *why* a specific
client was flagged as at-risk, which matters both for regulatory/business
trust and for the retention team to act on the prediction.
**Source:** General ML/explainability concept

### Cost-sensitive learning
**Plain-English definition:** Modeling approaches that explicitly account for
the fact that different types of prediction errors (false positives vs false
negatives) have different real-world costs, rather than treating all errors
equally.
**Why it matters for this project:** Missing a high-AUM at-risk client is far
costlier than a false alarm on a small account — this project needs to
reflect that asymmetry, not just optimize for accuracy.
**Source:** General ML concept

---

*(Keep adding here as you go — don't wait until the end of the project.)*
