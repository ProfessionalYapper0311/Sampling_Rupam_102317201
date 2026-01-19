# Sampling Techniques for Imbalanced Data

## Project Overview
This project analyzes the impact of different sampling techniques on the performance of various ml models when dealing with a highly imbalanced dataset. 


## Methodology

### 1. Data Preprocessing (Leakage Prevention)
Handling imbalanced data requires careful splitting to avoid **data leakage** which can occur if you tend to oversample the minority class to match the majority class.
* **Split First:** The dataset was first split into **Training** and **Testing** sets using `train_test_split`.
* **Balance Training Data Only:** We balanced the training set using **Random Oversampling** to handle the min class. The testing set was kept **untouched** and **imbalanced** for real-world performance accurately.

### 2. Sampling Techniques
We determined the appropriate sample size using thhe given formula to find the **sample size** (95% confidence, 5% error). Five different sampling techniques were applied to the balanced training data:
1.  **Simple Random Sampling:** Random selection of samples from the population.
2.  **Systematic Sampling:** Selecting samples after every $k^{th}$ record at regular intervals.
3.  **Stratified Sampling:** Startify ensures that sample preserves the class distribution (50:50).
4.  **Cluster Sampling:** Grouping data into clusters and randomly selecting clusters from the entire clusters for samples.
5.  **Bootstrap Sampling:** Random sampling but with replacement, items picked have a tendency to be picked again having equal probability.

### 3. Models Evaluated
For each of the 5 samples, we trained each sample using different model:-
* Logistic Regression
* Decision Tree 
* Random Forest 
* Support Vector Machine 
* K-Nearest Neighbors 

## Results
<img width="453" height="217" alt="image" src="https://github.com/user-attachments/assets/434a8ae7-5ba9-4372-8a03-3ac9570caf4a" />


## Conclusion
  <img width="653" height="182" alt="image" src="https://github.com/user-attachments/assets/4ff37411-bda5-4a17-82b8-8f7fad729629" />

* **Random Forest** achieved the highest accuracy of **99.48%** and it utilized either **Cluster Sampling** or **BootStrap Sampling**
* Stratified and Random sampling generally provided more consistent results across different models. Cluster sampling showed higher variability but it's dependent based on the selected clusters.
* Tree-based models like random forest and decision tree handled the complexity of the dataset better than linear models like logistic regression, this was true even for smaller sample sizes.
  <img width="392" height="108" alt="image" src="https://github.com/user-attachments/assets/1b18e94d-ca1c-4908-adbf-ef0f5e5452dd" />

