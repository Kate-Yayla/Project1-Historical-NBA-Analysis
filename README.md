# The Historical NBA Analysis

![NBA Court](/Images/basketballcourt.png)

## Table of content

* [General info](#general-info)
* [Questions](#questions)
* [Parameters](#Parameters)
* [Data Sources](#data_sources)
    * [Preview](#preview)
* [Data Cleaning](#Data_Cleaning)
* [Data Visualization](#Data_Visualization)
* [Reports](#reports)
* [Setup](#setup)
* [Team](#team)

## General info

In this project, we analyzed the NBA history with the parameters of players age, the winning percentage of teams, PER (players efficieny rating), minutes played between 1986-2017 and used Python jupyter notebook for creating codes.

## Questions

1. Can the Team Four Factor Rating of Basketball help in accurately determining the team’s win/success?
2. How does age of the player affect PER (Player Efficiency Rating)?
3. How does a player’s move (Top 10 only based on overall points) affect the new team’s winning percentage?
4. How to find top 50 or 100 players and their performance based on minutes played?

## Parameters

| Parameters | Against |
| --------- | -------- |
|Four Factors | Team win/success
|Age | Players Efficiency Ratings (PER)
|Player's Move | New Teams winning percentage
|Player's Performance | Time

## Data Sources

### Four factors contribution to NBA Teams success

* (https://www.kaggle.com/drgilermo/nba-players-stats?select=Seasons_Stats.csv)

* (https://data.world/gmoney/nba-team-records-by-year/workspace/file?filename=Historical+NBA+Performance.xlsx)

### Additional sources

* (https://www.sportsgamblingpodcast.com/2020/04/20/nba-most-valuable-statistic/)
* (https://pypi.org/project/nba-api/)
  Notes: Limiting our project between 1986-2017.

### Preview of the NBA data set

![Preview of our Data](/Visualizations/playerData.PNG)

## Data Cleaning

* **complete_nba_data**: Merged team data with city data and added players data in csv files to work on first question and related visualizations and arranged the data between 1986 to 2017 and cleaned up dataset to use as main data.

* **age_player_data**: Create a dataframe using complete_nba_data  to find age effects PER (Player Efficiency Rating). Gathered the data from complete_nba_data and use "Year", "Player", "Age", "G", "MP","PER" as column to find out top players.


### Cleaned NBA data set

![Cleaned Data](/Visualizations/Cleaneddata.PNG)

## Data Visualization

* **Impact of Four Factor Ratings on Winning Percentage**: Analyzed the impact of four factor ratings against the winning percentage and plot both parameters. Analyzed 2017 Team performance based on four factors compare with our prediction with actual winning percentage and found Difference in Winning Percentages.Statistical Analysis and table done on the resulting data.

* **Impact of age based on PER**: Analyzed players age data and found the quartiles, IQR, upper and lower bound to compare the players who would be on top 10 based on players median. 

* **Impact of players move based on points**: Analyzed players move based on points and winning percentage using player_points_data. Found top 10 players based on points and impact of their move to other team.

## Visualized four factors ratings impacts on winning percentage

![Winning Percentage]()

* There is a positive correlation with Four Factors Ratings and Winning Percentage.

## Visualized ages impacts on Player Efficiency Rating (PER)

![Player Efficieny]()

* There is a slightly positive correlation with ages and Player Efficiency Rating (PER).

## Visualized Player Changing Teams (Top 10)

### Top 10 Players

<img src="Visualizations\top%2010.png" alt="drawing" width="500"/>

### Tracy McGrady Teams

<img src="Visualizations/tmcg%20teams.png" alt="drawing" width="500"/>

### Tracy McGrady Team Changes

<img src="Visualizations/tmcg%20changes.png" alt="drawing" width="500"/>

### Reports

    # Observations Question 3 – How does a Player&#39;s move to a new team effect the winning Percentage of the New Team. Using just the top 10 unique points leaders for the 1986-2017 season.

    1. Our expectation would be the new team would improve.
      1. In most cases that is exactly what happen.
      2. In the cases they did not, some of the players like Tracy McGrady were traded / moved several times in a year and his teams did not improve.
      3. The Top 10 had 2 players Kobe Bryant andRussell Westbrook that did not move if we had more time, we could have replaced them with the next best player that had a move. This would have help in verifying the outcome to back up out Theroy.
      4. The Top 10 had 1 player Kevin Durant that did had a move to a brand new team OKC. This caused a bug that if we had more time we would have fixed, Due to OKC being a new team we had not data on new team. The query should have returned only on Team change with a Message that This is a New Team and no winning Percentage was found. The code displays the current year data for the new team instead.
      5. The Top 10 had 2 players Alex English and Dwayne Wade that did not have a positive outcome. When they went to the new team they were both at the end of their careers.
      6. The Top 10 had 1 player Dominique Wilkins that had mixed results. He was on 2 different teams in 1994 he was traded from and to the same team the Atlanta Hawks. He also was traded again at the end of his career to Seattle, and they were an awfully bad team before he got there.
    
    1. Based on the finding we would need more Data to deal with the outliers.
    2. If we had more time, we could have tried to a line series plot for each player with years on the bottom and age on side.
    3. If we had more time, we could have used Points as well as winning % to see how many more or less points they averaged.
    4. If we had more time, we could of we could have looked at Player Efficiency Rating over that time
    5. If we had more time, we could have used a Confusion Matrix to help Validate the outcome.
    
        - Here is the process and an example
      - You need a test dataset or a validation dataset with expected outcome values.
      - Make a prediction for each row in your test dataset.
      - From the expected outcomes and predictions count:
      - The number of correct predictions for each class.
      - The number of incorrect predictions for each class, organized by the class that was predicted. ![](RackMultipart20210722-4-197p35x_html_c84638979ef26478.jpg)
### Setup

Required dependencies:

``` Python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import scipy.stats as stats
```

### Team

Created by:

* [@jaybdhruv](https://github.com/)
* [@MondragB](https://github.com/MondragB)
* [@sammyschapps87](https://github.com/)
* [@DennisPSmith5676](https://github.com/)
* [@Kate-Yayla](https://github.com/)