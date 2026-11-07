# Formula 1 Cost Cap Impact Analysis: Regulatory Policy & Market Parity (2010–2025)

This repository contains our empirical analysis evaluating whether Formula 1’s 2021 financial cost cap ($145M baseline in 2021, scaled to $135M in 2023–2025) succeeded in leveling the competitive playing field across Constructors' Championship performances.

## Deliverables
* **Analysis Notebook:** [`B05-F1-Cost-Cap.ipynb`](B05-F1-Cost-Cap.ipynb)
* **Interactive Environment:** [PASTE YOUR EXISTING COLAB BADGE MARKDOWN HERE]

---

## Business Problem & Motivation
Prior to 2021, Formula 1 operated under an unregulated spending arms race where top constructors spent over $400M annually while smaller teams operated on ~$120M. In 2021, the FIA introduced a financial cost cap to promote competitive parity and financial sustainability. 

**Core Research Question:** *Did championship point distribution become more balanced after the 2021 cost cap implementation, and which constructors gained or lost market share?*

---

## Data & Methodology
* **Data Source:** Public [F1DB](https://github.com/f1db/f1db) release `v2026.15.1` (CC BY 4.0), retrieved programmatically via the GitHub Releases API with automated SHA-256 checksum verification.
* **Scope:** 16 complete seasons (2010–2025), comparing the **Pre-Cap Era (2010–2020, n = 11)** against the **Post-Cap Era (2021–2025, n = 5)** across 170 constructor-season records and 13 continuous team lineages.
* **Market-Share Proxies & Metrics:**
  * **Top-Two Concentration (CR2):** Combined season points share of the P1 and P2 constructors.
  * **Midfield Share (P4–P7):** Combined points share of constructors finishing 4th through 7th.
  * **Big Three Share:** Combined points share of Ferrari, Mercedes, and Red Bull.
  * **Effective Equal-Share Constructors ($1 / \text{HHI}$):** Inverse Herfindahl-Hirschman Index measuring overall field evenness.
* **Statistical Approach:** Relational schema validation, lineage chronology mapping, two-sided Welch’s two-sample t-tests (accounting for unequal variances and sample sizes), and leave-one-season-out sensitivity testing.

---

## Key Findings
1. **Top-Two Concentration (CR2) Saw a Modest, Non-Significant Dip:** 
   * Mean CR2 declined by **2.58 percentage points**, from **54.72%** (2010–2020) to **52.14%** (2021–2025). 
   * However, Welch’s two-sided t-test confirms this shift is not statistically significant ($t = -1.215, p = 0.245$), and annual volatility dropped from a standard deviation of 5.59 pp to 2.89 pp.
2. **Midfield (P4–P7) Gains Were Marginal:** 
   * The P4–P7 group's average points share rose slightly from **24.71% to 26.16%** (+1.45 pp), while the effective number of equal-share constructors across the entire grid barely moved from **4.83 to 4.92**.
3. **The "Big Three" Decline Hinges Entirely on 2025:** 
   * While the combined share of Ferrari, Mercedes, and Red Bull dipped from **67.51% to 65.82%** across the full 5-year post-cap window, sensitivity testing reveals that **excluding 2025 reverses the finding**—raising the 2021–2024 post-cap average to **69.8%**.
4. **Points Transferred Between Front-Runners Rather Than Lifting the Bottom Grid:** 
   * Comparing 2021–2025 against 2010–2020, only three lineages gained average points share: **McLaren (+7.48 pp)**, **Red Bull (+4.60 pp)**, and **Racing Bulls (+0.27 pp)**. Meanwhile, **Mercedes (-5.63 pp)**, **Williams (-2.70 pp)**, and **Alpine (-2.05 pp)** experienced the steepest declines.

---

## Strategic Recommendations for Stakeholders
* **For Regulators (FIA):** Require a multi-metric competitive balance review across a full technical regulatory cycle before altering financial cap thresholds, as points data cannot isolate the cost cap from the 2022 ground-effect aerodynamic reset and sliding-scale Aerodynamic Testing Restrictions (ATR).
* **For Midfield Constructors:** Benchmark multi-year development trajectories against break-out peers (such as McLaren) rather than relying on spending limits alone to close the performance gap.
* **For Commercial Sponsors:** Expand sponsorship shortlists to emerging upper-midfield contenders and structure contracts around performance/podium incentives, as non-Big Three podium opportunities expanded in recent seasons.

---

## Tech Stack
* **Languages & Libraries:** Python 3.13, pandas, NumPy, SciPy (`scipy.stats`), Matplotlib
* **Team B05:** Adrian Marcell, Ashwin Pillanda Ravindra, Jenniffer Hierro Cruz, and Saleha Hassan Alvi
