# Microsoft: Cybersecurity Incident Classification

This project aims to enhance the efficiency of Security Operation Centers (SOCs) by developing a machine learning model to automatically classify cybersecurity incidents. By categorizing incidents as **True Positive (TP)**, **Benign Positive (BP)**, or **False Positive (FP)**, the model helps security analysts prioritize genuine threats and reduce manual triage efforts.

## 🚀 Key Features

  * **Comprehensive Data Preprocessing**: Handles missing values, performs feature engineering (e.g., creating a `Month` feature), and encodes categorical data.
  * **Advanced Modeling**: Utilizes a powerful **XGBoost Classifier**, a leading model for structured data, to achieve high-performance classification.
  * **Hyperparameter Optimization**: Employs `RandomizedSearchCV` to efficiently find the optimal model settings, maximizing performance without exhaustive search.
  * **Robust Evaluation**: The final model is rigorously evaluated on a completely unseen test dataset to ensure its effectiveness and ability to generalize to new, real-world data.

## 📊 Model Performance

The final XGBoost model achieved excellent results on the unseen test data. The performance metrics confirm its ability to accurately classify cybersecurity incidents.

### Test Set Metrics:

| Metric | Score |
| :--- | :--- |
| **Accuracy** | 90.7% |
| **Macro F1 Score** | 90.0% |

### Confusion Matrix (Test Set)

| | **Predicted 0 (TP)** | **Predicted 1 (BP)** | **Predicted 2 (FP)** |
| :--- | :--- | :--- | :--- |
| **Actual 0 (TP)** | 1,629,873 | 72,736 | 50,331 |
| **Actual 1 (BP)** | 96,467 | 755,065 | 51,166 |
| **Actual 2 (FP)** | 84,311 | 29,054 | 1,378,989 |

## 💡 Insights & Error Analysis

The model performs exceptionally well across all classes, but a detailed error analysis reveals specific areas for future improvement:

  * **Primary Challenge**: The model struggles most with classifying **Benign Positive (Class 1)** incidents. This class accounts for the highest number of misclassifications, indicating its inherent complexity and similarity to other incident types.
  * **Future Work**: Addressing this issue could involve exploring advanced data balancing techniques or developing more sophisticated features that better differentiate between benign and malicious events.
