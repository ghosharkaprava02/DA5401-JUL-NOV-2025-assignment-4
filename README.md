# DA5401 – Assignment 4  
**GMM-Based Synthetic Sampling for Imbalanced Data**

---

- **Name:** Arkaprava Ghosh  
- **Roll Number:** DA25C003  

---

## Repository Structure

- **ghosharkaprava02**  
  - **DA5401-JUL-NOV-2025-assignment-4**  
    - Assignment4_DA5401_final.ipynb → Main Jupyter Notebook  
    - README.md → Documentation  

---

## Documentation
This repository contains my submission for **Assignment 4** of DA5401.  
The objective is to address **class imbalance in fraud detection** using a **Gaussian Mixture Model (GMM)-based synthetic sampling** approach, and compare its performance with a baseline model.

The notebook includes:
1. **Data Analysis & Baseline Model** – Logistic Regression trained on the imbalanced dataset.  
2. **GMM Implementation** – Fitting a GMM on minority class samples and selecting the number of components using BIC.  
3. **Synthetic Data Generation** – Generating new minority samples by sampling from the GMM.  
4. **Rebalancing with CBU** – Applying clustering-based undersampling on the majority class and balancing with GMM-synthetic samples.  
5. **Performance Comparison** – Evaluating baseline, GMM-only, and GMM+CBU models on Precision, Recall, and F1-score.  

---

## Results Summary

**Minority Class Performance**

| Metric     | Baseline | GMM-only | GMM+CBU |
|------------|----------|----------|---------|
| Precision  | 0.8505   | 0.0933   | 0.0781  |
| Recall     | 0.6149   | 0.8514   | 0.8581  |
| F1-score   | 0.7137   | 0.1682   | 0.1431  |

- **Baseline:** High precision but limited recall (misses many frauds).  
- **GMM-only:** Significantly boosts recall (~0.85) but precision drops sharply, leading to many false positives.  
- **GMM+CBU:** Maintains high recall while reducing dataset size; precision slightly lower, but better balance in practical settings.  

**Conclusion:**  
- Accuracy alone is misleading for imbalanced data.  
- GMM-based oversampling greatly improves the ability to detect the minority class (recall).  
- **GMM + CBU** offers the best trade-off, making it the recommended strategy for fraud detection when recall is the priority.  
  
