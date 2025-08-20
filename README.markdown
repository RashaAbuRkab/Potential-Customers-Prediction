# ExtraaLearn Project: Potential Customers Prediction

## Overview
This project aims to predict which leads are likely to convert into paid customers for ExtraaLearn, an EdTech startup offering programs on cutting-edge technologies. The analysis involves exploratory data analysis (EDA), building machine learning models (Decision Tree and Random Forest), hyperparameter tuning, and providing actionable insights to optimize lead nurturing strategies. The implementation is provided in a Jupyter Notebook (`Rasha_Abu_Rkab- Full Code Version - Potential Customers Prediction.ipynb`) using Python with libraries like Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn.

## Context
The EdTech industry is projected to reach $286.62 billion by 2023 with a CAGR of 10.26% from 2018 to 2023. The surge in online education, accelerated by COVID-19, has led to increased lead generation through digital marketing, social media, website interactions, and emails. ExtraaLearn seeks to identify high-potential leads to allocate resources efficiently.

## Objective
- Develop a machine learning model to predict lead conversion likelihood.
- Identify key factors driving lead conversion.
- Create a profile of leads most likely to convert.

## Data Description
The dataset (`ExtraaLearn.csv`) contains 4,612 records and 15 features:
- **ID**: Unique identifier for the lead.
- **age**: Age of the lead (18–63 years).
- **current_occupation**: 'Professional', 'Unemployed', or 'Student'.
- **first_interaction**: Initial interaction channel ('Website' or 'Mobile App').
- **profile_completed**: Profile completion level ('Low': 0–50%, 'Medium': 50–75%, 'High': 75–100%).
- **website_visits**: Number of website visits (0–30).
- **time_spent_on_website**: Total time spent on the website in seconds (0–2,537).
- **page_views_per_visit**: Average pages viewed per visit (0–18.434).
- **last_activity**: Last interaction type ('Email Activity', 'Phone Activity', 'Website Activity').
- **print_media_type1**: Seen ad in Newspaper? ('Yes'/'No').
- **print_media_type2**: Seen ad in Magazine? ('Yes'/'No').
- **digital_media**: Seen ad on digital platforms? ('Yes'/'No').
- **educational_channels**: Heard via educational forums? ('Yes'/'No').
- **referral**: Heard via referral? ('Yes'/'No').
- **status**: Target variable (1: Converted, 0: Not converted; ~30% positive class).

### Data Observations
- No missing values or duplicate rows.
- Numerical features (e.g., `time_spent_on_website`) show skewness.
- Categorical features are balanced across categories.

## Installation
1. Clone the repository:
   ```
   git clone https://github.com/RashaAbuRkab/Potential-Customers-Prediction
   cd Potential-Customers-Prediction
   ```
2. Create a virtual environment (recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

## Usage
1. Place the dataset (`ExtraaLearn.csv`) in the project directory.
2. Launch Jupyter Notebook:
   ```
   jupyter notebook "Rasha_Abu_Rkab- Full Code Version - Potential Customers Prediction.ipynb"
   ```
3. Execute cells sequentially to perform:
   - Data loading and preprocessing.
   - Exploratory Data Analysis (EDA) with visualizations.
   - Model training (Decision Tree and Random Forest).
   - Hyperparameter tuning and evaluation.
   - Feature importance analysis and actionable insights.

## Exploratory Data Analysis (EDA)
- **Conversion Rate**: Approximately 30% of leads convert.
- **Key Findings**:
  - Professionals have the highest conversion rates compared to students or unemployed leads.
  - Website-first interactions yield higher conversions than Mobile App.
  - Higher profile completion (`High`) and longer `time_spent_on_website` strongly correlate with conversions.
  - Email activities and referrals are associated with higher conversion rates.
- Visualizations include histograms, boxplots, countplots, and correlation heatmaps to uncover patterns.

## Models and Performance
### 1. Decision Tree Classifier
- Trained with entropy criterion.
- Accuracy: ~80%.
- Pruned (max_depth=5) to improve recall for converted leads.
- Key Feature: `time_spent_on_website` is the most important predictor.

### 2. Random Forest Classifier (Recommended)
- Tuned using GridSearchCV with parameters:
  - `n_estimators`: [50, 100, 200]
  - `max_depth`: [5, 10, 15]
  - `min_samples_split`: [2, 5]
- Best Parameters: `n_estimators=100`, `max_depth=10`, `min_samples_split=5`.
- Performance Metrics (Test Set):
  - Accuracy: ~81%
  - F1-Score (Class 1): 0.64
  - Confusion Matrix:
    ```
    [[533  40]
     [124 145]]
    ```
- Preferred over Decision Tree due to better robustness and generalization.

## Actionable Insights and Recommendations
1. **Target Professionals**: Focus marketing on career-oriented content to engage professionals, who show the highest conversion rates.
2. **Improve Mobile App UX**: Lower conversion rates from Mobile App suggest usability issues; implement A/B testing to enhance navigation and content delivery.
3. **Enhance Email Nurturing**: Invest in personalized email sequences, as email activities are strongly linked to conversions.
4. **Promote Referrals**: Introduce referral incentive programs (e.g., discounts) to leverage high-conversion referrals.
5. **Encourage Profile Completion**: Use progressive profiling or incentives to achieve higher profile completion rates, which correlate with conversions.
6. **Deploy Random Forest Model**: Use the tuned Random Forest model for lead scoring, prioritizing leads with high `time_spent_on_website`.
7. **Lead Profile**: Likely converters are professionals over 40, with website-first interactions, high profile completion, and exposure to multiple channels (e.g., referrals, email).

## Project Structure
```
extraalearn-project/
├── Rasha_Abu_Rkab- Full Code Version - Potential Customers Prediction.ipynb  # Jupyter Notebook
├── README.md                           # Project documentation
├── requirements.txt                    # Python dependencies
```

## Contributors
- Rasha Abu Rkab (Author)

## License
This project is licensed under the MIT License.
