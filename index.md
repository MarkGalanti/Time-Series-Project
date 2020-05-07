# Mark Galanti's Stat 153 Project
## The Dataset
For my final project I chose to analyze the data from NBA player Lebron James. Specifically I am looking at a theorectical value called Effort to Win (or for short E2W). The data is from each game Lebron James played from 2003 up until 2019 and he is given a value for how hard it was for him to win that game. 

And this is what the data look like 



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
Simply looking at the data as it relates to time sometimes lets us understand the trend in the data. As we can see in the above plot of all the data points the average of the data tends to decrease overtime. Seeing this allows me to make the assumption that the data is linear overtime. Meaning Lebron will require less E2W as time goes on. Maybe the team is getting better while he gets older.

### 2. Seasonality
Continuing on intuition, things like domain knowledge can really help your model. Domain knowledge is basically understanding the data I'm working with. In this case its basketball, more specifically the NBA. Knowing something about the NBA can give insight into how to make my model fit future data points better. I feel comforatble making the assumption that the NBA is very competitive and all the teams are good and Lebron and the rest of the team will be trying to win all the time, every game. This leads me to believe that the seasonality of this data set is zero or negligible 

### 3. Noise
This is the money maker in time series analysis. The ultimate goal is to dumb down a data set to noise and ideally White Noise. What is noise you ask? Noise is basically a random number generated from a well studied statistical distribution. White Noise for example is purely theoretical and basically will never actually exist in nature, but the idea is if X is a white noise random variable it will fluctuate in even directions (positive and negative) from 0 but will always have an expected value (average) of 0. When something is broken down to "noise" we call it a stationary process and then we can finally predict future values.



**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/MarkGalanti/153project/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
