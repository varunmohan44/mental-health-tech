# Employer Mental Health Support in Tech

An R/Quarto analysis of how employer mental health support varies with company size, whether workers know what support they have, and whether support is associated with treatment-seeking.

**[View the rendered report](https://YOUR_RPUBS_OR_GITHUB_PAGES_LINK)**

## Findings

- **Support is concentrated at large employers.** Welch's ANOVA on a 0–6 support index shows a significant difference across company sizes (p < 0.001). Holm-adjusted pairwise tests show that companies with more than 1,000 employees drive the difference.
- **Awareness is a separate problem.** Reported coverage rises from 12% at the smallest employers to 70% at the largest, yet 21–40% of workers in every size group don't know whether they have coverage.
- **Support is associated with treatment-seeking.** Workers who sought treatment scored 0.64 points higher on the support index (Welch t-test and permutation test, both p < 0.001). The association holds in a logistic regression controlling for family history, company size, and remote work (OR = 1.27 per point).

## Methods

Welch's one-way ANOVA, Kruskal-Wallis test, pairwise Welch t-tests with Holm correction, Welch two-sample t-test, permutation test, and logistic regression.

## Data

[OSMI Mental Health in Tech Survey (2014)](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey), filtered to the 1,031 respondents who work at tech companies. The raw file is included at `data/survey.csv`.

## Reproduce

```r
install.packages(c("dplyr", "tidyr", "ggplot2", "scales", "broom", "knitr", "rmarkdown"))
```

```bash
quarto render mental_health_tech.qmd
```

## Limitations

The data are observational and cross-sectional, from a self-selected 2014 sample. The support index reflects workers' perceptions, not employers' actual policies. See the report for details.
