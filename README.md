# capstone-sentencing
My senior Capstone research project identifies any inherent bias in prison sentencing algorithms and proposes ways to eliminate them using data science techniques.
I used the ProPublica COMPAS dataset to create both a random forest and logistic regression model that I performed several tests of fairness on. Initial exploration of the input variables in the dataset is found in “Data Exploration” in the "code" folder. I measured disparate impact by comparing positive predictions, precision of predictions, and true negatives across sub-groups to measure proportional parity, predictive parity, and specificity parity respectively. The initial data processing, the results of the initial random forest classifier, and functions for three tests of fairness of the three subsets of risk are found in “Data Split” in the "code" folder. The final random forest and logistic classifier fairness tests and an attempt at a regularization parameter are found in “Final Risk Models” in the "code" folder. I also compared the inverse true positive ratio across Caucasian and African-American subgroups to create a powerful visual that exemplified the bias that exists in presumption towards high risk for African-Americans. This graph can be found in “Odds Chart” in the "resources" folder.
I studied multiple possible solutions – (1) Proposed in “Data preprocessing techniques for classification without discrimination” by Faisal Kamiran and Toon Calders and supported in “The racist algorithm?” by Anupam Chander, re-weight the training dataset so that the protected variable correlates to more positive outcomes for the disadvantaged group than other cases; (2) From “Achieving Fairness through Adversarial Learning: an Application to Recidivism Prediction” by Christina Wadsworth et al., re-train the algorithm to prevent a second algorithm from guessing the protected variable given the training data and the outcome; (3) Proposed in “Fairness-aware Learning through Regularization Approach” by Toshihiro Kamishima et al. and referenced in “Fairness in Criminal Justice Risk Assessments: The State of the Art” by Richard Berk et al., minimize the mutual information between the protected variable and the outcome. My analysis of each solution can be found in “Solution Notes” in the "resources" folder. 
I used a fair learn package to re-weight the data, and found that the inverse true positive disparity reduced by around 30%. My practice with this bias reduction method is found in “Bias Reduction Sample” in the "code" folder. The results of the reweighting are found in “Bias Reduction” in the "code" folder. My final presentation and script can be found in the "presentation" folder.
