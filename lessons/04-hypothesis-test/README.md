# Lesson 4: Hypothesis Testing

## Overview

This lesson introduces the classical hypothesis testing workflow used throughout applied statistics. Students will learn how to formulate hypotheses, choose appropriate test statistics, interpret p-values, link tests with confidence intervals, and assess power. The material emphasizes both conceptual intuition and practical implementation in Python, supported by rich visuals and real-world data examples.

**Estimated time:** 3–4 hours self-study

## Learning Objectives

- Formulate statistical hypotheses and identify Type I/II errors, significance level, and power
- Compute and interpret p-values correctly; connect confidence intervals to test decisions
- Apply z- and t-tests (one-sample, paired, and two-sample) and understand their assumptions
- Test proportions and categorical relationships via z-tests, chi-squared tests, and Fisher’s exact test
- Perform basic power analyses and sample size calculations for means and proportions
- Control multiplicity using Bonferroni/Holm (FWER) and Benjamini–Hochberg (FDR)
- Deploy nonparametric (Mann–Whitney, Wilcoxon) and permutation tests when model assumptions fail

## Folder Structure

```
lessons/04-hypothesis-test/
├── README.md                           # This file
├── material.md                         # Detailed theory and worked examples
│
├── exercises/                          # Practice problem sets (one per topic block)
│   ├── 01-foundations.md
│   ├── 02-z-t-tests.md
│   ├── 03-proportions-chi2.md
│   ├── 04-power-sample-size.md
│   ├── 05-multiple-testing.md
│   └── 06-nonparametric-permutation.md
│
├── notebooks/                          # Interactive Jupyter notebooks (theory + lab)
│   ├── 01-foundations.ipynb
│   ├── 02-z-t-tests.ipynb
│   ├── 03-proportions-chi2.ipynb
│   ├── 04-nonparametric-tests.ipynb
│   ├── 05-permutation-tests.ipynb
│   ├── 06-power-analysis.ipynb
│   ├── 07-multiple-testing.ipynb
│   ├── 08-practical-lab.ipynb
│   └── 08-practical-lab-solution.ipynb
│
└── slides/
    ├── main.tex                        # Beamer deck (Tectonic-compatible)
    ├── Makefile
    ├── make_figures.py
    ├── sections/
    │   ├── 01-foundations.tex
    │   ├── 02-z-t-tests.tex
    │   ├── 03-proportions-chi2.tex
    │   ├── 04-power-sample-size.tex
    │   ├── 05-multiple-testing.tex
    │   └── 06-nonparametric-permutation.tex
    └── figure_scripts/
        ├── __init__.py
        ├── config.py
        ├── type1_type2_regions.py
        ├── pvalue_under_null.py
        ├── ttest_visual.py
        ├── chi2_gof_visual.py
        ├── power_curves.py
        ├── multiple_testing_sim.py
        └── permutation_demo.py
```

## Prerequisites

- Probability foundations: random variables, CLT, LLN (Lesson 1)
- Point estimation and asymptotics (Lesson 2)
- Estimator properties and confidence intervals (Lesson 3)
- Python skills with NumPy, SciPy, pandas, matplotlib/seaborn, statsmodels

## How to Use This Lesson

1. **Slides:** Start with `slides/main.tex` (or compiled PDF) for a pedagogy-focused overview with visuals, intuition, and key takeaways.
2. **Theory:** Read `material.md` for deeper derivations, code examples, and extended commentary that complements the slides.
3. **Exercises:** Practice with the `exercises/` sheets; they align with slide sections and reinforce theory via pen-and-paper work and short computations.
4. **Notebooks:** Open `notebooks/` in Jupyter or VS Code to explore simulations, run statistical tests, and complete the practical lab.

## Viewing and Running the Materials

### Slides
```bash
cd lessons/04-hypothesis-test/slides
make                  # builds figures
tectonic main.tex     # compile slides (installed via cargo install tectonic)
```

### Jupyter Notebooks
```bash
jupyter notebook lessons/04-hypothesis-test/notebooks/
```

## Topics Covered

1. **Foundations:** Hypotheses, errors, p-values, likelihood ratios
2. **z/t Tests:** Mean comparisons (one-sample, paired, two-sample) and effect sizes
3. **Proportions & Chi-Squared:** A/B testing, contingency tables, Fisher's exact test
4. **Nonparametric Tests:** Mann-Whitney U, Wilcoxon signed-rank, robustness to outliers
5. **Permutation Tests:** Resampling methods, null distributions, exact p-values
6. **Power & Sample Size:** Power functions, MDE, statsmodels tooling
7. **Multiple Testing:** FWER vs FDR, Bonferroni/Holm, BH, simulation insights
8. **Practical Lab:** Comprehensive end-to-end hypothesis testing workflow

## Key Concepts

By the end of this lesson, you should be able to:

- ✓ Design and justify hypothesis tests for common parametric settings
- ✓ Interpret p-values responsibly and connect decisions to confidence intervals
- ✓ Evaluate power, estimate required sample sizes, and communicate MDE
- ✓ Apply categorical tests and understand their assumptions and limitations
- ✓ Mitigate false discoveries in multiple-testing regimes
- ✓ Choose robust alternatives (nonparametric/permutation) when conditions warrant

## Related Lessons

- Lesson 1: Statistical Modeling
- Lesson 2: Statistical Learning
- Lesson 3: Estimator Properties

---

Questions or suggestions? Reach out to the course team.

