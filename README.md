# Breast Cancer Prediction

## Description

Breast cancer is the most common cancer among women globally, accounting for 25% of all cancer cases. In 2015 alone, it affected over 2.1 million people. The disease starts when cells in the breast grow uncontrollably, often forming tumors that can be detected via X-ray or felt as lumps. Detecting whether these tumors are malignant (cancerous) or benign (non-cancerous) is a critical challenge.

This project aims to classify tumors as malignant or benign using machine learning models based on real-world datasets. The dataset used can be found on Kaggle:
[Breast Cancer Dataset](https://www.kaggle.com/datasets/yasserh/breast-cancer-dataset).

### Attribute Information
1. **ID number**
2. **Diagnosis**: Malignant (M) or Benign (B)
3. **Features**: Ten real-valued features are computed for each cell nucleus:
    - Radius (mean distance from center to perimeter points)
    - Texture (standard deviation of gray-scale values)
    - Perimeter
    - Area
    - Smoothness (local variation in radius lengths)
    - Compactness (perimeter²/area - 1.0)
    - Concavity (severity of concave portions of the contour)
    - Concave points (number of concave portions of the contour)
    - Symmetry
    - Fractal dimension ("coastline approximation" - 1)

Each feature's mean, standard error, and "worst" (largest value) are also included, resulting in 30 total features.

---

## Installation

To run this project, ensure you have Python 3.7+ and the following libraries installed:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn
```

---

## Project Structure

- **breast-cancer.csv**: Dataset used for training and testing.
- **Data Preparation**: Feature selection and preprocessing steps.
- **Modeling**:
    - Random Forest Classifier
    - Support Vector Machine (SVM)
- **Evaluation**: Confusion matrix and classification report for both models.

---

## Exploratory Data Analysis (EDA)

- Histograms were plotted to observe the distribution of features for malignant and benign cases.
- Key findings:
  - Larger mean, standard error, and worst values of `radius`, `concave points`, `concavity`, `compactness`, `area`, and `perimeter` correlate strongly with malignant tumors.
  - Features like `texture`, `smoothness`, `symmetry`, and `fractal dimension` do not show a significant correlation.

---

## Feature Selection

The following features were identified as important for classification:

- **Mean Features**: `radius_mean`, `perimeter_mean`, `area_mean`, `compactness_mean`, `concavity_mean`, `concave points_mean`
- **Standard Error Features**: `radius_se`, `perimeter_se`, `area_se`, `compactness_se`, `concave points_se`
- **Worst Features**: `radius_worst`, `perimeter_worst`, `area_worst`, `compactness_worst`, `concavity_mean`, `concave points_worst`

---

## Data Preprocessing

- The selected features were normalized using `MinMaxScaler`.
- The dataset was split into training (20%) and testing (80%) sets.

---

## Model Training and Evaluation

### Random Forest Classifier
- **Performance**:
  - Achieved better accuracy and precision compared to SVM.
  - Provides robust performance for this classification task.

### Support Vector Machine (SVM)
- **Performance**:
  - Slightly lower accuracy compared to Random Forest.
  - Still effective but not as precise as Random Forest for this dataset.

---

## Results

- Random Forest outperformed SVM in accuracy and precision for predicting breast cancer.
- Confusion matrices and classification reports indicate the effectiveness of feature selection and preprocessing.

---

## How to Run

1. Clone the repository and navigate to the project directory.
2. Load the dataset (`breast-cancer.csv`).
3. Run the Python script containing the model training and evaluation steps.

---

## Future Improvements

1. Explore more advanced machine learning models like XGBoost or Neural Networks.
2. Perform hyperparameter tuning for the Random Forest and SVM models.
3. Use cross-validation for better model evaluation.
4. Integrate the model into a web application for user-friendly predictions.


