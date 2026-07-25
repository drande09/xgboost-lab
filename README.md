# Inside XGBoost: An Interactive Lab

An interactive, single-page teaching tool that walks business-school undergrads
through how XGBoost actually works — on real data, with real algebra, and no
calculus.

**Live site:** https://drande09.github.io/xgboost-lab/

## What's in the lab

1. **The data** — a 30-person sample of the canonical 1,338-person U.S.
   medical-cost dataset (age, sex, BMI, children, smoker, region → annual
   charges), plus the "one-number model" baseline and the idea of residuals.
2. **You be the algorithm** — students pick a feature and a cut-off, and the
   page walks through every line of the split math: residual sums, similarity
   scores `(Σr)² ÷ (n + λ)`, gain, and leaf corrections. A leaderboard tracks
   attempts against XGBoost's best possible split.
3. **XGBoost's turn** — the exact algorithm, driven by buttons: scan all
   candidate splits (ranked gain table), grow the depth-2 tree (live diagram
   with the math on every node), update predictions with learning rate η = 0.3,
   repeat for 6 boosting rounds. RMSE falls ~68%; charts show the residual
   cloud collapsing and two tracked customers converging on their true cost.
4. **Why it wins** — five takeaways (boosting on residuals, exhaustive search,
   λ/γ regularization, learning rate, automatic interaction discovery), each
   tied to numbers computed on the page.

## Notes

- Everything is computed live in the browser; this is real XGBoost math for
  squared-error regression (λ = 1, γ = 0, η = 0.3, depth 2, min 2 per leaf).
- No dependencies, no build step — one self-contained HTML file.
- Data: sample of the medical-cost dataset from Lantz, *Machine Learning with R*
  (via [stedy/Machine-Learning-with-R-datasets](https://github.com/stedy/Machine-Learning-with-R-datasets)),
  charges in $1,000s.
