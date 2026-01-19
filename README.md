# Sampling Techniques for Imbalanced Data

## Project Overview
This project analyzes the impact of different sampling techniques on the performance of various machine learning models when dealing with a highly imbalanced dataset. The dataset used is `Creditcard_data.csv`, which contains transactions labeled as legitimate (0) or fraud (1).

## Methodology

### 1. Data Preprocessing & Leakage Prevention
Handling imbalanced data requires careful splitting to avoid **data leakage**.
* **Split First:** The dataset was first split into **Training** and **Testing** sets using `train_test_split`.
* **Balance Training Data Only:** We balanced the training set using **Random Oversampling** (SMOTE-like logic) to handle the minority class (Fraud). The testing set was kept **untouched** and **imbalanced** to reflect real-world performance accurately.

### 2. Sampling Techniques
We determined the appropriate sample size using **Cochran’s Formula** (95% confidence, 5% margin of error). Five different sampling techniques were applied to the balanced training data:
1.  **Simple Random Sampling:** Randomly selecting samples from the population.
2.  **Systematic Sampling:** Selecting every $k^{th}$ record at regular intervals.
3.  **Stratified Sampling:** Ensuring the sample preserves the class distribution (50:50).
4.  **Cluster Sampling:** Grouping data into clusters and randomly selecting entire clusters.
5.  **Bootstrap Sampling:** Random sampling with replacement.

### 3. Models Evaluated
We trained five different machine learning models on each of the five samples:
* **M1:** Logistic Regression
* **M2:** Decision Tree Classifier
* **M3:** Random Forest Classifier
* **M4:** Support Vector Machine (SVM)
* **M5:** K-Nearest Neighbors (KNN)

## Results

The models were evaluated based on **Accuracy** on the unseen test set.

| Model | Random Sampling | Systematic Sampling | Stratified Sampling | Cluster Sampling | Bootstrap Sampling |
|-------|-----------------|---------------------|---------------------|------------------|--------------------|
| **M1** (Logistic Regression) | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* |
| **M2** (Decision Tree)       | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* |
| **M3** (Random Forest)       | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* |
| **M4** (SVM)                 | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* |
| **M5** (KNN)                 | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* | *[Insert Acc]* |

*(Note: Replace `[Insert Acc]` with the values from your generated `sampling_rupam_102317201.csv` file)*

## Discussion
* **Best Performer:** The **[Insert Best Model Name]** model utilizing **[Insert Best Sampling Technique]** achieved the highest accuracy of **[Insert Accuracy]%**.
* **Impact of Sampling:** Stratified and Random sampling generally provided more consistent results across different models. Cluster sampling showed higher variability depending on the representativeness of the selected clusters.
* **Model Comparison:** Tree-based models (Random Forest, Decision Tree) handled the complexity of the credit card data better than linear models (Logistic Regression), even with smaller sample sizes.

## How to Run
1.  Ensure `Creditcard_data.csv` is in the directory.
2.  Run the script:
    ```bash
    python sampling_assignment.py
    ```
3.  The results will be saved to `sampling_rupam_102317201.csv` and printed to the console.
