\# Discovering Plate Approach Patterns Among Major League Baseball (MLB) Batters Through Data Mining



\## Project Description

This project examines patterns in MLB batter approach when hitting by using plate approach statistics. The goal is to uncover natural groupings of players based on their plate discipline metrics, including swing and contact rates. Observed and expected performance results will also be analyzed across the groups to measure their effectiveness and outcome variance. Rather than exploring prediction, pattern discovery is emphasized in this project through data mining. 

The dataset was first inspected and preprocessed, revealing no missing or duplicate values. Univariate analysis showed generally unimodal feature distributions with slight skewness and manageable outliers, while bivariate and multivariate analysis revealed strong relationships between swing rates, contact rates, strikeouts, and performance metrics, justifying a multivariate clustering approach.

Feature engineering included creating a performance differential metric to measure under- and overperformance relative to expected outcomes. Redundant features were also removed based on correlation findings. All clustering variables were standardized to ensure proportional scaling before algorithm implementation.

K-Means clustering was selected due to the approximately normal structure of the dataset and the assumptions of spherical clusters. Three clusters were determined using the elbow method and silhouette scores.


\## Identified Plate Approach Clusters

Selective Batters (196 players)
These batters hold the Lowest swing rates, the highest walk and strikeout rates, and the strongest overall offensive production. This group notably underperforms expected statistics, indicating untapped potential or unluckiness from underlying statistics. Despite high strikeout totals, this group yields the highest average offensive value.

Swing-Heavy Batters (251 players)
These batters hold the highest swing rates, the lowest walk rates, and elevated strikeouts. Their performance and expected performance outcomes tend to align closely with league averages, implying a high-variance, aggression-based approach.

Contact Batters (222 players)
These batters hold the highest contact rates and the lowest strikeout rates. They rely on putting the ball in play and exhibit very similar performance metrics as Swing-Heavy Batters.


\## Key Findings

- MLB hitters naturally separate into three distinct plate-approach archetypes: selective, contact-based, swing-based
- Plate discipline does not necessarily correspond to reduced strikeouts.
- Strikeout rate alone does not strongly impact weighted on-base average.
- Selective batters demonstrate the highest average offensive production despite higher strikeout rates.
- Observed and expected performance statistics differentiate most strongly within the selective cluster.
- Players can excel under any cluster category


\## Dataset

The dataset used in this project is taken from the Baseball Savant MLB leaderboard and includes qualified batters from the 2021-2025 seasons.

https://baseballsavant.mlb.com/



\## Author

Christopher Harris

