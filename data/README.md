# Data

Raw data files are **not committed** to this repo (kept out via
`.gitignore`) — only this documentation of where data came from and how it
was adapted.

## Data sourcing log

| Date | Dataset | Source | Why chosen |
|------|---------|--------|------------|
|25th September,2025| Churn for Bank Customers     | Kaggle    | It's the right size and complexity for a first serious project, has a direct AUM proxy field (Balance), and gives you published benchmarks to reverse-engineer against       | 

## Honesty note

Real wealth-management client data is proprietary and not publicly
available. Wherever this project uses a proxy dataset (e.g., a retail
banking or general customer dataset adapted to simulate wealth-management
style fields like AUM), that adaptation is documented here explicitly —
including exactly which fields were renamed/reinterpreted and why — rather
than left implicit.
