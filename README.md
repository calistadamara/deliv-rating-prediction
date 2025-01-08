# ⭐ Customer’s Rating Predictive Model on Delivery Operations Business ⭐
Hi there! This is my first data science project about Implementing Machine Learning Model to predict and optimize the Rating Rate of Delivery Business Operations. If you have any suggestions or supportive critics, please do not hesitate to contact me. 😊

## 🛠️ Tools and Language 🛠️
<img align="left" alt="Visual Studio Code" width="30px" src="https://upload.wikimedia.org/wikipedia/commons/9/9a/Visual_Studio_Code_1.35_icon.svg" style="padding-right:10px;" />
<img align="left" alt="Google Colab" width="50px" src="https://upload.wikimedia.org/wikipedia/commons/d/d0/Google_Colaboratory_SVG_Logo.svg" style="padding-right:10px;" />
<img align="left" alt="Python" width="30px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/110px-Python-logo-notext.svg.png?20100317150552" style="padding-right:10px;" />
<br />

## 📜 Script 📜 
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UUFCCU-p92vpGhRZHAOxKgSyPOEOVEcB?usp=sharing)

## 💎 Business Understanding 💎
### 🎯 Project Background
Delivery Operations Business experiences rapid growth every year and is predicted to experience greater growth in 2025-2026, based on ![Statista Market Insights](https://www.statista.com/outlook/emo/online-food-delivery/worldwide). In Indonesia itself, it has experienced 30% growth, especially after the pandemic.
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/Delivery%20Business%20Revenue.png" width="700" /><br >
This business also affects various sectors, such as economic growth, social behavior, and digitalization. Businesse that provide efficiency is also in great demand by the public and have a big influence on the public's consumption behaviour. In addition, this business also influences technological progress and digitalization in operational delivery. That's why I chose Delivery Operations topic.<br >
### 🎯 Problem
The large growth of this business also makes its competitiveness high, so the problem raised in this project is the high competition in the delivery business.
### 🎯 Goals
1. Analyzing Customer Behaviours on Delivery Operation Services and found features that influence the Rating Rate
2. Create a predictive model that can accurately predict the Rating Rate
### 🎯 Business Objective
Increase the Rating rate by 30% within 3 months by creating a predictive model on the Rating Rate and optimizing features that influence it. 

## 📊 Data Description 📊
The dataset used is an open source [Zomato Delivery Operations Analytics Dataset](https://www.kaggle.com/datasets/saurabhbadole/zomato-delivery-operations-analytics-dataset).
### ✏️ Data Shape
Rows: 45.584 <br >
Columns: 20 
### ✏️ Columns/Features
* ID: Unique identifier for each delivery.
* Delivery_person_ID: Unique identifier for each delivery person.
* Delivery_person_Age: Age of the delivery person.
* Delivery_person_Ratings: Ratings assigned to the delivery person.
* Restaurant_latitude: Latitude of the restaurant.
* Restaurant_longitude: Longitude of the restaurant.
* Delivery_location_latitude: Latitude of the delivery location.
* Delivery_location_longitude: Longitude of the delivery location.
* Order_Date: Date of the order.
* Time_Ordered: Time the order was placed.
* Time_Order_picked: Time the order was picked up for delivery.
* Weather_conditions: Weather conditions at the time of delivery.
* Road_traffic_density: Density of road traffic during delivery.
* Vehicle_condition: Condition of the delivery vehicle.
* Type_of_order: Type of order (e.g., dine-in, takeaway, delivery).
* Type_of_vehicle: Type of vehicle used for delivery.
* Multiple_deliveries: Indicator of whether multiple deliveries were made in the same trip.
* Festival: Indicator of whether the delivery coincided with a festival.
* City: City where the delivery took place.
* Time_taken (min): Time taken for delivery in minutes.
  
## 🫧 Data Preprocessing 🫧
### 🧹 Handling Missing Value
The dataset contains 8 features that have missing values.<br >
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/missing%20value.png" width="400" /><br >
I chose not to drop the missing values ​​directly. Although the percentage per column is small, but the accumulated as a whole it will be a lot which can cause the output results to be less accurate.<br >
Here I do different treatments for each type of column.
* for categorical columns the missing value will be replaced using the mode value because the percentage is quite small
* for numeric columns the missing value will be replaced using the median value because it is more suitable for numeric data.
* for the Time_Order column the missing value will be dropped, because later this column will be modified to create a new column, so I don't want to increase the bias in the modified column.

### 🧹 Filtering
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/filter%20(1).png" width="400" /><br >
Filter the unmatched value, because we don't know exactly what the value of the data is.
### 🧹 Data Type Convert
Convert the datatype according to its value
* Order_Data: obj -> datetime
* Time_Ordered: obj -> datetime
* Time_Order_picked: obj -> datetime
### 🧹 Duplicate Value
There is no duplicate value

## ⚙️ Feature Engineering (Before EDA) ⚙️
### Add New Features
* order_prepare_time : the difference between Time_Ordered and Time_Order_picked, reflecting the time taken for order preparation
* distance : the spatial separation between Restaurant_coordinates and Delivery_coordinates.
* day_of_week : Extracted from Order_Date, specifying the day (Sunday/Monday/etc)
* time_category : Time_Order grouping -> Morning (00.00-10.00), Afternoon(10.01-14.00), Evening (14.01-18.00), Night (18.01-23.59)
### Drop Unnecessary Features
Some of the features are already represented by other features, so we need to drop these features:
* Restaurant_latitude
* Restaurant_longitude
* Delivery_location_latitude
* Delivery_location_longitude
* Time_Orderd
* Time_Order_picked
## 🔭 Exploratory Data Analysis 🔭
### 💈 Customer's Behaviour about Time and Day
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/time%20cat%20count.png" width="300" />        <img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/day%20of%20week%20count.png" width="400" /><br >
From the graphics above, we can conclude that Customers most likely to use Delivery Service on the night (after 18.00 - 23.59) and 
The day with the most customer’s orders is Wednesday.
### 💈 Customer's Behaviour about their favorite type of Order
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/fav%20meal.png" width="400" /><br >
From the graphic above, we can conclude that Customer's Favorite Order on Each Time Category are:
* Morning: Meal
* Afternoon: Meal
* Evening: Drink
* Night: Snack
  
### 💈 Does the large number of orders coming in at night affect the rating?
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/rating%20on%20each%20time.png" width="400" /><br >
Although most of customers using delivery services on the night, It doesn’t affects the Ratings. Night shift drivers still has good performance.<br >
So, what features that impact to Rating Rate?
### 💈 Correlation Between Time Taken and Rating Rate
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/rating%20vs%20time%20taken.png" width="400" /><br >
One of the features that impact to Rating is Time (Delivery) Taken. It has negative correlation.<br >
It means the longer time can make the lowest ratings.

## ⚙️ Feature Engineering (After EDA) ⚙️
Feature engineering after EDA is carried out to standardize features so that they are ready for machine learning modeling.
### Scaling Numerical Features
* Delivery_person_Age
* distance
* Time_taken (min)
* order_prepare_time (min)
### Encoding Categorical Features
1. Label Encoding for Festival
2. Ordinal Encoding for Weather_conditions, Type of vehicle, Road_traffic_density, City, day of week
   
## 🧮 Machine Learning 🧮
### 📌 Split the Data
The first step to modeling machine learning is splitting the data. In this project, I split the data with a ratio of 80:20.<br >
* 80% of 100% for the training dataset, which we will use for training the model
* 20% of 100% for the testing dataset, which we will use for testing the model
  
### 📌 VIF Score & Heatmap Correlation
Variance Inflation Factor (VIF) is a statistical measure used to detect the presence and severity of multicollinearity in a dataset.
Multicollinearity is the condition when two or more features/predictors are highly correlated with each other. This can cause coefficients of estimates to become unreliable. 
* VIF == 1 → No multicollinearity
* VIF between 4 and 10 → Moderate multicollinearity
* VIF > 10 → Severe multicollinearity <br >
Here is the output of vif score calculation:<br >
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/vif.png" width="200" />
VIF Score < 4.0, Multicollinearity between independent variables is low and the model is stable, so there is no need for multicollinearity handling.<br >
Visualization of correlation for each features:
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/heatmap.png" width="500" />

### 📌 Modeling and Evaluation
In this project, 4 types of ML are used for comparison, namely Ridge Regression, Lasso Regression, Random Forest Regression and Xgboost Regression. Also, 3 metrics are used to measure their performance, namely RMSE (Root Mean Square Error), MAE (Mean Absolute Error) and MAPE (Mean Absolute Percentage Error). The following is the results of model evaluation on the train dataset and test dataset.<br >
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/modeling%20and%20eval.png" width="500" /><br >
From the 4 models, RandomForest Regression is the best model, The model has the smallest error and experiences an increase in performance when implemented from training data to test data.

### 📌 Hyperparameter Tuning
Tuning the parameters with cross validation with k-fold using GridSearchCV.<br >
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/parameter%20tuning.png" width="400" /><br >
The highest score (0.493689) was achieved by the model with max_depth=5 and n_estimators=10.
Comparison metrics before and after tuning parameters.<br >
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/before-after%20tuning.png" width="300" /><br >
After tuning, the model shows better accuration of test data.

### 📌 Importance Features
To understand how the model predicts and provide interpretive insights, the DALEX library is used. DALEX (Descriptive mAchine Learning EXplanations) is a Python library for describing and analyzing machine learning models.
<img src="https://github.com/calistadamara/deliv-rating-prediction/blob/main/img/importance%20feature.png" width="500" /><br >
From the output of DALEX explainer above we can conclude that the top 3 features that influences the rating rate are:
1. Time taken
2. Weather condition
3. Vehicle condition
## 💡 Insight and Recommendation 💡
### 🗂️ EDA Insight and Recommendation
1. Optimize Night Operational Service
   Insight: Customers most likely to use Delivery Service on the night (after 18.00 - 23.59)
   Recommendation:
   * Prioritizing resource allocation such as drivers, vehicles, and night monitoring systems to accommodate high demand.
   * Provide incentives to night drivers to maintain motivation and performance,
2. Peak Day Strategy
   Insight: The day with the most customer’s orders is Wednesday
   Recommendation: Special promotions such as discounts or bundling on that day to increase customer satisfaction and potential repeat orders.
3. Favorite Order
   Insight: Favorite order in each time -> Morning: Meal; Afternoon: Meal; Evening: Drink; Night: Snack
   Recommendation:
   * Morning and Afternoon: Promote meal category
   * Afternoon: Offer discounts on popular drinks.
   * Evening: Create special promotions for late-night snacks such as discounts on snack orders.
### 🗂️ Machine Learning Model
Predictive Model succesfully build, the best model is Random Forest Regressor, 
Top 3 The Most Importance Features are:
1. Time taken<br >
   Recommendation to manage time taken:
   * Optimize delivery routing algorithms to ensure more efficient trips.
   * Invest in technology like traffic prediction and delivery time estimation to assist drivers.
3. Weather condition<br >
    Recommendation to manage Weather condition: Offer customers notification of potential delays due to extreme weather conditions
4. Vehicle condition <br >
   Recommendation to manage Vehicle condition: Design regulation of vehicle inspections into operational flows to minimize the risk of delays.

### ❤️ Closing ❤️
That's all about the project, I hope this project can bring insight. Thank you!


