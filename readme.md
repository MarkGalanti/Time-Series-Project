# Mark Galanti's Stat 153 Project
## The Dataset
For my final project I chose to analyze the data from NBA player Lebron James. Specifically I am looking at a theorectical value called Effort to Win (or for short E2W). The data is from each game Lebron James played from 2003 up until 2019 and he is given a value for how hard it was for him to win that game. 

And this is what the data look like 

![image](https://github.com/MarkGalanti/153project/blob/master/e2w_1.png)

## The Goal
I want to be able to predict the E2W for Lebron's next 10 games. And to do this I need to fit the data as best as I possibly can. 

There are 3 main components when it comes to fitting a model to time series data.
1. Trend
2. Seasonality
3. Noise

And before I can predict time points beyond the data I need to make sure I have these three things acounted for.

## The Method
First I will do something called "Exploratory Data Analysis" (EDA). This means I look at the data for what it is and try to understand it. EDA will allow me to find the 3 components needed to understand this data set.

### 1. Trend
Simply looking at the data as it relates to time sometimes lets us understand the trend in the data. As we can see in the above plot of all the data points the average of the data tends to decrease overtime. Seeing this allows me to make the assumption that the data is linear overtime. Meaning Lebron will require less E2W as time goes on. Maybe the team is getting better while he gets older. A reliable way to get rid of a dataset's trend is called first differencing and that is subtracting time step 2 from 1 and so forth. And this becomes the new data set. So the difference between the each step will cause any linear trend to disappear and allow us to predict better. 

### 2. Seasonality
Continuing on intuition, things like domain knowledge can really help your model. Domain knowledge is basically understanding the data I'm working with. In this case its basketball, more specifically the NBA. Knowing something about the NBA can give insight into how to make my model fit future data points better. I feel comforatble making the assumption that the NBA is very competitive and all the teams are good and Lebron and the rest of the team will be trying to win all the time, every game. This leads me to believe that the seasonality of this data set is zero or negligible. So for this dataset we do not have to worry about seasonality

### 3. Noise
This is the money maker in time series analysis. The ultimate goal is to dumb down a data set to noise and ideally White Noise. What is noise you ask? Noise is basically a random number generated from a well studied statistical distribution. White Noise for example is purely theoretical and basically will never actually exist in nature, but the idea is if X is a white noise random variable it will fluctuate in even directions (positive and negative) from 0 but will always have an expected value (average) of 0. When something is broken down to "noise" we call it a stationary process and then we can finally predict future values.

For example this is what the data looks like now with the trend. AKA its stationary

![image](https://github.com/MarkGalanti/153project/blob/master/e2w_diff.png)

## Predicting
Once we remove the trend and seasonality we have a stationary process of differences between the data points. So we can then predict what the difference between $X_t and X_t+1$ will be and then we have a prediction one step into the future. Then with that prediction for $X_t+1$ we can get a prediction for $X_t+2$ and so forth. And with adding in a few other fancy statistically modeling techniques we can come up with this prediction of the next ten points. (The predicted points are in red)

![image](https://github.com/MarkGalanti/153project/blob/master/arima_0_1_1_pred.png)


## Conclusion
Time series is very powerful method for prediction and estimation. It can be used to make money, save money, win basketball games, and so much more.  There is endless applications for time series and it was one of the most fun and interesting things I have learned in college.


Here are some bonus graphs!

![image](https://github.com/MarkGalanti/153project/blob/master/arima_0_1_1.png)

**Standardized Residuals** shows how close we were to the predicting the real data. Its good when this is stationary  
**ACF of residuals** shows us if the model we are chosing is correct. It would reveal most seasonality and allows us to fine tune our model. An example would be exposing a moving average in the data.  
**Q-Q plot of residuals** is similar in use of the standardized residuals  
**The Ljung-Box Statistic** checks for randomness in residuals and overall checks for correlation it is another sanity check for your model.
