# The GenG Model for Property Investors (GGMPI)

# Methodology: Property Investment Risk Model

This project is all about building a model that helps determine the investment risk of buying a property. The goal is to predict whether a property is a **high**, **medium**, or **low risk** for investment based on factors like price, property age, and maintenance costs. We’ll use machine learning and some data visualisation techniques to give users insights on which properties might be safer to invest in.

# Steps and Key Concepts

## 1\. Loading the Data

First, we load a dataset containing property details, such as the price, taxes, square footage, and other key features. We check out a few rows of the data to make sure everything is in order before moving on.

## 2\. Creating New Features (Feature Engineering)

To improve our model, we create some new features that are important for calculating investment risk:

* **Price per Square Foot**: This is the price of the property divided by its size (in square feet). It helps us compare properties more fairly since bigger homes naturally cost more.  
* **Price Volatility**: This shows how much prices in a certain area (ZIP code) tend to go up and down. We calculate this using a formula called the "coefficient of variation" (CV), which gives a sense of how stable or risky an area’s housing market is.  
* **Maintenance Cost**: This is the total of property taxes and homeowners association (HOA) fees, helping us understand the ongoing costs of owning the property.

These new features are key to understanding how risky an investment might be.

## 3\. Defining the Risk Levels

We break properties into three categories based on how risky they seem:

* **High Risk**: These properties have high prices, lots of price volatility, or high maintenance costs. Older properties also tend to be higher risk.  
* **Medium Risk**: These properties fall in the middle range for price, volatility, and maintenance.  
* **Low Risk**: Properties with low prices, little volatility, and low ongoing costs. Newer properties are also seen as less risky.

## 4\. Calculating the Overall Risk Score

To figure out a property's overall risk, we create a score by combining different factors and giving each a weight based on how important it is:

* **Price Volatility**: 50% weight (since price changes can be a big risk).  
* **Sold Price**: 30% weight (higher prices mean more money at stake).  
* **Maintenance Costs**: 10% weight (ongoing costs like taxes and HOA fees).  
* **Age of Property**: 10% weight (older homes can be riskier).

We calculate a **weighted score** for each property. Based on the score, we label the property as **high risk**, **medium risk**, or **low risk**.

## 5\. Training a Machine Learning Model

After setting up the data, we use a machine learning model called **K-Nearest Neighbors (KNN)**. This model predicts whether a new property is high, medium, or low risk by comparing it to similar properties in the dataset.

The model looks at:

* Price per square foot  
* Year built  
* Maintenance costs  
* Price volatility (or how much prices change in the area)

Once trained, this model can make predictions about new properties based on these factors.

## 6\. Using Geographic Data

If we don't have direct information about a property's area, we use the **Haversine formula** (which calculates distances between latitude and longitude) to find nearby properties and estimate risk. This helps us fill in gaps when exact data isn't available for a specific location.

## 7\. Predicting Risk for New Properties

The model allows users to input details about a property (like its price per square foot, age, and location), and it predicts how risky the investment is. This makes it easy to assess the potential risk before making any investment decisions.

## 8\. Visualizing Risk on a Map

To make things even clearer, we use maps to show the risk levels for properties in different areas. Users can input a **ZIP code**, and the map will show the average risk for properties in that area. Properties are color-coded:

* **Red**: High risk  
* **Orange**: Medium risk  
* **Green**: Low risk

This visualization helps investors see which areas might be riskier than others.

# What You Get

After running the model, you’ll get:

1. A **risk classification** for each property based on the weighted score.  
2. A **map visualization** showing the risk levels of different neighborhoods.

## Summary

This project helps predict how risky a property investment might be by combining data about price, location, maintenance costs, and property age. The model uses a simple machine learning approach to calculate an overall risk score for each property, and the map tool makes it easy to see which areas are riskier than others.

By using this model, real estate investors can make more informed decisions about where to buy properties and what level of risk they might face. This system could be further improved by adding more data (like market trends or economic factors) to make predictions even more accurate.

