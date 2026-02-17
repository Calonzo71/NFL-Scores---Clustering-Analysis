# NFL-Scores---Clustering-Analysis
This project performs K-means clustering on NFL teams based on their offensive and defensive performance during the 2025 regular season (weeks 1-18). Teams are grouped into four distinct clusters that reveal patterns in team performance.


Methodology
Data Collection

Source: ESPN NFL API
Season: 2025 Regular Season
Weeks: 1-18
Metrics:

Average Points Scored (offensive performance)
Average Points Allowed (defensive performance)



Clustering Algorithm

Algorithm: K-Means Clustering
Number of Clusters: 4
Feature Scaling: StandardScaler (ensures both metrics contribute equally)
Random State: 42 (for reproducibility)

Cluster Descriptions
Cluster 0: Struggling Offenses
Teams with defensive strength but offensive challenges.
Cluster 1: The Rebuilding
Teams showing weaknesses on both sides of the ball.
Cluster 2: The Contenders
Elite teams with strong offensive and defensive performance.
Cluster 3: The Middle of the Pack
Teams with average performance across both metrics.
Project Structure
├── DataColumn_10-25_updated.ipynb    # Main analysis notebook
├── DataColumn.csv                     # Raw game data (generated)
└── README.md                          # This file
Getting Started
Prerequisites
bashpip install requests pandas matplotlib scikit-learn
Running the Analysis

Clone the repository

bashgit clone <your-repo-url>
cd <your-repo-name>

Open the Jupyter notebook

bashjupyter notebook DataColumn_10-25_updated.ipynb

Run all cells

The notebook will fetch data from ESPN's API
Perform clustering analysis
Generate visualizations



Customization
To analyze a different season or weeks, modify the data collection cell:
python# Change year or week range
weeks_to_fetch = list(range(1, 19))  # Weeks 1-18
df_week = get_weekly_scores(year=2025, weeks=w)
Visualizations
The notebook generates a scatter plot showing:

Each team's position based on points scored (x-axis) and points allowed (y-axis)
Color-coded clusters
Team labels for easy identification
Cluster centroids marked with 'X'

Interpretation:

Top-left quadrant: High scoring, low points allowed (elite teams)
Bottom-right quadrant: Low scoring, high points allowed (struggling teams)
Top-right quadrant: High scoring, high points allowed (shootout teams)
Bottom-left quadrant: Low scoring, low points allowed (defensive teams)

Key Insights
The clustering reveals:

Performance tiers among NFL teams
Offensive vs defensive trade-offs
Team similarities that may not be obvious from standings alone
Season-long trends rather than week-to-week fluctuations

Code Structure
1. Data Collection (get_weekly_scores)
Fetches game scores from ESPN API for specified weeks.
2. Data Preprocessing
Calculates average points scored and allowed per team.
3. Clustering

Scales features using StandardScaler
Applies K-means with k=4
Assigns teams to clusters

4. Visualization
Creates an annotated scatter plot with custom cluster names.
5. Summary Statistics
Prints cluster characteristics (averages, team counts).
Technical Details

Language: Python 3.11+
Libraries:

requests: API calls
pandas: Data manipulation
matplotlib: Visualization
scikit-learn: Machine learning (K-means, StandardScaler)



Data Schema
Raw Data (per game):

game_id: Unique game identifier
date: Game date
week: Week number
team: Team name
homeAway: Home or away status
Points_Scored: Points scored by team
Points_Allowed: Points allowed by team
opponent: Opponent team name

Aggregated Data (per team):

team: Team name
points_scored: Average points scored
points_allowed: Average points allowed
cluster: Assigned cluster ID


Data provided by ESPN NFL API
Clustering implementation using scikit-learn
