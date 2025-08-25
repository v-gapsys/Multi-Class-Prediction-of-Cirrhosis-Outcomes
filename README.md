# Multi-Class Prediction of Cirrhosis Outcomes

##  Kaggle Competition: Playground Series S3E26 https://www.kaggle.com/competitions/playground-series-s3e26/overview

This project participated in the **Playground Series S3E26** competition on Kaggle, which focused on predicting cirrhosis patient survival outcomes. Despite being a "playground" competition, this was a  multi-class prediction challenge that attracted 1,663 participants.

**Competition Status**:  **CLOSED** - No submissions could be made to the leaderboard after the competition ended.

##  Competition Details

- **Competition Type**: Multi-class classification
- **Evaluation Metric**: Multi-class logarithmic loss
- **Total Participants**: 1,663
- **Target Variable**: Patient Status (3 classes: C, CL, D)
- **Dataset**: Synthetic medical data based on real cirrhosis patient records

##  Project Objective

Predict the survival outcome of cirrhosis patients based on clinical features including:
- Patient demographics (Age, Sex)
- Clinical symptoms (Ascites, Hepatomegaly, Spiders, Edema)
- Laboratory values (Bilirubin, Cholesterol, Albumin, Copper, etc.)
- Treatment information (Drug type, N_Days)

## Approach & Methodology

### Data Strategy
- **Combined synthetic + original data**: Merged the competition's synthetic dataset with the original cirrhosis dataset to create a more robust training set
- **Total training samples**: 8,323 (7,905 synthetic + 418 original)
- **Test samples**: 5,271

### Model Architecture
- **Primary Model**: XGBoost with optimized hyperparameters
- **Preprocessing**: Advanced ColumnTransformer pipeline with separate handling of numeric and categorical features
- **Validation**: 10-fold stratified cross-validation
- **Feature Engineering**: 25 final features after preprocessing

### Key Hyperparameters
```python
{
    'max_depth': 29,
    'learning_rate': 0.05,
    'n_estimators': 850,
    'subsample': 0.65,
    'colsample_bytree': 0.18,
    'gamma': 0.9
}
```

##  Results & Performance

### Cross-Validation Performance
- **Mean CV Score**: 0.4175 ± 0.0168
- **Best Fold**: 0.3934
- **Worst Fold**: 0.4528
- **Overall OOF Score**: 0.4175

### Leaderboard Comparison
**Estimated Ranking**: Among the **top 30** out of 1,663 participants! 

Kaggle private score **0.39866**, this result would have placed in the top 2% of all submissions, demonstrating exceptional performance despite the competition being closed.

##  Technical Implementation

### Dependencies
- Python 3.x
- XGBoost
- Scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn

### File Structure
- `xgboost_final.ipynb` - Main implementation notebook
- `train.csv` - Training data
- `test.csv` - Test data  
- `cirrhosis.csv` - Original dataset
- `sample_submission.csv` - Submission format


- **Competition**: [Playground Series S3E26](https://www.kaggle.com/competitions/playground-series-s3e26)
- **Original Dataset**: [Cirrhosis Patient Survival Prediction](https://www.kaggle.com/datasets/joebeachcapital/cirrhosis-patient-survival-prediction)

