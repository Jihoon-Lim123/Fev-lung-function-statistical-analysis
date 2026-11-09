# Smoking and Lung Function in Children — Statistical Analysis

**STAT 420: Theory and Methods of Statistics | University of Maryland**  
**Team project:** Anand Vinod, Alan Jiang, and Jihoon Lim

## Overview

We examined the association between smoking status and forced expiratory volume (FEV) in an observational dataset of children using R. The analysis combines a two-sample hypothesis test, exploratory assessment of potential confounding, and multiple linear regression with diagnostic checks.

## Data

`fev.txt` contains **654 observations** and seven columns: `seqnbr`, `subjid`, `age`, `fev`, `height`, `sex`, and `smoke`. In the supplied dataset, `smoke = 1` denotes smokers and `smoke = 2` denotes non-smokers. There are **65 smokers and 589 non-smokers**. This is a teaching dataset; do not treat the sample as representative of all children.

## Methods

1. **One-sided two-sample Welch t-test** comparing mean FEV in smokers versus non-smokers.
2. **Exploratory analysis** of age, height, and sex by smoking status using summary statistics and plots.
3. **Multiple linear regression** fitting `FEV ~ smoking + height + sex`, with 95% confidence intervals and residual diagnostics.

## Key findings

- Mean FEV: **3.277** among smokers versus **2.566** among non-smokers. Smokers in this sample were also older and taller on average, illustrating confounding in a raw group comparison.
- In the regression adjusted for height and sex, the estimated smoker coefficient is **+0.034 L** (95% CI **−0.081 to +0.149**, **p = 0.560**).
- The adjusted association is **not statistically significant**. The observed data do not establish whether smoking causally increases or decreases lung function.
- The height coefficient is approximately **+0.130 L per inch**, holding smoking status and sex fixed.

## Reproduce the analysis

1. Install [R](https://cran.r-project.org/) and [RStudio](https://posit.co/download/rstudio-desktop/), if needed.
2. Install packages: `install.packages(c("rmarkdown", "ggplot2", "cowplot", "knitr"))`.
3. Open `FEV_Lung_Function_Analysis.Rmd` in RStudio, keeping `fev.txt` in the same working directory.
4. Click **Knit** to render the HTML report, or run `rmarkdown::render("FEV_Lung_Function_Analysis.Rmd")` from this directory.

## Limitations and notes

- This is an observational analysis; differences in age, height, and other unmeasured variables complicate causal interpretation.
- The sample includes relatively few smokers. Residual diagnostics should be considered before drawing inferential conclusions.
- The supplied class report was **minimally corrected** for internal consistency: the adjusted smoking coefficient is positive, not negative, and the 95% confidence interval lower bound is approximately −0.081. The core analysis code and team authorship were retained.
- This repository should be published only if the course material, source dataset, and teammates' work may be shared publicly. Individual contributions should be clarified before presenting the project as independent work.