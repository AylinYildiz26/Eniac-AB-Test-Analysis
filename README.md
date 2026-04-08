# 🧪 Eniac — A/B Test Analysis

> *Does changing a button really make a difference?*  
> A statistical analysis of Eniac's homepage button experiment to determine which variant drives the highest user engagement.

---

## 🧰 Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557c?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white"/>
</p>

---

## 📌 About the Project

Eniac is a Spanish e-commerce company specialising in Apple products and accessories. The homepage featured a white **"SHOP NOW"** button attracting only ~2% of visitors — the UX team proposed three new variants to improve click-through rate.

**The experiment ran from November 2–16, 2021** across four button versions:

| Version | Button | Color |
|---------|--------|-------|
| A | SHOP NOW | White (control) |
| B | SHOP NOW | Red |
| C | SEE DEALS | White |
| D | SEE DEALS | Red |

---

## 📁 Project Structure

| File | Description |
|------|-------------|
| `ENIAC_AB_Test_Analysis_F.ipynb` | Full analysis — data quality check, contingency table, chi-square test, post-hoc pairwise tests, multi-metric evaluation |
| `eniac_a.csv` | Tracking data for Version A |
| `eniac_b.csv` | Tracking data for Version B |
| `eniac_c.csv` | Tracking data for Version C |
| `eniac_d.csv` | Tracking data for Version D |

---

## 🔍 What We Analysed

**Data Quality Check**  
Verified integrity of all four CSV files before analysis.  
Found that `eniac_c.csv` was a duplicate of Version A — no SEE DEALS button present, identical click data across all 57 rows. Version C values were sourced from course lesson materials and clearly documented.

**Contingency Table & CTR**  
Built a click / no-click contingency table for all four versions.  
Calculated click-through rate per version from total visitor counts.

**Chi-Square Test — Overall**  
Tested whether observed CTR differences across all four versions were statistically significant.  
Result: χ² = 224.02, p ≈ 0 → H₀ rejected.

**Post-Hoc Pairwise Tests (Bonferroni Correction)**  
With 6 pairwise comparisons, adjusted alpha to 0.0083.  
Identified which specific version pairs differed significantly.

**Multi-Metric Evaluation**  
Since A vs C showed no significant CTR difference, analysed drop-off rate and homepage-return rate to determine the overall winner.  
Applied a weighted scoring system (CTR 50% · Drop-off 25% · Homepage-return 25%).

---

## 💡 Key Findings

- **Version C** had the highest CTR at **2.12%** — marginally above Version A at **2.02%**
- **A vs C** was the only non-significant pairwise result (p = 0.46) — statistically tied on CTR
- **Red button (B)** reduced clicks by ~43% vs control — colour change clearly hurt performance
- **SEE DEALS red (D)** reduced clicks by ~62% — worst performing variant
- Drop-off rate: **Version A 62% vs Version C 71%** — A users were more likely to complete a purchase
- Weighted score ranking: **A (0.74) · C (0.70) · B (0.64) · D (0.01)**

---

## 🏆 Winner: Version A — White "SHOP NOW"

Although Version C had a marginally higher CTR, Version A wins on the most critical downstream metric: **drop-off rate**.  
A drop-off rate of 62% vs 71% means users who click Version A are significantly more likely to complete a purchase. A higher CTR is meaningless if users abandon immediately after clicking.

---

## 📊 Recommendations

1. **Retain the original white "SHOP NOW" button** — both new variants underperformed
2. **Do not use red buttons** — significantly hurt engagement across both text variants
3. **Run a follow-up experiment** testing destination-specific text such as *"Shop iPhones"* to address the user research finding that clarity of destination is the main driver of click decisions

---

## 🚀 How to Run

1. Clone or download this repository
2. Open [Google Colab](https://colab.research.google.com/)
3. Upload `ENIAC_AB_Test_Analysis_F.ipynb`
4. Ensure the four CSV files are accessible via Google Drive
5. Update the file paths in the notebook to match your Drive structure
6. **Runtime → Run all**

> ⚠️ **Note:** The CSV files contain aggregated element-level click data — not individual visitor sessions. Total visitor counts used in the analysis are sourced from course lesson materials and clearly documented in the notebook.

---

## 🤝 Contact

**Aylin Yildiz**

<p align="left">
  <a href="#">
    <img src="https://user-images.githubusercontent.com/74038190/235294012-0a55e343-37ad-4b0f-924f-c8431d9d2483.gif" alt="LinkedIn" width="50"/>
  </a>
  &nbsp;
  <a href="https://github.com/AylinYildiz26">
    <img src="https://user-images.githubusercontent.com/74038190/212257468-1e9a91f1-b626-4baa-b15d-5c385dfa7ed2.gif" alt="GitHub" width="45"/>
  </a>
</p>
