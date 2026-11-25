# CareLoop Clinics – No-Show Guard

**GitHub Repository:** https://github.com/prr3mmmm/CareLoop-NoShow-Guard

## Project Overview

CareLoop Clinics operates eight outpatient clinics across six Indian cities. This project analyses appointment no-shows using Python, SQL, Machine Learning and Generative AI.

## Business Objective

Identify appointments that are most likely to be missed, understand the reasons behind missed appointments and recommend strategies to reduce no-shows.

## Tools and Technologies

- Python
- Google Colab
- Pandas and NumPy
- MySQL Workbench
- Matplotlib
- Scikit-learn
- Gemini API
- Pydantic
- GitHub

## Key Findings

1. **Part 1 – Data Cleaning:** The cleaned dataset contains 990 appointments, including 218 no-shows, resulting in an overall no-show rate of 22.02%.
2. **Part 2 – SQL Analysis:** Gomti Nagar Care Point has the highest no-show rate of 33.3%. Appointments booked more than 30 days in advance have a no-show rate of 60.5%.
3. **Part 3 – Machine Learning:** The selected model achieved a test ROC-AUC of [actual AUC] and flagged [actual flagged count] out of 198 test appointments.
4. **Part 4 – Generative AI:** Gemini analysed the first 10 patient follow-up notes, identifying structured reasons with [actual valid count] valid responses and one blank note skipped.

## Machine Learning Results

Three machine learning algorithms were trained and evaluated:

- Logistic Regression
- Decision Tree
- Random Forest

GridSearchCV was used to tune the Random Forest model. Five-fold cross-validation on training data was used to select the final model.

| Metric | Result |
|---|---|
| Training records | 792 |
| Testing records | 198 |
| Baseline accuracy | 75.25% |
| Selected model | [Actual model name] |
| Cross-validation ROC-AUC | [Actual CV AUC] |
| Test ROC-AUC | [Actual test AUC] |
| Final threshold | [Actual threshold] |
| Final precision | [Actual precision] |
| Final recall | [Actual recall] |
| Appointments flagged | [Actual flagged count] |

The final model was selected because it achieved the highest cross-validated ROC-AUC. The classification threshold was selected using the F1 score calculated from out-of-fold training predictions.

## Generative AI Analysis

The Gemini API was used to classify patient follow-up notes into six categories:

- forgot_or_no_reminder
- distance_or_transport
- cost_or_fee
- illness_or_emergency
- work_or_schedule
- other

A CRAFT prompt and JSON schema were used to generate structured responses. Pydantic was used to validate the responses. Blank notes were skipped, while invalid responses were retained for review.

Total Gemini generation calls: [Actual API call count]

## Business Recommendation

CareLoop Clinics should introduce targeted appointment reminders and follow-up calls for high-risk patients. Out of 990 appointments, 218 were missed, representing a 22.02% no-show rate. Appointments booked more than 30 days in advance have a particularly high no-show rate of 60.5%, while Gomti Nagar Care Point has the highest clinic-wise rate of 33.3%. The selected machine learning model can help the front desk prioritize patients for follow-up calls on the evening before their appointments. Patient follow-up notes can provide additional information about reminder issues, transportation difficulties and scheduling conflicts. CareLoop should pilot targeted follow-ups and measure whether they reduce missed appointments before implementing the strategy across all clinics.

## Limitations

1. Data cleaning statistics were calculated before the train-test split, allowing some indirect influence from test data.
2. The same patient may appear in both training and testing datasets, and the random split does not represent future appointment predictions.
3. Only 10 patient follow-up notes were analysed, so the AI findings cannot be generalized to all patients.

## Conclusion

This project combines data cleaning, SQL analysis, predictive machine learning and Generative AI to help CareLoop understand appointment no-shows and prioritize patient follow-up activities.
