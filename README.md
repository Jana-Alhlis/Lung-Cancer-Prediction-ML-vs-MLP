# Lung Cancer Prediction: ML vs. Deep Learning

A comparative study of traditional machine learning algorithms and a neural network for lung cancer classification using patient-related data.

## Project Summary

This project investigates how different classification techniques perform on a lung cancer dataset. Four models were developed and evaluated to compare their predictive performance, ability to identify positive cases, and interpretability.

The evaluated approaches include Decision Tree, Logistic Regression, Gradient Boosting, and a Multi-Layer Perceptron (MLP).

The main objective is to assess whether a deep learning model offers an advantage over traditional machine learning methods for this tabular classification task.

## Dataset

The project uses the **Survey Lung Cancer** dataset, which contains survey-based patient attributes associated with lung cancer status.

- **Dataset:** Survey Lung Cancer
- **Task:** Binary classification
- **Input:** Patient-related features, including age and categorical attributes
- **Target:** Lung cancer status
- **Data source:** [Search for the Survey Lung Cancer dataset on Kaggle](https://www.kaggle.com/datasets?search=survey+lung+cancer)

The dataset was examined to understand its structure, feature distributions, class balance, and suitability for model training.

*Note: The exact number of records, feature count, and original dataset source should be confirmed from the dataset used in the notebook.*

## Data Preparation

The following preprocessing operations were included in the workflow:

- Inspecting missing values and feature distributions.
- Encoding categorical variables into numerical representations.
- Converting the target variable into binary labels.
- Standardizing the `AGE` feature.
- Examining low-variance features and class imbalance.
- Splitting the data into stratified training and testing sets.
- Applying SMOTE during model experimentation to address class imbalance.

Resampling should be performed on the training set only to avoid data leakage into the evaluation set.

## Models Evaluated

### Traditional Machine Learning

**Decision Tree**

Used to model feature-based decision rules and provide a relatively interpretable classification approach.

**Logistic Regression**

Included as a linear classification baseline for comparison with more complex algorithms.

**Gradient Boosting**

Evaluated as an ensemble method that combines sequentially trained decision trees to improve predictive performance.

### Deep Learning

**Multi-Layer Perceptron (MLP)**

A feed-forward neural network was implemented using TensorFlow/Keras with the following architecture:

- Input layer matching the prepared feature set.
- Dense layer with 32 neurons and ReLU activation.
- Dense layer with 16 neurons and ReLU activation.
- Sigmoid output layer for binary classification.

The documented training configuration used the Adam optimizer, binary cross-entropy loss, 20 epochs, and a batch size of 32.

## Model Evaluation

The models were compared using accuracy, sensitivity, and specificity to examine both overall classification performance and the identification of positive and negative cases.

### Reported Results

| Model | Accuracy | Sensitivity | Specificity |
|---|---:|---:|---:|
| Decision Tree | 94% | 92% | 96% |
| Gradient Boosting | 91% | 88% | 90% |
| Logistic Regression | 89% | 82% | 84% |
| MLP | 89% | 88% | 91% |

### Observations

The Decision Tree achieved the highest reported accuracy at 94%, with 92% sensitivity and 96% specificity.

Gradient Boosting ranked second in accuracy, while Logistic Regression and the MLP both achieved 89%.

These findings illustrate that traditional machine learning methods can perform competitively on structured datasets and may outperform neural networks in some experimental settings.

The reported results depend on the dataset, preprocessing choices, train-test split, and evaluation procedure.

## Model Interpretability

Interpretability was considered alongside predictive performance:

- **Decision Tree:** Decision paths can be inspected to understand how predictions are made.
- **Logistic Regression:** Model coefficients can help explain feature relationships.
- **Gradient Boosting:** Feature importance can be examined, although the combined model is more complex.
- **MLP:** Its layered architecture can make individual predictions more difficult to explain.

For healthcare-related classification, model performance should be assessed alongside error patterns, reliability, and the consequences of false-negative predictions.

## Workflow

1. Load and inspect the dataset.
2. Explore feature distributions and target balance.
3. Encode categorical features and prepare numerical inputs.
4. Split the data into training and testing sets.
5. Apply the selected preprocessing and imbalance-handling methods.
6. Train the four classification models.
7. Evaluate predictions using classification metrics and confusion matrices.
8. Compare model performance and interpretability.

## Technology Stack

- **Programming:** Python
- **Data Analysis:** Pandas, NumPy
- **Machine Learning:** Scikit-learn
- **Deep Learning:** TensorFlow, Keras
- **Class Imbalance:** SMOTE
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

## Project Contents

The notebook documents the main stages of the experiment, including:

- Exploratory data analysis.
- Data preprocessing and feature preparation.
- Traditional machine learning model training.
- MLP architecture and training.
- Performance evaluation and model comparison.
- Confusion matrices and visualization of results.
- Feature importance and training-history analysis, where applicable.

## Potential Improvements

Future work could strengthen the evaluation by:

- Using cross-validation to assess model stability.
- Reporting precision, recall, F1-score, and ROC-AUC.
- Verifying that SMOTE is applied only to training data.
- Investigating feature importance and prediction errors.
- Evaluating the models on additional independent data.
- Assessing the impact of false negatives in the intended application.

## Academic Context

This project explores the application of machine learning and deep learning to a healthcare-related classification problem, with an emphasis on model comparison and interpretability.
