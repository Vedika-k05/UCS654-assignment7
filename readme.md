# Sampling Techniques on Imbalanced Credit Card Dataset

##  Objective

The objective of this assignment is to understand the importance of sampling techniques in handling imbalanced datasets and to analyze how different sampling strategies affect the performance of various machine learning models.


##  Dataset

The dataset used is a credit card transaction dataset containing fraudulent and non-fraudulent transactions.

* Original Records: 772
* Class Distribution:

  * Normal (0): 763
  * Fraud (1): 9

This shows a highly imbalanced dataset, which can bias machine learning models.

To remove bias, the dataset was balanced using **undersampling**.


##  Sampling Techniques Used

Five probabilistic sampling techniques were applied to create different samples:

1. Simple Random Sampling
2. Systematic Sampling
3. Stratified Sampling
4. Simple Random Sampling (different seed)
5. Bootstrap Sampling


##  Machine Learning Models Used

The following models were trained and evaluated:

* Logistic Regression
* Random Forest
* Support Vector Machine (SVM)
* Naive Bayes
* K-Nearest Neighbors (KNN)


##  Results

| Model               | Simple Random | Systematic | Stratified | Random (Seed 2) | Bootstrap |
| ------------------- | ------------- | ---------- | ---------- | --------------- | --------- |
| Logistic Regression | **1.0**       | 0.5        | 0.0        | **1.0**         | 0.5       |
| Random Forest       | 0.0           | 0.0        | **0.5**    | 0.5             | 0.5       |
| SVM                 | 0.0           | 0.5        | 0.0        | 0.5             | 0.5       |
| Naive Bayes         | 0.5           | 0.5        | 0.0        | 0.5             | 0.5       |
| KNN                 | 0.0           | 0.5        | 0.0        | 0.5             | 0.5       |

---

##  Best Sampling Technique for Each Model

From the results:

- Logistic Regression → performed best with Simple Random Sampling and Random Sampling (Seed 2).
- Random Forest → performed best with Stratified, Random (Seed 2)and Bootstrap Sampling.
- SVM → showed better performance with Systematic,Random (Seed 2)and Bootstrap Sampling.
- Naive Bayes → showed stable performance across Systematic, Random (Seed 2) and Bootstrap Sampling.
- KNN → performed better with Systematic, Random (Seed 2) and *Bootstrap Sampling.

###  Overall Observation

* **Bootstrap Sampling** and **Random Sampling (Seed 2)** produced the most consistent performance across models.
* Logistic Regression achieved the highest accuracy overall.



##  Discussion

The original dataset was highly imbalanced, which could lead to biased predictions favoring the majority class. After balancing the dataset, different sampling techniques were applied to evaluate their impact on model performance.

Due to the small dataset size, accuracy varied across samples. Even a single incorrect prediction significantly affected performance metrics. This highlights the importance of appropriate sampling strategies when working with limited or imbalanced data.

Bootstrap sampling provided stable results, while stratified sampling ensured class balance but did not perform well due to the extremely small dataset.


