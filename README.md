Machine Learning Strategies for IAT Score Prediction
====================================================

This repository describes the decision making process for the following project:
Can a good predictive model (i.e., the one having a good balance between bias and variance that minimizes the total error) reveal meaningful individual differences on IAT scores, across 8 different training conditions?

Author(s)
-------
- **Sunmee Kim** <sunmee.kim@mail.mcgill.ca>

Updates
----------
- 2020-Feb-04: final decision on the outcome variable and the baseline scores as a covariate through both a literature review and empirical study
  - References: [Allison, 1990](https://www.jstor.org/stable/271083?seq=1#metadata_info_tab_contents), [Dalecki and Willits, 1991](https://www.tandfonline.com/doi/abs/10.1080/02732173.1991.9981960), [Vickers and Altman, 2001](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1121605/)
  - A simulation:
    - (1) across various data splitting percentages (from 70/30, 80/20, to 90-10 splits)
    - (2) using two machine learning techniques (Ridge and lasso)
    - (3) using either the change score or IAT.t2 as outcome
