# DBSCAN-Bayesian-Network


🧩 Part 1 — DBSCAN Image Denoising
In this part, I applied the DBSCAN clustering algorithm to remove noise from a binarized 28×28 MNIST image.


Each pixel was represented by its (x, y) coordinates and intensity value (–1 = dark, +1 = light).


DBSCAN was used to identify noisy pixels (label = -1) and cluster the true digit pixels.


By adjusting parameters (eps and min_samples), I reduced misclassified noise points.


A custom function then replaced each noisy pixel’s intensity with the majority of its clean neighbors, producing a cleaner image.


Result:
The DBSCAN model successfully detected and removed most noise, leaving a clearer reconstructed digit.

❤️ Part 2 — Bayesian Network for Heart Disease Prediction
I built a Bayesian Network (BN) using the pgmpy library to model relationships between clinical variables:
Age, Sex, Cholesterol, Resting BP, Fasting Blood Sugar, and Heart Disease (HD).
Steps:


Created the BN structure:
Age → Chol, Sex → Chol, Chol → HD, RestBP → HD, FastingBS → HD


Trained parameters using Maximum Likelihood Estimation (MLE).


Verified that P(Sex) matched dataset proportions (≈31.6% female, 68.4% male).


Used Variable Elimination for inference:


Found that HD probability differs by Age/Sex when Chol isn’t given.


When Chol is fixed, HD probability stays constant — confirming conditional independencies
Age⫫HD∣CholAge ⫫ HD | CholAge⫫HD∣Chol and Sex⫫HD∣CholSex ⫫ HD | CholSex⫫HD∣Chol.




Evaluated test accuracy:
BN accuracy = 0.9854 (98.5%)



Summary:


DBSCAN was used for unsupervised noise detection and image cleanup.


The Bayesian Network modeled probabilistic dependencies for heart disease prediction, achieving ~98.5% accuracy on the test data.

