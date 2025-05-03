<h1>Formula 1 Race Winner Prediction Project</h1>
<hr>

<h2>Objective</h2>
<p>Develop a supervised binary classification model to predict whether a Formula 1 driver will finish in 1st position (win the race) based on features such as starting grid position, team, track, and driver characteristics.</p>
<hr>

<h2>Relevance</h2>
<ul>
    <li><b>Teams:</b> Optimize race strategies.</li>
    <li><b>Fans:</b> Enhance engagement through predictions.</li>
    <li><b>Analysts:</b> Support betting and performance analysis.</li>
</ul>
<p>The dataset (Formula1_2024season_raceResults.csv) contains race results from the 2024 season, with key predictors like starting grid position and team.</p>
<hr>

<h2>Problem Type</h2>
<p>Binary classification:</p>
<ul>
    <li><code>is_winner = 1</code>: Driver finishes 1st.</li>
    <li><code>is_winner = 0</code>: Driver does not finish 1st.</li>
</ul>
<hr>

<h2>Data Preparation</h2>
<h3>Dataset Description</h3>
<ul>
    <li><b>Rows:</b> ~480 (20 drivers × 24 races).</li>
    <li><b>Columns:</b></li>
    <ul>
        <li><b>Track:</b> Race location (e.g., Bahrain, Monaco).</li>
        <li><b>Position:</b> Finishing position (1 to 20, or DQ, NC).</li>
        <li><b>No:</b> Driver number.</li>
        <li><b>Driver:</b> Driver name.</li>
        <li><b>Team:</b> Team name.</li>
        <li><b>Starting Grid:</b> Starting position (1 to 20).</li>
        <li><b>Laps:</b> Number of laps completed.</li>
        <li><b>Time/Retired:</b> Finishing time or DNF status.</li>
        <li><b>Points:</b> Points earned.</li>
        <li><b>Set Fastest Lap:</b> Whether driver set fastest lap (Yes/No).</li>
        <li><b>Fastest Lap Time:</b> Fastest lap time.</li>
    </ul>
</ul>
<hr>

<h2>Exploratory Data Analysis (EDA)</h2>
<h3>Class Distribution</h3>
<p>Visualize <code>is_winner</code> to confirm ~5% winners.</p>
<h3>Starting Grid vs. Winning</h3>
<p>Plot Starting Grid vs. <code>is_winner</code> to verify correlation of lower grid positions (e.g., 1 or 2) with wins.</p>
<h3>Team Performance</h3>
<p>Bar plot of average finishing position by team.</p>
<h3>Driver Performance</h3>
<p>Bar plot of win counts by driver.</p>
<h3>Track Analysis</h3>
<p>Check if specific tracks favor certain teams/drivers.</p>
<hr>

<h2>Expected Insights</h2>
<ul>
    <li><b>Starting Grid:</b> Lower positions (e.g., 1 or 2) strongly predict wins.</li>
    <li><b>Team Strength:</b> Teams like Red Bull and Ferrari have high positive SHAP values.</li>
    <li><b>Driver Win Rate:</b> Drivers like Verstappen significantly impact predictions.</li>
</ul>
<hr>

<h2>Ethical Considerations</h2>
<h3>Bias</h3>
<p>Model may favor dominant teams (e.g., Red Bull, Ferrari), marginalizing smaller teams like Haas.</p>
<h3>Fairness</h3>
<p>Predictions could influence betting or team strategies, creating unfair expectations for drivers.</p>
<h3>Transparency</h3>
<p>SHAP values ensure stakeholders understand prediction rationale.</p>
<h3>Data Privacy</h3>
<p>Public race data poses no privacy concerns.</p>
<hr>

<h2>Challenges and Limitations</h2>
<h3>Class Imbalance</h3>
<p>~5% winners may reduce recall for <code>is_winner = 1</code>.</p>
<h3>Feature Limitations</h3>
<p>No real-time data (e.g., pit stops, weather).</p>
<h3>Generalization</h3>
<p>Model may not extend to future seasons with new regulations.</p>
<h3>Previous Error</h3>
<p>ValueError from empty training data due to flawed sampling. Resolved using <code>train_test_split</code> with <code>test_size=0.1</code>.</p>
<hr>

<h2>Future Work</h2>
<h3>Add Features</h3>
<p>Include qualifying times, pit stop data, weather.</p>
<h3>Real-Time Predictions</h3>
<p>Use live race data.</p>
<h3>Multi-Class Prediction</h3>
<p>Predict top 3 finishers.</p>
<h3>Deployment</h3>
<p>Create a web app for fan predictions.</p>
