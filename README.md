## Who will be the next NBA MVP winner?

Basketball is one of the most popular sports in the world, and NBA represents the highest level of playing the sport. So the MVP winner from NBA is the best player of the basketball in that year. I know everyone has their own MVP in their mind, but do you think it is possible using the stats of passing MVP to predict the future MVP?

![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/nextmvp.jpg "nextmvp?")

## Data Description 

All the stats used in this project are obtained from [Basketball reference](https://www.basketball-reference.com/leagues/NBA_2019_per_game.html). There are three sets of data used in this project. First one is named MVP which is included pass years' MVP winners and some non-MVP players. This dataset is used to train the model which I will use to predict the MVP winner. The other two datasets are the stats of all players in season 2018 and season 2019(As of Nov 30th). The stats included the name of player, age, team, game played, points per game, assists per game, steals per game, blocks per game, percent field goals, percent three points, percent free throws, win share, win share per 48 minutes, and overall percent team wins.


## Explore the Data

Before we deciding on what kind of model is suitable for our prediction of MVP, I graphed the data to visualize the diffferences between MVP and the non-MVP. The following code was used:

```yml
sns.pairplot(mvp, x_vars=['PTS','WS/48','MP','TW','G%','G','Age','WS'], y_vars='Title', height=7, aspect=0.7)
```

The relationship shows as follow: 
![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/data.png "relationships")

From the visulization of the relationships, I think the factors impact on MVP winners are points, WS, WS/48, minutes played per game, percent team wins, and game played. 


## Model the Data

Two different models used to predict the future MVP. The first one is Support-Vector Clustering(SVC) with the poly kernel. By changing the gamma value, the model could have a better accuracy. I used 37 MVP winners and 46 non-MVP with all the factors I have to fit the model. The other model I used is logistic regression which I have chosen the factors with higher impacts based on the visulization during the explore the data. 


## As of Result

First I used both model to "predict" the MVP winner in 2018 season which we already know is Giannis Antetokounmpo. By using SVC with a gamma of 0.002( the best gamma I could find manually), the model predicted 4 players could be the MVP which included Giannis the MVP, James Harden, Nikola Jokic, and Damian Lillard. All four of them were actual MVP canadids from last season.

![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/svc2018.png "prediction with SVC")

For the logistic regression model, it predicted Giannis and 14 other great players as MVP.

![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/log2018.png "prediction with LOG")

I think SVC has a better accurcy than logistic regression model, but both models have predicted the actual MVP winner in their results.

Now I want to predict the MVP for the current on-going season. I used the data as of Noverber 30th to predict the MVP. 
For SVC model with gamma of 0.0214, it predicted either Luka Doncic or LeBron James would be the MVP winner. Personally I also think one of these two will be the MVP.

![alt text](https://github.com/baitongc/Chen-Project/blob/master/svc2019.png "prediction with SVC for 19-20")

For the regression model, it predicted 15 players as the MVP for the 2019-2020 season which most of them are in the MVP canadid lists.

![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/log2019.png "prediction with log for 19-20")










