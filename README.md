# Data-Driven Abalone Harvesting Strategy using R

## Project Overview
This project conducts a comprehensive analysis of abalone data to develop a data-driven harvesting strategy. The primary goal is to determine an optimal volume-based cutoff for harvesting that maximizes the yield of adult abalones while minimizing the harvest of infants, ensuring the long-term sustainability of the population. The analysis uses various statistical modeling and decision science techniques in R to evaluate the trade-offs between economic yield and biological conservation.

# Key Questions Addressed
How do physical characteristics like shuck-to-volume ratio differ across various age classes and sexes?

Can the assumptions for parametric testing be met, and what data transformations are necessary?

What factors (volume, age class, type) are significant predictors of abalone meat yield (shuck weight)?

How can we define and compare different harvesting rules based on volume cutoffs?

What is the optimal cutoff that balances harvesting adults and protecting infants?

## Methodology & Skills Demonstrated

# Data Transformation & Exploration:

Used log10() transformation to normalize the RATIO variable, correcting for skewness and achieving better conformance to normality.

Performed exploratory data analysis using histograms, Q-Q plots, and boxplots (ggplot2) to visualize distributions and check model assumptions.

Assessed homogeneity of variances using bartlett.test().

# Analysis of Variance (ANOVA):

Fitted ANOVA models using aov() to analyze the effects of CLASS (age) and SEX on the log-transformed ratio (L_RATIO).

Evaluated the significance of interaction terms (CLASS:SEX) to understand the combined effects of the factors.

# Multiple Comparisons & Post-Hoc Testing:

Applied TukeyHSD() to conduct pairwise comparisons between different age and sex classes, identifying specific groups that differed significantly.

# Multiple Linear Regression:

Developed a multiple linear regression model (lm()) to predict log-transformed shuck weight (L_SHUCK).

Interpreted model coefficients to understand the influence of predictors like log-volume (L_VOLUME), CLASS, and TYPE (Infant/Adult).

Assessed overall model fit using R-squared and F-statistics.

# Model Diagnostics:

Conducted a thorough residual analysis by plotting residuals against fitted values to check for non-linearity and heteroscedasticity.

Verified the normality of residuals using Q-Q plots and histograms.

# Decision Science & ROC Curve Analysis:

Simulated various harvesting strategies by iterating through different volume cutoffs.

Constructed an ROC curve by plotting the True Positive Rate (proportion of adults harvested) against the False Positive Rate (proportion of infants harvested).

Identified the optimal cutoff by finding the point that maximizes the difference between the TPR and FPR.

Calculated the Area Under the Curve (AUC) using the flux package to quantify the model's discriminatory power.

## Key Findings & Conclusion
The log-transformation was effective in normalizing the data, making it suitable for linear modeling.

The regression model demonstrated high predictive power (Adjusted R-squared: 0.95), with L_VOLUME and CLASS being highly significant predictors of meat yield.

The analysis identified a clear trade-off between maximizing adult harvest and protecting the infant population.

The ROC curve analysis yielded an AUC of 0.867, indicating good discriminatory power for separating adults from infants based on volume.

A final data-driven recommendation was made for an optimal harvesting cutoff that balances competing objectives, supported by a comprehensive analysis of various strategic choices.

## Tools Used
R & RMarkdown

Data Manipulation: dplyr

Visualization: ggplot2, Base R plotting

Statistical Analysis: rockchalk, moments, flux
