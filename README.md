# Motor Vehicle Insurance Premium Prediction (36106 AT1)

This project builds several regression models to predict motor vehicle insurance premiums. It includes exploratory data analysis, data preparation, a baseline model, and three experiments (Ridge, Lasso, and KNN regression). The goal is to support pricing and risk teams with a model that is accurate, stable, and easy to explain.

---

## 1. Project Overview

The dataset contains one year of motor insurance records. It includes customer details, policy information, claims history, and vehicle features. The target is the net premium amount.

Three models are tested:

- Ridge regression  
- Lasso regression  
- K-nearest neighbors (KNN) regression  

The project aims to:

- Understand the data  
- Prepare clean features  
- Compare several models  
- Provide insights for pricing decisions  

---

## 2. File Structure

```text
/  
│  
├── 36106/assignment/AT1/data/ # Provided datasets  
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
```

---

## 3. Notebook Summaries

### EDA Notebook
- Looks at the distribution of the target  
- Checks missing values and outliers  
- Reviews important features (vehicle value, policy type, claims, seniority)  

### Preparation Notebook
- Removes personal information  
- Creates new features (car age, driving experience, age at contract)  
- Uses log1p on skewed features  
- Standardizes all numeric variables  
- Produces training and validation datasets  

### Baseline Notebook
- Uses the mean premium as a simple baseline  
- Helps compare improvements from trained models  

### Ridge Regression
- Tests several alpha values  
- Controls multicollinearity  
- Gives stable results  

### Lasso Regression
- Tests a detailed alpha grid  
- Selects key features  
- Achieves the best validation MAE  

### KNN Regression
- Tests different values of k, p, and distance weights  
- Uses selected features  
- More sensitive to scaling and performs slightly worse  

---

## 4. Model Performance

| Model     | Validation MAE |
|-----------|----------------|
| Baseline  | 147.72         |
| Ridge     | 126.95         |
| Lasso     | **126.46**     |
| KNN       | 128.58         |

Lasso regression performs best and uses fewer features. Ridge is close. KNN is weaker because it is sensitive to feature scaling and higher dimensions.

### Why Validation MAE is used

Validation MAE shows the average size of prediction errors on unseen data. It is simple to read and uses the same units as the premium. It is preferred because it shows how well the model works in real business conditions.

### Why MAE fits this project

- The target range is narrow  
- Small mistakes matter  
- MAE is easy to understand  
- MAE does not over-penalize large errors  
- It gives a clear sense of prediction accuracy  

### Other possible metrics

- RMSE (stronger penalty on large errors)  
- R² (explains variance)  
- Median Absolute Error (robust to outliers)  

MAE is still the most practical and relevant for this project.

---

## 5. Key Findings

- Premium values are tightly grouped, so small errors matter  
- Strong predictors include vehicle value, policy type, claims history, and seniority  
- Lasso regression balances accuracy and interpretability well  
- Ridge regression performs similarly  
- KNN is more sensitive to scaling  
- Log transforms and standardization improve model performance  

---

## 6. Ethical Considerations

- Removed personal information before modelling  
- Some variables may still act as proxies  
- Bias checks and documentation are recommended  
- Clear explanations help ensure fairness and trust  

---

## 7. How to Run the Project

1. Put the datasets inside `assignment/AT1/data/`  
2. Run the notebooks in this order:  
   - EDA  
   - Preparation  
   - Baseline  
   - Experiment 1  
   - Experiment 2  
   - Experiment 3  
3. Run each notebook top to bottom  
4. See the final report for detailed analysis  
