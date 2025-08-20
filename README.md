# Predicting Immune-Related Adverse Events (irAEs) from Structured IO Data Using Machine Learning

## Overview
This project develops machine learning models to predict **immune-related adverse events (irAEs)** in melanoma patients undergoing **immune checkpoint inhibitor (ICI) therapy**. Using structured EHR data from the **Lombardi Comprehensive Cancer Center (LCCC) I/O Registry**, we aim to identify patients at high risk of irAEs to improve clinical decision-making and patient management.

---

## Objectives
- Build predictive models for irAEs using structured demographic, clinical, and treatment data.
- Evaluate model performance across multiple classifiers.
- Identify key predictive features to guide future research and clinical applications.

---

## Dataset
- **Source**: Lombardi Comprehensive Cancer Center I/O Registry  
- **Cohort**: Melanoma patients receiving ICI therapy  
- **Variables**:  
  - Demographics (e.g., age, sex, race)  
  - Clinical history (e.g., comorbidities, labs)  
  - Treatment details (e.g., ICI type, drug category, line of therapy)  
  - irAE outcomes (binary classification: irAE vs. no irAE)

---

## Methods
1. **Preprocessing**
   - Data cleaning and handling missing values.
   - Feature engineering (Charlson Comorbidity Index, grouped cancer types, drug categories).
   - Encoding categorical variables and scaling continuous variables.

2. **Modeling**
   - Classifiers tested:
     - Logistic Regression
     - Random Forest
     - Gradient Boosted Trees
   - Evaluation metrics:
     - Accuracy
     - AUROC (Area Under the Receiver Operating Characteristic Curve)
     - Precision, Recall, F1-score

3. **Feature Importance**
   - SHAP (SHapley Additive exPlanations) values were used to interpret model predictions.

---

## Results
- **Random Forest** and **Gradient Boosted Trees** achieved the highest AUROC scores.
- Important predictive features included:
  - Type of ICI drug
  - Cancer type
  - Comorbidity index
  - Demographic factors (age, sex)

---

## Discussion
- The models demonstrated promising predictive ability for irAEs, with ensemble methods outperforming linear models.
- Feature importance highlighted clinically meaningful predictors, aligning with existing research.
- Limitations:
  - Single-institution dataset
  - Limited sample size
  - Only structured data used (no unstructured clinical notes or lab time series)

---

## Future Work
- Expand to multi-institutional datasets for generalizability.
- Integrate unstructured data (e.g., clinical notes, lab trends).
- Explore survival analysis and time-to-event modeling for irAEs.
- Develop clinician-friendly dashboards for real-time prediction.

---

## Team
- **Student Investigator**: Austin Cherian  
- **Mentors**:  
  - Yili Zhang, PhD (HIDS Faculty)  
  - Adil Alaoui, PhD (HIDS Capstone Course Director)  
  - Neil Shah, MD (LCCC Clinical Mentor)

---

## Acknowledgments
Special thanks to the **Lombardi Comprehensive Cancer Center** for providing access to the I/O Registry dataset and to the HIDS faculty for guidance throughout the project.

---

## License
This project is for **academic and educational purposes only**. Clinical application would require further validation and regulatory review.
