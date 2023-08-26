# When we notice linear relationship pattern in our data we can use Linear model to generate predictions
* We can use this in so many cases np: behavior of the stock market, Sports Performance, business growth
* It can be use to examine the differences between features in data, because some kinds of data fits better than others.
* This type of examination is common in scientific tests e.g: role of statistics in clinical trial in the drug approval

# I use it on Medical data to predict charges of patients
* I use various graph plots to explore different features in my data and correlation between them
* Then separate smokers and non-smokers in my examinations it is very important to to get the most clear image of the patients
* To boost performance of my model I use PolynomialFeatures to expand predictions possibilities and help my model figure out more patterns in my data
* I make performance measurement of my model using mean squared error and R2 score
* Finally I use hlines plot to see how my Linear Regression model with horizontal line fits in my data

![](https://github.com/JakubTabor/Regression/blob/main/Images/Med_Regression.png)

# Then I use Linear Regression model to to see which features affect the most on bikes renting frequency
* I plot data distribution to see which feature fits the most to linear pattern
* Then in pure python I create X and Y features of my data and then split them into Train, test and validation sets
* First I train my Linear model on one features which fits the most to the linear pattern
* And get answer that exist some correlation between number of bikes rented and temperature
* Then I use all features and get much higher score, it means that all features merge make more sense for our model predictions
* Next I normalize my data and train Neural Net Regressor model
* And measure performance of both Linear Regression model and Neural Net using MSE
* Final answer for my examination is that in this case Linear Regression Model work better
* I plot both models predictions on Graph

![](https://github.com/JakubTabor/Regression/blob/main/Images/Bikes_Regression.png)

# 
