# Demand-Forecasting-for-Walmart

The project involves Demand forecasting for the Walmart company, where the company provides data sets from 45 different stores located in various regions. The original project description wanted to project the sales for each department within each store, however I proposed to project the weekly sales based on the features from the data.  
 
# Details about data:  

The project provides three data files: features, stores, train. In total of more than 400k rows of data.

# Features.csv 
Store number, date, temperature, fuel price, 5 columns of markdown, consumer price index, unemployment rate and a boolean of whether or not that week contained a holiday.

# Stores.csv 
Information store type and size

# Train.csv and test.csv
It gives information on the store number, the department, date, weekly sales, and whether it is a holiday or not.  
 
# Random Forest Regression:
Considering that our project goal was to predict sales forecasting from a weekly basis, I decided to use RandomForestRegressor. One of the biggest benefits of using random forest is that when you use enough trees for predictions overfitting will not be an issue, however using too many trees can drastically affect the time it takes for the algorithm to run completely. 
Another benefit of using random forest was that it provided good results without necessitating too much parameter adjustments. In fact the only parameter I adjusted for this portion was the n_estimators, which is the number of trees the algorithm builds to perform the necessary prediction.  
I ran the algorithm with various n_estimators  num_est = [2,4,10,20,30,40,50,60,70,80,90,100] 
To which I compared the resulting r2_score to see which number of trees would best fit the dataset we were using. After running the algorithm through all 12 of the n_estimators, I found that the “60” gave the highest r2_score, indicating that it was the most suitable value to use for n_estimators for the algorithm. 
 
# Linear Regression: 

Since our goal was to estimate weekly sales based on features provided to us, Linear Regression sounded like a good fit. Linear regression models the relationship between a scalar variable and a set of independent variables.  Using the merged dataset which matched all stores to their specific features, and the yielded predictive model would tell us which features were most important to predicting weekly sales. The predictive model showed that the most important feature in determining weekly sales was the ‘IsHoliday’ feature. This means that the weeks that contained a holiday were the most successful when it came to weekly sales, while the least important feature was temperature. The dates that were taken into account contained important days such as the Super Bowl, Labor Day, Thanksgiving (most likely including black friday and cyber monday), and Christmas. 

 
# Decision Tree Regressor:

I decided to go with Decision Tree Regressor after getting an error when using Decision Tree Classifier. That error was that the data was continuous. Decision Tree Regressor was the solution found. It works similar to Decision Tree Classifier, not exactly the same but close enough, however, one of the key differences is that Regressor works better with continuous or numeric response variables. Regressor works well for prediction as opposed to classification. In the end the evaluation accuracy came out as 95%, with IsHoliday as the most important feature, followed by Fuel_Price. 

# Conclusion:
1-  The best Machine Learning algorithm we tested on this data set, was Random Forest.
2-  Random Forest composed of 60 trees was our best predictor.

