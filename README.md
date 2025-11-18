# Motor Vehicle Insurance Premium Prediction

This project builds several regression models to predict motor vehicle insurance premiums. The workflow includes exploratory data analysis, data preparation, a baseline model, and three experiments using Ridge, Lasso, and K-nearest neighbors regression. The aim is to support pricing and risk management teams with a model that is stable, accurate, and easy to explain.

---

## 1. Project Overview

The dataset contains one year of motor insurance records. It includes customer details, policy information, claims history, and vehicle features. The target variable is the net premium amount.

Three regression models are tested:

- Ridge regression  
- Lasso regression  
- K-nearest neighbors (KNN) regression  

The project focuses on:

- Understanding the dataset and its limitations  
- Preparing clean and useful features  
- Comparing several models using a consistent validation method  
- Providing insights that support insurance pricing decisions  

---

## 2. File Structure

36106-AT1-25948860/  
│  
├── assignment/AT1/data/ # Provided datasets  
│  
├── 36106-AT1-25948860-a-EDA.ipynb # Exploratory Data Analysis  
├── 36106-AT1-25948860-b-Preparation.ipynb # Data Preparation  
│  
├── 36106-AT1-25948860-0-Baseline.ipynb # Baseline Model  
├── 36106-AT1-25948860-1-experiment-1.ipynb # Ridge Regression  
├── 36106-AT1-25948860-2-experiment-2.ipynb # Lasso Regression  
├── 36106-AT1-25948860-3-experiment-3.ipynb # KNN Regression  
│  
└── 36106-AT1-25948860-z-project_report.docx # Final report  

---

## 3. Notebook Summaries

### EDA Notebook

- Reviews distributions of the target variable  
- Checks missing values and outliers  
- Examines key features such as vehicle value, policy type, claims history, and seniority  
- Shows the narrow premium range  

### Preparation Notebook

- Removes personally identifiable information  
- Creates new features such as car age, driving experience, and age at contract  
- Applies log transformation to skewed variables  
- Standardizes continuous variables  
- Produces clean training and validation datasets  

### Baseline Notebook

- Uses the mean premium as a simple baseline  
- Helps show if trained models offer real improvements  

### Experiment 1 — Ridge Regression

- Tests several alpha values  
- Controls multicollinearity  
- Produces stable coefficient estimates  

### Experiment 2 — Lasso Regression

- Tests a detailed alpha grid  
- Selects a smaller set of meaningful features  
- Achieves the best validation MAE  

### Experiment 3 — KNN Regression

- Tests values of k, p, and distance weights  
- Uses selected features  
- Shows lower performance due to scaling sensitivity  

---

## 4. Model Performance

| Model     | Validation MAE |
|-----------|----------------|
| Baseline  | 147.72         |
| Ridge     | 126.95         |
| Lasso     | **126.46**     |
| KNN       | 128.58         |

Lasso regression performs the best and uses fewer features. Ridge regression is close but keeps all coefficients. KNN regression performs less effectively because distance-based methods are sensitive to feature scaling and higher dimensional data.

### Why Validation MAE is used

Validation MAE is the main measure of model performance. It shows the average size of prediction errors in the same unit as the premium. A lower MAE means the predictions are closer to real values. It is used instead of training MAE because it shows how well the model works on unseen data.

### Why MAE fits this project

MAE is suitable here because:

- The target range is narrow (460–676)  
- Small premium errors matter  
- MAE is simple to read and explain  
- MAE does not over-penalize outliers  
- It gives a direct sense of prediction accuracy in business terms  

### Other possible metrics

Other regression metrics include:

- **RMSE** — stronger penalty on large errors  
- **R²** — shows how much variance is explained  
- **Median Absolute Error** — more robust to outliers  

These metrics can be useful, but MAE is the clearest and most relevant for this project.

---

## 5. Key Findings

- The premium range is narrow, so even small errors matter  
- Vehicle value, policy type, claims history, and seniority are strong predictors  
- Lasso regression balances accuracy and interpretability well  
- Ridge regression performs similarly but keeps all features  
- KNN regression is sensitive to feature scaling  
- Log transformation and standardization improve performance  

---

## 6. Ethical Considerations

- Personal and sensitive information was removed before modelling  
- Some variables may act as proxies for protected attributes  
- Regular documentation and bias checks are recommended  
- Model transparency helps support fairness and trust  

---

## 7. How to Run the Project

1. Place datasets inside `assignment/AT1/data/`  
2. Open notebooks in this order:  
   - EDA  
   - Preparation  
   - Baseline  
   - Experiment 1  
   - Experiment 2  
   - Experiment 3  
3. Run all cells from top to bottom  
4. Read the final report for detailed explanations  

---

## Author

**Jiayu Hao**  
Master of Data Science and Innovation  
University of Technology Sydney  
