# ⭐ Customer’s Rating Predictive Model on Delivery Operations Business ⭐
This is my first data science project. In this project, I will show you how to turn raw data into insightful business decision

## 🛠️ Tools and Language 🛠️
<img align="left" alt="Visual Studio Code" width="30px" src="https://upload.wikimedia.org/wikipedia/commons/9/9a/Visual_Studio_Code_1.35_icon.svg" style="padding-right:10px;" />
<img align="left" alt="Google Colab" width="30px" src="https://upload.wikimedia.org/wikipedia/commons/d/d0/Google_Colaboratory_SVG_Logo.svg" style="padding-right:10px;" />
<img align="left" alt="Python" width="30px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/110px-Python-logo-notext.svg.png?20100317150552" style="padding-right:10px;" />
<br />

## 📜 Script 📜 
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UUFCCU-p92vpGhRZHAOxKgSyPOEOVEcB?usp=sharing)

## 💎 Business Understanding 💎
### 🗂️ Project Background
[Data](
In this project, I chose the Delivery Operations topic because based on Statista Market Analyst, this business experiences rapid growth every year and is predicted to experience greater growth in 2025-2026. In Indonesia itself, it has experienced 30% growth, especially after the pandemic. This business also affects various sectors, such as economic growth, social behavior, and digitalization.<br >
### 🗂️ Problem
The large growth of this business also makes its competitiveness high, so the problem raised in this project is the high competition in the delivery business.
### 🗂️ Goals
1. Analyzing Customer Behaviours on Delivery Operation Services and found features that influence the Rating Rate
2. Create a predictive model that can accurately predict the Rating Rate
### 🗂️ Business Objective
Increase the Rating rate by 30% within 3 months by creating a predictive model on the Rating Rate and optimizing features that influence it. 

## 📊 Data Description 📊
The dataset used is an open source [Zomato Delivery Operations Analytics Dataset](https://www.kaggle.com/datasets/saurabhbadole/zomato-delivery-operations-analytics-dataset).
### Data Shape
Rows: 45.584 
Columns: 20 
### Columns/Features
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
[Persentase Missing Value](Missing Value)
There are 8 columns that have missing values. I chose not to drop the missing values ​​directly. Although the percentage per column is small, if accumulated as a whole it will be a lot which can cause the output results to be less accurate.<br >
Here I do different treatments for each type of column.
* for categorical columns the missing value will be replaced using the mode value because the percentage is quite small
* for numeric columns the missing value will be replaced using the median value because it is more suitable for numeric data.
* for the Time_Order column the missing value will be dropped, because later this column will be modified to create a new column, so I don't want to increase the bias in the modified column.

### 🧹 Filtering
[Filter]( )
Filter the unmatched value, because the umatched value 
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
### Customer's Behaviour about Time and Day
First, from several existing features, I explored the time features.

From the graphics above, we can conclude that Customers most likely to use Delivery Service on the night (after 18.00 - 23.59) and 
The day with the most customer’s orders is Wednesday.

### Customer's Behaviour about their favorite type of Order

From the graphic above, we can conclude that Customer's Favorite Order on Each Time Category are:
* Morning: Meal
* Afternoon: Meal
* Evening: Drink
* Night: Snack
  
### Does the large number of orders coming in at night affect the rating?
Although most of customers using delivery services on the night, It doesn’t affects the Ratings. Night shift drivers still has good performance.<br >
So, what features that impact to Rating Rate?
### Correlation Between Time Taken and Rating Rate

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
### Split the Data
The first step to modeling machine learning is splitting the data. In this project, I split the data with a ratio of 80:20.<br >
* 80% of 100% for training dataset, which we will use for training the model
* 20% of 100% for testing dataset, which we will use for testing the model
  
### VIF Score & Heatmap Correlation
Variance Inflation Factor (VIF) is a statistical measure used to detect the presence and severity of multicollinearity in a dataset.

### Modeling and Evaluation

### Hyperparameter Tuning

### Importance Features

## 💡 Insight 💡

## Recommendation
