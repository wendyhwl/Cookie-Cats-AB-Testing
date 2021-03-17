# Cookie-Cats-AB-Testing

## Background & Description

[Cookie Cats](https://www.facebook.com/cookiecatsgame) is a hugely popular mobile puzzle game developed by [Tactile Entertainment](http://tactile.dk). It's a classic "connect three" style puzzle game where the player must connect tiles of the same color in order to clear the board and win the level. It also features singing cats. We're not kidding! As players progress through the game they will encounter gates that force them to wait some time before they can progress or make an in-app purchase. In this project, we will analyze the result of an A/B test where the first gate in Cookie Cats was moved from level 30 to level 40. In particular, we will analyze the impact on _player retention_. 

*Description from [DataCamp](https://www.datacamp.com/projects/184)*


## Business Problem
Decide whether to move the gate from level 30 to 40 by looking at the retention rates for both groups.

## The Data
The data is from 90,189 players that installed the game while the AB-test was running. The variables are:
- `userid` - a unique number that identifies each player.
- `version` - whether the player was put in the control group (*gate_30* - a gate at level 30) or the test group (*gate_40* - a gate at level 40).
- `sum_gamerounds` - the number of game rounds played by the player during the first week after installation
- `retention_1` - did the player come back and play 1 day after installing?
- `retention_7` - did the player come back and play 7 days after installing?
When a player installed the game, he or she was randomly assigned to either *gate_30* or *gate_40*.

## Detailed Steps & Analysis

[Cookie Cat: A/B Testing & Hypothesis Testing](https://github.com/wendyhwl/Cookie-Cats-AB-Testing/blob/main/ab_testing_analysis.ipynb)

## Summary Statistics

### General Summary

- Users play a total of 52 game rounds on average
- 3994 users never played the game after installing (4.5%)
- 55.5% of users quit the game after 1 day of installing (44.5% retention)
- 81% of users quit the game after 7 days of installing (19% retention)

### 1-Day Retention Comparison
- 44.8% of gate_30 users continue to play the game after 1-day
- 44.2% of gate_40 users continue to play the game after 1-day

--> gate_30 yields 0.6% higher 1-day rentention rate

### 7-Day Retention Comparison
- 19.0% of gate_30 users continue to play the game after 1-day
- 18.2% of gate_40 users continue to play the game after 1-day

--> gate_30 yields 0.8% higher 7-day rentention rate

## Conclusion

The question: 
- **Should we or should we not move the gate from level 30 to 40?** 
- **Does moving gate to level 40 has an impact on player retention?**


In short, we should **NOT** move the gate from level 30 to level 40.


Both 1-day and 7-day retentions are higher when the gate is set at level 30. Despite the slight differences, the Mann-Whitney U-test tells us that the A/B groups are not similar. Therefore, there is a statistical difference in the total game rounds played between moving gates from level 30 to level 40.


**Why is it better to keep the gate at 30?**


Naturally, we would think that placing the gate earlier may be why users quit the game since they are forced to either wait for a certain period or make an in-app purchase before proceeding to the next level. However, this can be explained by a psychological theory called *Hedonic Adaptation*.


Hedonic Adaptation is a human tendency to lose happiness to a life event or an activity quickly. The idea can also be understood as to how human has unlimited desires — a higher salary would increase our level of happiness for a while. However, we would soon be expecting more, bringing us back to the initial level of happiness.


By keeping the gate at level 30, we keep the users in the happiness loop and prevent them from quitting the game just because they got bored of it. Thus, users' level of happiness is prolonged when they are forced to take a break. Of course, if we were to find the optimal solution to this, there are other factors that we need to consider, such as the wait time, price of in-app purchases, ... etc.
