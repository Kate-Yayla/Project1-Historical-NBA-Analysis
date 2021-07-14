# The Winning Factors


![NBA Court](/Images/basketballcourt.png)

## Table of content

* [General info](#general-info)
* [Questions](#questions)
* [Data Sources](#data_sources)
    * [Preview](#preview)
* [APIs](#APIs)
* [Data Cleaning](#Data_Cleaning)
* [Data Visualization](#Data_Visualization)
* [Reports](#reports)
* [Setup](#setup)
* [Team](#team)
****

## **General info**

Project Proposal: How well can you predict the results of the games in the NBA using their data alone?

### Questions:

1. Can the Team Four Factor Rating of Basketball help in accurately determining the team’s win/success? Four Factors are:
    * Shooting – Effective Field Goal
    * Turnover – Turnover Rate
    * Rebound – Offensive Rebound Rate
    * Free Throw – Free Throw Rate
    * Team Four Factor Rating Formula = ((0.4\*eFG%) – (0.25\*TOV%) + (0.2\*ORB%) + (0.15\*FT%))

2. How does age of the player affect PER (Player Efficiency Rating)?
3. How does a player’s move (Top 10 only based on overall points) affect the new team’s winning percentage?

****

## **Data Sources**

* Individual Player Data: (https://www.kaggle.com/drgilermo/nba-players-stats?select=Seasons_Stats.csv
)  
* Team Data:  (https://data.world/gmoney/nba-team-records-by-year/workspace/file?filename=Historical+NBA+Performance.xlsx
)  
Notes: Limiting our sample to the years of 1986-2017.
