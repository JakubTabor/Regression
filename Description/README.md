**MEDICAL REGRESSION MODEL**
# Here I gonna explore dataset that include some informations about (smokers and non-smokers), I need to find strong correlations 
* And then use (Linear model) to deal with this dataset 

# First I gonna check if my dataset include any (null values), it seems that this dataset is complete
* Now I gonna do simple preprocessing, so I import (LabelEncoder and OneHotEncoder)
* I use (LabelEncoder) to (drop duplicates from sex column) and change this column into numerical values
* I do this same with (smoker column) and also with region column
* My (region column) get numbers for each region, its not so good because they have no correlation, but its ok for now

# Then I look at correlation of each column in relation to (charges column), I can see that (smoker cloumn) have the strongest correlation
* I also (sort values) from the lowest to the highest, now I gonna explore the correlation in detail using different graph plots

# First I visualize all correlations on (subplots), for better visuality
* Then I visualize distribution of charges for (smokers and no-smokers), I can clearly see that smokers spent more on treatment
* (no-smokers) spent from (0 - 20 000) and (smokers) spent from (10 000 - 50 000) then charges are decreasing

# Now we are gonna look (number of smokers and no-smokers) according to sex
* We can notice that the number of smoking mens is higher than woman smokers, also non-smkoer womans are in majority
* Now we are gonna see, how look charges for (smoking womens and non-smoking womens), I use to do it (Box plot)
* We can see that smokers womes spent from (20 000 - 40 000) and non-smoker womens spent from (5 000 - 10 000)

# Then I plot on graph charges of (smoking mens and non-smoking mens) on a (Box plot)
* Charges are similar to (womens charges) from (5 000 - 10 000) non-smokers and (20 000 - 40 000) for smokers

# Now I gonna plot (Distribution of age) for patients, most of them are (around 20 years old) and range of data is from (20 to 65 year old)
* What's interesting to notice is that we have patients (below 20 years old), we are gonna plot it on (catplot)
* Trend for smokers and non-smoker (depending on the age) is this same as previous, we have more smokers man and more non-smokers women

# Now we are gonna plot on (Box plot) charges for (18 year old smokers), non-smokers spend less than (5 000)
* But (18 year old smokers) spend from (15 000 - 35 000) for treatment, very similar to older (smokers persons)

# Now we are gonna use (distplot) to see (Distribution of bmi), we can see that (BMI) grow from around (18 to somewhere over 30)
* At around (30 years old it reaches the pick) and start decreasing to age of (50 years old)   
* Next we are gonna see how look charges for persons (with BMI equal or greater than 30), so when BMI reaches the pick
* Persons with (BMI equal or greater than 30) spend the most from (0 to 20 000) then less of them something around (30 000 to 50 000)
* Now we are gonna compare (Distribution of charges for patients with BMI less than 30)
* The most of patients spend from (0 to 10 000) then spends decrease to (30 000)
* The data for persons (BMI greater than 30) is irregular distributed, in case of (Persons with BMI less than 30), data keep the flowing pattern

# Now we are gonna plot on Scatter plot (charges and bmi for smokers and non-smokers), then we do this same on (lmplot)
* We can see that the (charges growth when BMI growth) and there are higher charges for smokers
* We can also se on (lmplot) linear pattern of data and rapid growth of charges for smokers

# Now we are gonna look at (dependence of number of children for patients) I gonna use (catplot) for it
* The most of patients don't have children, then some patients have (1 children or 2), in minority (patients have 3 or more)
* Then I plot also on (catplot) number of (smokers and non-smokers) with dependence of sex, who have more than 0 childrens
* It seems that lot of smokers have children's (and most of them are mens)

# Now i gonna use (Linear model) on my dataset, so first I need to divide my data into (train and test sets)
* I prepare (X and y which is the target column) for (train_test_split) and I get (X and y sets)

# Then I can import (LinearRegression) model and train it with (X_train and y_train), score is good, but we can boost it
* I prepare (train and test set predictions) to plot them later on graph

# Now I gonna prepare new (X and y) without (region column), I gonna (preprocess my data using PolynomialFeatures)
* It gonna help my model to identify (nonlinear patterns) by adding polynomial terms to the model
* The (degree) of the polynomial is used to control the number of features added, I set it to (two)
* Then I transform my data (without target column) with use of (PolynomialFeatures)
* And I create new (train and test sets) with (PolynomialFeatures) inside

# I train my model once again (X_train and y_train) and call it (Polynomial Regression), score i much higher than previous
* Then I also prepare predictions for (train and test set)

# I print (mean squared error) for (train data and test data) and also (r2 score) for (train data and test data)
* (R2 score) is used to evaluate the performance of a (linear regression model), (Best possible score is 1.0)
* We have (0.833 on train data and 0.881 on test data) which is good, the worst score is (0.0)

# Now I gonna print (how my model make predictions on the given dataset)
* I supply (Y_train_pred) and then difference between (Y_train_pred - y_train), then i supply (Y_test_pred) and then difference between (Y_test_pred - y_test)
* Then I use (plt hlines) to (draw horizontal lines) on my dataset predictions

# My model perform very well on the dataset, I need to use (horizontal lines) to fit to the data

![](https://github.com/JakubTabor/Regression/blob/main/Images/Med_Regression.png)

**BIKES DATA REGRESSION MODEL**

# I gonna explore dataset that include (renting a bike) depending on some features
* First I drop some columns that are useless for me
* Now I gonna lock my (Hour column at 12) and drop the rest 

# Then I make for loop for (column in index 1 to the last) and plot them on the (scatter plot) 
* They will be named by the label and (Bike_Count) will be visible from the left
* The best linear pattern I can see on the (Temperature) plot

# I drop (Wind_speed and Visibility), because they are just messy points

# Now I gonna create (train, val and test sets) using (numpy split) and I split my data at (60% of data and then at 80% of data)
* Then I define function that will return me (X and y), first I make (deepcopy of my dataframe)
* Next I set condition for (x_labels) if is None, I define (X), which is (columns of dataframe that are not y_label) in acces to values
* In else I set condition (if there is x_labels), then my (X) is (x_labels of just that label in dataframe) with reshape to (2D)
* Then in else i specify that (if I have list of specific x_labels), then my X is equal to (dataframe of this x_labels)
* Next I specify what is (y), it is (y_label of my datatframe) with reshape to 2D
* And I (stack) both (X and y) horizontally, I save it as a new (data), then I return both (X and y) and new (data)

# Now I gonna use (Temperature) column to create (train, val and test sets), because this column have the best pattern of data
* So I use my (get_xy) fuction and (y label which is Bike_Count) and for (x_labels Temperature(C) column)

# Then I import (LinearRegression) and name it at (temp_reg), because of (Temperature feature)
* and train my model (X_train_temp, y_train_temp) and get pretty low score
* I can see that the dependence of this feature is not so strong, but exist some correlation

# Now I gonna plot my model predictions on (tensorflow linspace), data will be (from -20 to 40) and (100 values from it), i save it as (x)
* To (plt.plot) i put (x variable) and (model : temp_reg.predict this x variable), reshaped into (numpy 2D array)
* And now I can look how my model works on (Temperature(C)) data, its not perfect, but it fits into a pattern

# Now I gonna use all of my features to train the model, so I do as previous (np.split) and get (train, val and test sets)
* I use my function (get_xy) to get (train, val and test) and pass all columns without (Bike_Count) (df.columns[1:])
* I named my model (all_reg) and train it with new all features (X_train_all and y_train_all)
* And get score which is much higher than previous

# Now I gonna use (Regression for Neural Net), but first I gonna define plot function, that will plot (history of my model)
* So I gonna take from history (loss and val_loss), set their labels and show them on (Grid) with (legend)

# Then I gonna normalize my data for (Neural Net) using (tensorflow) and pass the model (tf.keras.layers.Normalization)
* I set (input_shape = (1, )) because I gonna do it solo on (Temperature(C) ), then (adapt X_train_temp with reshape to one single vector reshape(-1)) 

# Then I create my model and name it (temp_nn_model), because it gonna be trained on one feature
* I pass my (normalised layer), which i named (temp_normalizer) and one (Dense leayer with one unit)
* One single node means that my model is linear, output is also linear, because it doesn't have any activation function

# Then I compile my model with (Adam optimizer and loss as mean squared error), I set also learning rate at (0.1)
* And set loss as "mean_squared_error", to evaluate my linear model
* Then I train my model with (X_train_temp and y_train_temp) and also validation sets (X_val_temp and y_val_temp)

# I use my (plot function) and see that my loss i decreasing, it is calculated with MSE

# Then I gonna use this same plot as previous for my (Linear Regression model) and use it on (Neural Net Regressor)
* We can see that our (Neural Net Regressor) predict just a bit different
* Its a different aproach, with use of backpropagtion to train our Neural Net

# Now I gonna use Neural Net instead of one single node to make predictions
* I use my normalizer to (normalize and adapt all features of my dataset X_train_all)
* I have six features, so I put (input_shape equal 6), and then I can build my Neural Net

# First I can put my (normalised layer), then two hidden layers with (32 neurons and activation relu)
* And the output layer (without activation) and I compile with this same parameters as previous, but decrease (learning_rate just a bit)
* Then I do training of my model with (X_train_all and y_train_all) and also valid data (X_val_all and y_val_all)

# On my graph I see that loss is decreasing not as smooth as previous, but it reach same results as previous

# In our Neural Net model i can't get score, but I can use (mean squared error) to evaluate my model
* I gonna write (MSE function and use it on Linear Regression model as well as on Neural Net model)
* So I get predictions for (y_pred_lr and y_pred_nn) on (X_test_all)
* And (MSE function will take) (square difference between y_pred - y_real and take mean of it), thats how I gonna get 
* I get (mean squared error) for Linear Regression and then for Neural Net

# Whats interesting on Neural Net I have larger (mean squared error), Now I gonna plot (actual results vs predictions)

# I gonna plot the results on the same axes, so I set (aspect to 'equal') and then set (true values and predictions for Linear Regression and Neural net)
* Then set limits for (approximate number of bikes), dots for Neural Net are more spread out
* And Linear Regression fit better, so in this case (Linear Regressor) perform better 

# It is valuable to use (non-linear model) for comparison with the results of Linear model to see which one perform better

![](https://github.com/JakubTabor/Regression/blob/main/Images/Bikes_Regression.png)

**OCEAN DATA REGRESSION MODEL**

# Portfolio_Regression
* I am living link to dataset https://www.kaggle.com/sohier/calcofi

# In this exercise I want to explore the patterns in "ocean dataset" which contain ocean parameters measurement data
* And I want to track correlation between this parameters, then apply "Regression model" to deal with this problem 

# First I load dataset and save it as "bot" and get informations of this data, using "info()"
* Dataset is very big, so I gonna keep only the most important "in my opinion" columns, I lock numbers of this columns
* Then I check informations about my new dataset

* I use "seaborn" to look at (empty values) in my dataset, I can clearly see size of lack values
* Now I gonna deal with it, so I create variable which are my columns and iterate through it getting empty values and save them as "bottle"
* Then I use tehnic "reset_index" on previous saved dataset and set (drop at True), so it gonna drop all empty values
* I plot my dataset one more time and see that empty values are gone

# Now I gonna first build correlations between columns and then visualize them
* I can see the lowest correlation which is (lower number) and the strongest correlation which is (higher number)
* For example (T_degC and O2ml_L) have strong correlation which is (0.8) or (Salnty and Depthm) which is (0.56)
* I also have negative correlation in case of (Depthm and T_degC) which is (- 0.67)

* I plot on graph correlation between (Depth and T_degC) and see that (temperature decrese when depth incrise)
* But there is a strange bump (in range from 0 - 1000 m. depth)
* We can see that there must be some parameter that affect this change in temperature

* I plot also correlation between (Salnty and Depthm) and see that if (depth increase salinity also increase)
* Now I also want to see correlation between (Salnty and T_degC)

# Distribution of data tell us that it don't seem to have a strong relationship
* But with use of some additional informations on wikipedia (https://en.wikipedia.org/wiki/Potential_density)
* We can see that (density), also play the important role, density is not a measured but a calculated quantity from (Temperature, Pressure and Salinity)
* In conclusion Temperature can be expressed as a function of Salinity and Density
* We add additional variable to our graph (theta_step) and include it to our data, with use of (STheta), I call it (bottle_stheta)
* It looks that all is working, but we can call it (potential density), it's not the real density at the specific depth

# Now we can create a (predictive model), but before we need to prepare the data
* So first I gonna split my data to sets which are (bottle_train and bottle_test) and my dataset is (bottle)
* Then I print shape of my data, to see how complicated is my dataset

* I gonna divide my data into (features which are all columns without T_degC), all of this I gonna convert into list
* My target column will be "T_degC", Now when I have (features and target column) I can split data into (train and test sets)
* I gonna take (X_train and X_test) from (bottle_train of features and only values), its previous splited data by (train_test_split) method 
* It is data taken from (features variable), Now I gonna take data from (target variable), its only "T_degC" column
* My (y_train and y_test) are (bottle_train of target with solo values)

# Now when I have my data prepared and splitted I can use "Linear Regression" to make predictions
* So first I import "LinearRegression" and now I gonna make predictions on only one feature which is "Salnty" and how it impact (temperature)
* I save my feature as "features1", and with use of it I prepare new (train and test set)

* Then I create class of my "LinearRegression" and train my model with previous splitted new dataset
* And save my predictions as "y_pred1", its prediction of my model on "X_test1"
* Now to check model predictions "error" I gonna import "mean_squared_error" and supply it with (y_test1 and y_pred1)
* I save it as "mse_lin" and use "RMSE_lin", its squared "mse_lin variable", so I get my error in this formula

# Then I visualize regression plot and supply (x as Salnty and y as T_degC)
* I can clearly see on graph my model predictions, we isolated the feature of Salinity from the others, but it doesn't seem to exist a clear trend

# Now I gonna use all of my features to make predictions and see how the error changed
* So I train my model with previous defined (X_train and y_train) and get (y_pred2) by making predictions with (X_test)
* Then I define (RMSE) for my model and see that the error decreased

# This was a use case of (Linear Regression) model to deal with this problem
* One feature as Salinity is not enough to find a link with Temperature
* In order to enhance the temperature prediction with the linear regression model we need to use more features 
* That way we give useful informations to our predictive model.

![](https://github.com/JakubTabor/Regression/blob/main/Images/Regression.png)
