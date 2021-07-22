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

# General info

In this project, we analyzed the NBA history with the parameters of players age, the winning percentage of teams, PER (players efficieny rating), minutes played between 1986-2017 and used Python jupyter notebook for creating codes.

# Questions

1. Can the Team Four Factor Rating of Basketball help in accurately determining the team’s winning percentage? Does the data set we are using needs to be adjusted for accurate analysis?
2. How does age of the player affect PER (Player Efficiency Rating)?
3. How does a player’s move (Top 10 only based on overall points) affect the new team’s winning percentage?
4. Is the Minutes Played variable positively correlated with a players core performance variables? (i.e: 3pts, 2pts, blocks, steals, ect.)

# Parameters

| Parameters | Against |
| --------- | -------- |
|Four Factors Ratings | Team's winning percentage
|Age | Players Efficiency Ratings (PER)
|Player's Move | New Team's winning percentage
|Minutes Played | 3pts, 2pt, Stl, Blk, Drb, Orb, Ft

# Data Sources

### Four factors contribution to NBA Teams success

* (https://www.kaggle.com/drgilermo/nba-players-stats?select=Seasons_Stats.csv)

* (https://data.world/gmoney/nba-team-records-by-year/workspace/file?filename=Historical+NBA+Performance.xlsx)

### Additional sources

* (https://www.sportsgamblingpodcast.com/2020/04/20/nba-most-valuable-statistic/)
* (https://pypi.org/project/nba-api/)
  Notes: Limiting our project between 1986-2017.

### Preview of the NBA data set

![Preview Data](/Visualizations/previewdata.PNG)

# Data Cleaning

* **complete_nba_data**: Merged team data with city data and added players data in csv files to work on first question and related visualizations and arranged the data between 1986 to 2017 and cleaned up dataset to use as main data.

* **age_player_data**: Create a dataframe using complete_nba_data  to find age effects PER (Player Efficiency Rating). Gathered the data from complete_nba_data and use "Year", "Player", "Age", "G", "MP","PER" as column to find out top players.


# Cleaned NBA data set

![Cleaned Data](/Visualizations/Cleaneddata.PNG)

# Data Visualization

* **Impact of Four Factor Ratings on Winning Percentage**: Analyzed the impact of Four Factor ratings on team's Winning Percentage by performing linear regression and scatter plot. We also calculated Coefficient of Correlation (r) to see how Four Factors and Team's winning percentage are correlated. We calculated residuals and plotted residuals with predicted values to see if the data that we are working on needs adjustment or not.

* **Impact of age based on PER**: Analyzed players age data and found the quartiles, IQR, upper and lower bound to compare the players who would be on top 10 based on players median. 

* **Impact of players move based on points**: Analyzed players move based on points and winning percentage using player_points_data. Found top 10 players based on points and impact of their move to other team.
* **Impact of minutes played on key varibles**: Took the natural log of all varibles in order to see elasticity through regression analysis. 

# Reports

### <ins>**Q1:Analysis of Impact of Four Factors Ratings on Team's Winning Percentage**</ins>

![Correlation of Effective Field Goal and Winning Percentage](/Visualizations/EFG-WP.jpg)

![Coefficient eFG](/Visualizations/Coff-EFG-WP.PNG)

![Correlation of Tunrover Rate and Winning Percentage](/Visualizations/TR-WP.jpg)

![Coefficient TOV](/Visualizations/coff-TR-WP.PNG)

![Correlation of Offensive Rebound and Winning Percentage](/Visualizations/OR-WP.jpg)

![Coefficient ORB](/Visualizations/Coff-OR-WP.PNG)

![Correlation of Free Throw Rate and Winning Percentage](/Visualizations/FT-WP.jpg)

![Coefficient FT](/Visualizations/Coff-FTR-WP.PNG)

![Reports](Visualizations\EffectiveFieldGoal.jpg)

![Reports](Visualizations\CoefficienteFG.jpg)

![Reports](Visualizations\TunroverRate.jpg)

![Reports](Visualizations\CoefficientTOV.jpg)

![Reports](Visualizations\OffensiveRebound.jpg)

![Reports](Visualizations\CoefficientORB.jpg)

![Reports](Visualizations\FreeThrowRate.jpg)

![Reports](Visualizations\CoefficientFT.jpg)

We understand from these scatter plots that individual factors have a very weak correlation with the winning percentage as Coefficient of Correlation (r) is very low in all the cases.

Hence, we then perform linear regression on the Four Factor Rating to see if we get better correlation to Team’s winning percentage compared to individual factors.

![Correlation-FourFactorRating-WinningPercentage](/Visualizations/FFR-WP.jpg)

![Coefficient Four Factor Ratings](/Visualizations/COFF-FFR-WP.PNG)

From Scatter Plot and Linear Regression analysis, we can observe that Four Factor Rating has a better correlation to the team’s winning percentage than individual factors. 

For a healthy positive correlation, it is important to have Coefficient of Correlation (r) = 0.9. 

r is 0.377 in this case which indicates that it is a weak positive correlation. **This indicates that Four Factor Rating is not an efficient parameter in determining the winning percentage of the team. There are several other external factors that needs to consider to accurately predict the winning percentage.**

## **To check if data set we are using needs to be adjusted for accurate analysis**

We calculate residuals which are difference between predicted winning percentages and observed winning percentages. Residuals are essentially errors in our predictions. A positive residual indicates that our prediction was lower than expected while negative residual indicates that our prediction was higher than expected.

![Residual vs Predicted values](/Visualizations/Res-Pre.jpg)

We then plot a scatter plot of predicted values against residuals to check for the pattern. If we get any kind of pattern in this scatter plot, it means that we can predict our residual based on our predicted values. This means that our data model is not accurate, and it will require some transformation of the data.

From this Scatter plot, we can see that slope is 0 and linear regression is a horizontal line. This means that there is no correlation in the predicted values and residuals. **The occurrences or residuals are in a randomized order. This concludes that the data model we were working is an accurate data model.**

### <ins>**Q2: Analysis of  Player's age affecting his PER (Player Efficiency Rating)?**</ins>

![Correlation of Age and PER](/Visualizations/AgePER.jpg)

From this scatter plot and the value of r, we can conclude that there is a very weak positive correlation between Age and PER. **This is not a sufficient data to predict that age of the player affects his PER.**

But we can see it here that more datapoints are recorded between the age 20 and 30 and a very few datapoints are recorded after the age of 30. This also infers a player’s PER will reach a peak between these years.

### <ins>**Q3: Analysis of Player's move affecting the winning percentage of his new team**</ins>

#### Top 10 Players (Based on Points)

<img src="Visualizations\top%2010.png" alt="drawing" width="500"/>

#### Tracy McGrady Teams

<img src="Visualizations/tmcg%20teams.png" alt="drawing" width="500"/>

#### Tracy McGrady Team Changes

<img src="Visualizations/tmcg%20changes.png" alt="drawing" width="500"/>


Our expectation would be the new team would improve.

* **In most cases that is exactly what happen.**
* **In the cases they did not, some of the players like Tracy McGrady were traded / moved several times in a year and his teams did not improve.**
* **The Top 10 had 2 players Kobe Bryant and Russell Westbrook that did not move. If we had more time, we could have replaced them with the next best player that had a move. This would have help in verifying the outcome to back up out Theory.**
* **The Top 10 had 1 player Kevin Durant that did had a move to a brand new team OKC. This caused a bug that if we had more time we would have fixed, Due to OKC being a new team we had no data on new team's previous winning percentage. The query should have returned only on Team change with a message that "This is a New Team and no winning Percentage was found". The code displays the current year data for the new team instead.**
* **The Top 10 had 2 players Alex English and Dwayne Wade that did not have a positive outcome. When they went to the new team they were both at the end of their careers.**
* **The Top 10 had 1 player Dominique Wilkins that had mixed results. He was on 2 different teams in 1994 he was traded from and to the same team the Atlanta Hawks. He also was traded again at the end of his career to Seattle, and they were an awfully bad team before he got there.**

Based on the finding we would need more Data to deal with the outliers.

* If we had more time, we could have tried to a line series plot for each player with years on the bottom and age on side.

* If we had more time, we could have used Points as well as winning % to see how many more or less points they averaged.

* If we had more time, we could of we could have looked at Player Efficiency Rating over that time

* If we had more time, we could have used a Confusion Matrix to help Validate the outcome.

![Confusion](/Images/confusion.jpg)

Here is the process and an example

* You need a test dataset or a validation dataset with expected outcome values.
* Make a prediction for each row in your test dataset.
* From the expected outcomes and predictions count:
* The number of correct predictions for each class.
* The number of incorrect predictions for each class, organized by the class that was predicted.

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

* [@jaybdhruv](https://github.com/jaybdhruv)
* [@DennisPSmith5676](https://github.com/DennisPSmith5676)
* [@Kate-Yayla](https://github.com/Kate-Yayla)
* [@MondragB](https://github.com/MondragB)
* [@sammyschapps87](https://github.com/sammyschapps87)
