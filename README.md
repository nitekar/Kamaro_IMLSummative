# Kamaro: Country Vulnerability Classification

## Data source: https://www.kaggle.com/datasets/hellbuoy/pca-kmeans-hierarchical-clustering

##  Problem Statement

HELP International is a global NGO committed to combating poverty and supporting underdeveloped countries through direct aid and long-term developmental projects. After raising $10 million in recent funding, the organization now seeks to strategically allocate these resources to the countries most in need. The main challenge lies in identifying those nations that require urgent attention based on relevant indicators.

## Project Goal

This project aims to classify countries based on their **socio-economic and health indicators** to assist HELP International’s CEO in making data-driven decisions about aid distribution. 

---

##  Optimization Experiment Table (Neural Networks)

| Instance | Optimizer  | Learning Rate | Dropout | L2 Regularization | Early Stopping | Epochs | Accuracy | Loss  | F1 Score | Precision | Recall |
|----------|------------|---------------|---------|-------------------|----------------|--------|----------|-------|----------|-----------|--------|
| 1        | Default (Adam) | 0.001         | 0.3     | 0.001             | No             | 50     | 0.7901   | 0.6552 | 0.7780   | 0.7852    | 0.7841 |
| 2        | Adam       | 0.01          | 0.4     | 0.01              | Yes            | 26     | 0.8450   | 0.5893 | 0.8382   | 0.8417    | 0.8361 |
| 3        | RMSprop    | 0.005         | 0.5     | 0.005             | No             | 75     | 0.7632   | 0.7134 | 0.7525   | 0.7591    | 0.7456 |
| 4        | SGD        | 0.01          | 0.2     | 0.01              | Yes            | 92     | 0.7351   | 0.7290 | 0.7217   | 0.7360    | 0.7184 |



##  Summary of Findings

- **Best Performing Model:** Instance 2 (Adam, learning rate 0.01, dropout 0.4, L2=0.01, with EarlyStopping) with **Accuracy: 84.5%** and **F1-Score: 83.8%**.
- Instance 1 using default Adam settings performed decently as a baseline.
- Too high dropout or regularization (Instances 3 & 4) led to performance dips.
- Early stopping consistently improved training time and generalization.


##  Classical ML vs Neural Network

| Model                 | Accuracy | F1 Score | Precision | Recall |
|-----------------------|----------|----------|-----------|--------|
| Logistic Regression   | 0.8125   | 0.8061   | 0.8150    | 0.8017 |
| Simple Neural Network | 0.7653   | 0.7582   | 0.7651    | 0.7528 |
| Best Neural Network   | **0.8450** | **0.8382** | **0.8417**  | **0.8361** |

- **Best Model:** Neural Network (Instance 2)
- **ML Model Chosen:** Logistic Regression using `C=10`, `solver='lbfgs'`, `max_iter=1000`

---

## Video:

