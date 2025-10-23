# Lesson 1: Statistical Modeling

## Overview

This lesson introduces the foundational concepts of statistical modeling, including random variables, probability distributions, and key limit theorems. Students will learn how to formulate statistical models, understand the Central Limit Theorem and Law of Large Numbers, and apply these concepts to real-world data analysis.

**Estimated time:** 3–4 hours self-study

## Learning Objectives

- Understand random variables and probability distributions
- Apply the Law of Large Numbers (LLN) and Central Limit Theorem (CLT)
- Formulate statistical models for data
- Visualize and interpret distributions
- Use Python to simulate and analyze random variables

## Folder Structure

```
lessons/01-statistical-modeling/
├── README.md                           # This file - lesson overview
├── material.md                         # Complete lesson content and theory
│
└── slides/                             # Presentation slides
    └── main.tex                        # Beamer presentation source
```

## Prerequisites

- Basic probability concepts (events, conditional probability)
- Python programming experience with numpy, scipy, matplotlib
- Familiarity with basic calculus and linear algebra

## How to Use This Lesson

### 1. Start with the Slides
Review the slides for a comprehensive overview of all concepts covered in this lesson.

### 2. Read the Theory
Study `material.md` for detailed explanations, mathematical derivations, and theoretical foundations.

### 3. Interactive Learning
Use Python and Jupyter notebooks to:
- Run code examples
- Visualize concepts
- Experiment with different distributions
- Simulate random variables

## Viewing the Materials

### Slides
```bash
cd lessons/01-statistical-modeling/slides
make                  # builds slides
tectonic main.tex     # compile slides (installed via cargo install tectonic)
```

### Theory
```bash
cat lessons/01-statistical-modeling/material.md
```

## Topics Covered

The lesson is organized into main sections:

### 1. Random Variables & Distributions
Understanding the foundation of statistical modeling:
- Discrete and continuous random variables
- Probability mass and density functions
- Common distributions (Normal, Binomial, Poisson, Exponential)
- Properties of distributions (mean, variance, skewness)

### 2. Law of Large Numbers (LLN)
Convergence of sample averages:
- Definition and intuition
- Weak and strong LLN
- Practical implications
- Simulation examples

### 3. Central Limit Theorem (CLT)
Distribution of sample means:
- Statement and proof sketch
- Conditions and assumptions
- Practical applications
- Limitations and when CLT fails

### 4. Statistical Models
Formulating models for data:
- Model specification
- Parametric vs. nonparametric models
- Likelihood and maximum likelihood estimation
- Model validation

## Key Concepts

**By the end of this lesson, you should be able to:**
- ✓ Define and work with random variables and distributions
- ✓ Understand and apply the Law of Large Numbers
- ✓ Apply the Central Limit Theorem to real problems
- ✓ Formulate appropriate statistical models
- ✓ Simulate random variables and verify theoretical results
- ✓ Visualize and interpret probability distributions

## Related Lessons

- **Lesson 2:** Statistical Learning - Estimation methods and model fitting
- **Lesson 3:** Estimator Properties - Bias, variance, and confidence intervals
- **Lesson 4:** Hypothesis Testing - Statistical inference and testing

---

For questions or issues, please refer to the course instructor or teaching assistants.

