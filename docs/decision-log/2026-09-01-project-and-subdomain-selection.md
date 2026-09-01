# Project and subdomain selection

**Date:** 2026-09-01

**Context:** Needed to choose a finance-domain ML project for my portfolio,
targeting data analyst roles at firms like BNY, Big 4, Goldman Sachs, and
Barclays. Started with close to no finance domain knowledge and had to
narrow down from "finance" broadly to a specific, defensible problem.

**Options considered:**
- Credit risk / loan default prediction
- Credit card fraud detection
- Stock price direction prediction
- Corporate bankruptcy / default prediction
- Customer churn/retention in retail banking
- Client attrition / assets-at-risk in wealth & investment management

**Decision:** Client attrition and assets-at-risk prediction, framed for
wealth & investment management (not generic retail banking).

**Reasoning:**
- Strong ROI/business narrative, which is the type of framing I find most
  engaging to work with.
- Technically rich (class imbalance, cost-sensitive evaluation, ranking
  under budget constraints, interpretability) — enough depth to defend
  properly in an interview.
- Reframing it toward wealth/investment management (rather than plain retail
  banking churn) aligns the vocabulary and business context with the actual
  business lines at my target employers (e.g., BNY's core asset-servicing
  and wealth management business).
- Public data is a known limitation for this exact framing — real
  wealth-management client data is proprietary — so a proxy dataset will be
  used and disclosed honestly (see `docs/reasoning.md`).

**AI tool usage:** Used Claude to (a) explain differences between finance
sub-domains I didn't understand, (b) pull current statistics/context on
client attrition economics in wealth management, and (c) stress-test my
reasoning for why this project fits my target roles. Claude did not choose
the project for me — I made the final call after comparing the options
Claude helped me understand.

**Outcome / what I'd revisit:** To be filled in once the project is further
along — particularly whether the proxy dataset holds up well enough to
support the wealth-management framing, or whether I need to adjust scope.
