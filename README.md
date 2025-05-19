                                                                    # Airbnb Exploratory Data Analysis Project
This project involves analyzing the Airbnb NYC 2019 dataset to uncover valuable insights into the distribution of listings, pricing, availability, and customer preferences across the five boroughs of New York City: Manhattan, Brooklyn, Queens, The Bronx, and Staten Island. Given the complexity and diversity of the New York City rental market, this analysis is vital for understanding the unique dynamics that characterize each borough and neighborhood.

The primary objective of this project is to extract meaningful insights from the data to provide crucial information to management and stakeholders. This data-driven approach will enable them to make informed decisions on how to expand or improve the business, ultimately leading to growth. By identifying emerging patterns from the observations, stakeholders can consider strategic recommendations tailored to their specific operational contexts. For example, insights regarding pricing strategies, listing features, and customer demographics can directly influence marketing approaches and resource allocation. This analysis will assist not only guests in making better choices but also help hosts implement necessary changes to enhance their offerings and grow their businesses.

## Problem Statement
The task of the project is to perform an exploratory analysis of Airbnb listing data to uncover insights into factors that influence pricing, booking frequency, and customer satisfaction that can help hosts optimize their listings and help travelers make more informed decisions.

## Business Objective
The objective of the Airbnb analysis project is to help hosts, property managers, and Airbnb itself optimize their business strategies by leveraging data-driven insights.

## Import Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

## Key Features
- Dataset Loading , Dataset First View, Dataset Rows & Columns count, Dataset Information.

## About Dataset
After examining the dataset, I found that it is not clustered to a significant extent, indicating that it is in its initial pre-wrangling stage. The dataset does not contain any duplicated rows. However, upon inspecting individual columns, I noticed that the 'name' and 'host_name' columns have some duplicated values. I decided to leave them as is, as they can be utilized in further wrangling and analysis processes. Additionally, I observed that approximately 15% of the values in the 'last_review' and 'reviews_per_month' columns are missing, and there are negligible missing values in the 'name' and 'host_name' columns. These missing values can be handled by either dropping or replacing them with other values.

## Understanding Your Variables
- Dataset Columns, Dataset Describe,Check Unique Values for each variable.

## Variables Description
Upon examining the variables in our dataset, we found that they consist of three data types: integer, float, and object (string). Each variable serves a distinct purpose, including:

'Id' for a unique identifier, 'name' for the name of the listing, 'host_id' for a unique host identifier, 'host_name' for the name of the host, 'neighbourhood_group' for the location, 'neighbourhood' for the area, 'latitude' for the latitude range, 'longitude' for the longitude range, 'room_type' for the type of listing, 'Price' for the price of the listing, 'minimum_nights' for the minimum number of nights to be paid for, 'number_of_reviews' for the number of reviews, 'last_review' for the content of the last review, 'reviews_per_month' for the number of checks per month, 'calculated_host_listings_count' for the total count, 'availability_365' for the availability throughout the year.

## Data Wrangling Code
- Identifying and handling outliers
- Engineering Time-Based Features
We have created a new dataframe to generate insights with respect to those specific columns. The outliers in the 'price' column have been eliminated, and the dates in the 'last_review' column have been converted from pandas string objects to datetime format.

## Data Vizualization, Storytelling & Experimenting with charts : Understand the relationships between variables
- Price Distribution Across Neighbourhood Groups
#### Clustered bar chart: 
The chart will show how many properties fall into each price range, segmented by neighborhood group.
We can easily compare the price distribution across neighborhood groups and see which group has more properties in specific price ranges.
