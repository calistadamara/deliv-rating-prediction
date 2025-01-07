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

## 🔭 Exploratory Data Analysis 🔭

## Machine Learning


## Insight

## Recommendation
