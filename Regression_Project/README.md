# [First step: Data Preprocessing](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Regression_data_preprocessing_0.ipynb)
# In this project i gonna use various techniques to first preprocess it, then remove outliers and take care of the data distribution
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/histogram_d_rate.png)
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/boxplot_d_rate.png)
* Various plots will gonna help me see what is the percentage of outliers in data and how my data is distributed
* Especially we are looking for columns with normal distribution (gaussian columns)
* And techniques of replacing outliers rather than removing them

# I write some functions for data preprocessing
* Function that deal with column (right image) and return three different columns that interpreted same data
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/bin_to_num_function.png)
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/binnedInc_column.png)
# And function which deals with geography column
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/geography_function.png)
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/geography_column.png)
* And function for one hot encoding
# Next i write the function that identify gaussian columns
* But i have only one normally distibuted column

![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/gaussian_column.png)
# I also write the function that shows me rest of the columns that are skewed, so they are not normally distributed
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/skewed_columns.png)

# Then i write the function that will return me columns with outliers
* This function takes the upper and lower limit and everything above and below are outliers
# And next i write function that take this all columns with outliers and replace them with (max. and min.) allowed
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/capping_function.png)
* This technique helps me keep the informations and get better final model statistics
# Now all outliers are gone and we don't loose many informations (data)
![](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Images/boxplot_no_outliers.png)
# There is no data below and above the lower and upper fence, this is what we achieve

# [Next step: Regression Model](https://github.com/JakubTabor/Regression/blob/main/Regression_Project/Regression_model_on_cupped_data.ipynb)
# Now when my data is ready i gonna use the OLS Regression model 
* First i write function that will build correlation between all columns
