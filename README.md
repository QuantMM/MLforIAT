Machine Learning Strategies for IAT Score Prediction
====================================================

This repository describes the decision making process for the following project:
Can a good predictive model (i.e., the one having a good balance between bias and variance that minimizes the total error) reveal meaningful individual differences on IAT scores, across 8 different training conditions?

Author(s)
-------
- **Sunmee Kim** <sunmee.kim@mail.mcgill.ca>

Updates: Jan - Feb, 2020
----------
- Final decision on the outcome variable and the baseline scores as a covariate through both a literature review and empirical study: Diff = (intercept) + (IAT.t0 as a covariate) + (the rest of the predictors)
  - Literature: [Allison (1990)](https://www.jstor.org/stable/271083?seq=1#metadata_info_tab_contents), [Dalecki and Willits (1991)](https://www.tandfonline.com/doi/abs/10.1080/02732173.1991.9981960), [Vickers and Altman (2001)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1121605/)
  - A simulation: By looking at these two figures ([Fig1](https://github.com/QuantMM/MLforIAT/blob/master/Diff.png) and [Fig2](https://github.com/QuantMM/MLforIAT/blob/master/IATt2.png)), the model with Diff resulted in smaller MSEs in both training and validation sets
    - (1) across various data splitting percentages (from 70/30, 80/20, to 90-10 splits)
    - (2) using two machine learning techniques (Ridge and lasso)
    - (3) using either the change score or IAT.t2 as outcome
    
- Four models to compare:
  - (1): reg with main effects
  - (2), (3): ridge/lasso reg with all possible 2-way interactions (using IAT.t0)
  - (4): Neural Net

- Model evaluation metrics:
  - [p. 1087 of Wu et al. (2018)](https://dl.acm.org/doi/abs/10.1145/3209978.3210077)
  - ![RMSE and Corr](https://github.com/QuantMM/MLforIAT/blob/master/evaluation_metrics.PNG)

- Training (80%) / Validation (20%) split for model building
  - To avoid overfitting and increase generalizability
