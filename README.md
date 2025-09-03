# Employee Sentiment Analysis — [YourName]

## Summary
This project labels raw employee messages as Positive/Negative/Neutral, performs exploratory data analysis, computes monthly sentiment scores and rankings, identifies flight-risk employees (>=4 negatives in any rolling 30-day window), and fits a linear regression to predict monthly sentiment scores.

## Usage / Setup
1. Create and activate a virtual environment.
2. Install dependencies:
pip install -r requirements.txt
3. Place `test.csv` or `test.xlsx` in the project root.
4. Open `employee_sentiment_analysis.ipynb` in JupyterLab and run cells in order.

## Outputs
- `labeled_data.csv`: messages with sentiment label.
- `monthly_employee_scores.csv`: monthly scores per employee.
- `employee_rankings.csv`: top-3 positive/negative per month.
- `flight_risks.csv`: employees flagged as flight risk.
- `sentiment_trend_lr_model.joblib`: trained linear regression model.
- `visualizations/`: plots supporting EDA.

## Methodology
- Sentiment labeling: VADER lexicon-based sentiment (compound score thresholds: >=0.05 positive, <=-0.05 negative, else neutral). Rule-based method chosen for reproducibility and speed.
- EDA: counts, message length distribution, monthly trends.
- Monthly scoring: Positive=+1, Negative=-1, Neutral=0 aggregated per employee per month.
- Ranking: top three positive and top three negative (tie-breaker: alphabetical order).
- Flight risk: any employee with `>=4` negative messages in any rolling 30-day period.
- Modeling: Linear Regression (sklearn) on aggregated employee-month features.

## Files to submit (zip)
- IPYNB, CSV outputs, visualizations, README, .env.example (if used).

