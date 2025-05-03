Formula 1 Race Winner Prediction Project
Objective
Develop a supervised binary classification model to predict whether a Formula 1 driver will finish in 1st position (win the race) based on features such as starting grid position, team, track, and driver characteristics.
Relevance

Teams: Optimize race strategies.
Fans: Enhance engagement through predictions.
Analysts: Support betting and performance analysis.
The dataset (Formula1_2024season_raceResults.csv) contains race results from the 2024 season, with key predictors like starting grid position and team.

Problem Type
Binary classification:

is_winner = 1: Driver finishes 1st.
is_winner = 0: Driver does not finish 1st.

Data Preparation
Dataset Description

Rows: ~480 (20 drivers × 24 races).
Columns:
Track: Race location (e.g., Bahrain, Monaco).
Position: Finishing position (1 to 20, or DQ, NC).
No: Driver number.
Driver: Driver name.
Team: Team name.
Starting Grid: Starting position (1 to 20).
Laps: Number of laps completed.
Time/Retired: Finishing time or DNF status.
Points: Points earned.
Set Fastest Lap: Whether driver set fastest lap (Yes/No).
Fastest Lap Time: Fastest lap time.



Exploratory Data Analysis (EDA)

Class Distribution: Visualize is_winner to confirm ~5% winners.
Starting Grid vs. Winning: Plot Starting Grid vs. is_winner to verify correlation of lower grid positions (e.g., 1 or 2) with wins.
Team Performance: Bar plot of average finishing position by team.
Driver Performance: Bar plot of win counts by driver.
Track Analysis: Check if specific tracks favor certain teams/drivers.

Expected Insights

Starting Grid: Lower positions (e.g., 1 or 2) strongly predict wins.
Team Strength: Teams like Red Bull and Ferrari have high positive SHAP values.
Driver Win Rate: Drivers like Verstappen significantly impact predictions.

Ethical Considerations

Bias: Model may favor dominant teams (e.g., Red Bull, Ferrari), marginalizing smaller teams like Haas.
Fairness: Predictions could influence betting or team strategies, creating unfair expectations for drivers.
Transparency: SHAP values ensure stakeholders understand prediction rationale.
Data Privacy: Public race data poses no privacy concerns.

Challenges and Limitations

Class Imbalance: ~5% winners may reduce recall for is_winner = 1.
Feature Limitations: No real-time data (e.g., pit stops, weather).
Generalization: Model may not extend to future seasons with new regulations.
Previous Error: ValueError from empty training data due to flawed sampling. Resolved using train_test_split with test_size=0.1.

Future Work

Add Features: Include qualifying times, pit stop data, weather.
Real-Time Predictions: Use live race data.
Multi-Class Prediction: Predict top 3 finishers.
Deployment: Create a web app for fan predictions.

Requirements

Python 3.x
Libraries: pandas, scikit-learn, matplotlib, seaborn, shap
Dataset: Formula1_2024season_raceResults.csv

Usage

Load and preprocess the dataset.
Perform EDA to visualize key relationships.
Train a binary classification model (e.g., XGBoost, Random Forest).
Evaluate using metrics like precision, recall, and F1-score.
Interpret predictions using SHAP values.

Contact
For questions or contributions, contact the project maintainer.
