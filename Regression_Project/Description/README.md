# [First step: Data Preprocessing]()
# I gonna use Regression model on Cancer data 
* First I check my data distribution and look if there are any outliers, to do this i use histplot
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/Histogram_death_rate.png)
* We can see the data that is placed apart from most of the distribution

# I also check distiobution of the data on boxplot
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/Boxplot_death_rate.png)
* We can see outliers above and below the (upper and lower fences)

# Then I am searching for columns with single or few values and duplicates and data and deal with all of them
* I have complicated column (bindIng), so I write the function that will remove brackets and split values, take a mean and remove remaining column
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/bin_to_num_function.png)

# Then I deal with (Geography) column, because it have two variables with comma, I need to split them and save in different columns
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/categ_to_col_function.png)

# I write also function that will take categorical (object) columns and convert them into encoded, numerical columns
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/one_hot_encoding_function.png)

# Then i deal with missing values, it will drop columns with more than 50% of missing values, but if columns have less than 50% it will fill missing values with mean value
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/drop_and_fill_function.png)

# Now we are gonna extract gaussian columns from our dataset
* After rejection of null hipotesis we are searching for columns that significance is greater than 0.5
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/gaussian_columns.png)
* We are gonna use Z-Score technique to detect outliers and also look at normally distributed columns

# I write function that will define outliers and extract columns without them
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/deal_with_outliers.png)
* Then i gonna remove categorical columns with less than 10 unique values

# Next I gonna identify columns that have skewed distribution and plot them on graph
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/identify_skewed_function.png)
* I use boxplot to see all outliers in my data
* We can see that we have bunch of them

# Then i define upper and lower limit using quantile method
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/quantile_upper_lower_limit.png)
* Using this method i write function that will return me columns with outliers

# Now I can use Trimming or cupping method to detect and remove outliers
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/capping_function.png)
* I choose cupping method to not loos so many informations
* This technique replace outliers with max and min allowed

# When I plot my data of graph i can see that all outliers are gone, my data is ready
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/boxplot_no_outliers.png)

# [2 step: Regression Model]()
# In this section i gonna use Regression model on my already preprocessed data
* First i write a function that will build correlation between columns and return columns with more than 80% correlation
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/correlation_function.png)

# I gonna use it on my cupped data, it will help my model figure out the most significant features from my data 
* Then I use sklearn to split my data into train and test sets, i write it in form of function and use it on my dataset

# I define my OLS model and add a constant to my X_train set
* It means that every row in this columns will be multiplied with bias equal one
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/Linear_Regression_model.png)

# Next in my function i define model training with y_train and changed X_train
* And then i call object of my class and train OLS model on my data

# I call summary of my model, now i gonna extract the most important informations
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/summary.png)
* Which are p-value, r-squared value, adjusted r-squared value

# Now i write function to get significant variable, to accomplish it I reject null hypothesis
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/significant_variables_function.png)
* And set p-value threshold at 0.5, when i get less than 0.5 it means that it is significant variable

# Then i call my function and use it on my Linear Regression model
* I must add constant to my X_train and use my model function
* to train it on significant variables of X_train and just y_train

# Finally i call summary of my model and i get only the most important measurment and reduce complexity



