# Discovering Plate Approach Patterns Among Major League Baseball (MLB) Batters Through Data Mining

![Python Version](https://img.shields.io/badge/python-3.13-blue.svg)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## Repository Structure

- data/ -> dataset used for analysis
- notebooks/ -> Jupyter notebook with full analysis
- docs/ -> milestone reports
- graphs/ -> miscellaneous chart images
- requirements.txt -> Python dependencies required to run the project
- README.md -> Project overview and instructions

## Run Project in Browser

Allow 1-2 minutes for the environment to build:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Chris83848/MLB-Data-Mining/HEAD)

## How To Run

Clone the repository:

git clone https://github.com/Chris83848/MLB-Data-Mining
cd MLB-Data-Mining

Install Dependencies:

pip install -r requirements.txt

Launch Jupyter Notebook:

jupyter notebook

Then open the notebook in notebooks/ and run all cells.

## Summary

This project applies clustering techniques (K-Means) and anomaly detection to MLB hitter data to identify patterns in plate discipline and highlight common exceptions and unique players. Batters are grouped based on metrics such as Z-Swing% and O-Swing%, revealing distinct approaches at the plate. The biggest insight is that plate discipline alone does not predict offensive performance, and that anomalies are independent of one another, underscoring the multitude of ways to succeed offensively and the overall complexity of hitting.

## Example Visualization

<img src="graphs/Cluster_Chart.png" alt="Alt text" width="1000">


\## Project Description

This project examines patterns in MLB batters' plate approaches using plate approach statistics. The goal is to uncover natural groupings of players based on their plate discipline metrics, including swing and contact rates. Observed and expected performance results will also be analyzed across the groups to measure their effectiveness and outcome variance. Rather than focusing on prediction, this project emphasizes pattern discovery through data mining.

The dataset was first inspected and preprocessed, revealing no missing or duplicate values. Univariate analysis showed generally unimodal distributions of features with slight skewness and manageable outliers, while bivariate and multivariate analyses revealed strong relationships among swing rates, contact rates, strikeouts, and performance metrics, justifying a multivariate clustering approach.

Feature engineering included creating a performance differential metric to measure under- and overperformance relative to expected outcomes. Redundant features were also removed based on correlation findings. All clustering variables were standardized to ensure proportional scaling before algorithm implementations.

K-Means clustering was selected due to the approximately normal structure of the dataset and the assumptions of spherical clusters. Three clusters were determined using the elbow method and silhouette scores.

Anomaly detection located players who deviated from their respective clusters, both structurally through plate approaches and performance-wise through departures from expected performance results. Euclidean cluster centroid distances were calculated for these identifications, followed by flagging anomalies within the upper 5% of each respective calculation, ensuring appropriate anomalies without being overly strict or permitting.


\## Identified Plate Approach Clusters

Selective Batters (196 players):
These batters hold the lowest swing rates, the highest walk and strikeout rates, and the strongest overall offensive production. This group notably underperforms expected statistics, indicating untapped potential or unluckiness from underlying statistics. Despite high strikeout totals, this group yields the highest average offensive value.

Swing-Heavy Batters (251 players):
These batters hold the highest swing rates, the lowest walk rates, and elevated strikeouts. Their performance and expected performance outcomes tend to align closely with league averages, implying a high-variance, aggression-based approach.

Contact Batters (222 players):
These batters hold the highest contact rates and the lowest strikeout rates. They rely on putting the ball in play and exhibit very similar performance metrics as Swing-Heavy Batters.


\## Identified Structural Anomalies

Outliers (35 players):
These batters demonstrate extreme cases of their plate approach within each cluster. They are farthest from their cluster centroid by Euclidean distance and exhibit either dramatically elevated or reduced values for one or more attributes compared to the majority of points in their cluster. They still align with the conditions of their cluster, but in a much more exaggerated way. For example, a Swing-Heavy Batter who owns extremely high swing rates compared to the rest of the grouping. Outliers remained consistent and equally distributed across all clusters.

Hybrids (35 players):
These batters represent edge cases and sit between two clusters, reflecting a mixed plate approach. Their cluster centroid distances between the two closest clusters are nearly identical. Therefore, they do not neatly fit under a single classification, and assigning them to just one misrepresents them and their abilities. The plate approach they own is a blend, such as a player assigned as a Selective Batter who also holds the contact rates seen in the Contact Batters cluster. Hybrid players remained consistent and equally distributed across all clusters.


\## Identified Performance Anomalies

Overperformers (20 players):
These batters hold extremely positive differences between their wOBA and xwOBA, meaning they significantly overperformed their expected statistics based on how well they hit the ball across the course of the season. Because these batters hold higher wOBA values than xwOBA values, this means that they experienced favorable luck and variance, since these are the factors introduced by wOBA. Contact Batters held the most overperformers, with ten players in total, suggesting that frequent contact increases the chances of good luck for batters, while Swing-Heavy Batters only held four of these players.

Underperformers (14 players):
Similar to Overperformers, these batters show extremely negative differences between their wOBA and xwOBA instead, meaning they significantly underperformed their expected statistics. Underperformers hold lower wOBA values than xwOBA values, indicating bad luck throughout the course of the given season. These batters were evenly distributed across the cluster, with no grouping clearly susceptible to them, suggesting that bad luck is more of a fixed variable than good luck. There is not much difference between players who overperformed and those who underperformed, aside from cluster denotation, indicating the unpredictable nature of performance anomalies.


\## Key Findings

- MLB hitters naturally separate into three distinct plate-approach archetypes: selective, contact-based, swing-based
- Plate discipline does not necessarily correspond to reduced strikeouts
- Strikeout rate alone does not strongly impact weighted on-base average
- Selective batters demonstrate the highest average offensive production despite higher strikeout rates
- Observed and expected performance statistics differentiate most strongly within the selective cluster
- Players can excel under any cluster category
- Batters exist in each cluster who showcase extreme instances of their respective plate approaches through one or multiple pronounced attributes
- Batters exist throughout the dataset who do not fit squarely into one cluster, taking on a blend of plate approaches instead
- Positive variance in baseball is mostly external, but can be slightly influenced through frequent contact with balls in play
- Poor variance in baseball is constant and unpredictable in nature
- Player anomalies are independent of each other, having no relation to much else
- Unnatural plate approaches are just as likely to result in similar performance results and standard ones


\## Dataset

The dataset used in this project is taken from the Baseball Savant MLB leaderboard and includes qualified batters from the 2021-2025 seasons.

https://baseballsavant.mlb.com/



\## Author

Christopher Harris

