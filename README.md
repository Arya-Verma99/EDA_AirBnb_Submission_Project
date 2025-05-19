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
### 1. Price Distribution Across Neighbourhood Groups
#### countplot chart: 
The chart will show how many properties fall into each price range, segmented by neighborhood group.
We can easily compare the price distribution across neighborhood groups and see which group has more properties in specific price ranges.

#### insights found from the chart
The countplot chart reveals how property prices are distributed across different neighborhood groups. Lower-priced listings are more common in neighborhoods like Brooklyn and Queens, while higher-priced listings are concentrated in Manhattan.

#### positive business impact
By insights this suggests that Manhattan has more premium listings, whereas Brooklyn and the Bronx cater more to budget-conscious customers. These insights can help guide pricing strategies and marketing efforts, focusing on different price ranges for each neighborhood group.

### 2. The most preferred room type based on price in different neighbourhood groups.
#### insights found from the chart
the most preferred room type is an entire home/apartment, while the least preferred is a shared room in every neighbourhood group. The highest proportion of rooms is in Manhattan, with the lowest in the Staten Island.

#### positive business impact
After gaining insights, we can increase the count and services of room types that are in higher demand, which will allow us to proportionally increase prices and help generate better revenue. Additionally, we can improve other rooms based on the preferences of high-demand rooms to boost their popularity.

### 3. Reviews on Room Type in different Neighbourhood Groups
#### insights found from the chart
It provides clear insights into which room types are most popular (in terms of reviews) in specific neighbourhoods. The chart reveals that entire home/apt is the most popular accommodation choice, suggesting that guests highly prefer privacy and exclusive use of a space. Private rooms have medium popularity, indicating that some guests are willing to share spaces but still prioritize personal privacy. In contrast, shared rooms are the least popular, showing minimal demand, likely due to guests' preference for more private accommodations. These insights suggest focusing on offering entire homes or private rooms, while minimizing investment in shared rooms, to better meet customer preferences and boost business performance

#### positive business impact
analyzing customer reviews based on room types and neighbourhoods can provide valuable insights that drive positive business outcomes, such as enhanced marketing, improved customer satisfaction, and optimized pricing strategies.

### 4. Price vs. Minimum Nights in Different Neighbourhood_group
#### insights found from the chart
Neighbourhoods like Manhattan has typically shown a wide range of prices, with some listings priced much higher than others. This area has likely catered to a diverse range of customers, from budget travelers to luxury seekers.
neighbourhoods like Bronx and Queens seem to have shorter minimum night stays and lower prices, appealing to more budget-conscious or short-term travelers.

#### positive business impact
Are there any insights that lead to negative growth? Justify with specific reason.

### 5. Reviews per Month by Room Type and Neighbourhood Group
#### insights found from the chart
Certain neighbourhood groups (like Bronx) has higher reviews for Entire Home/Apt listings, indicating a strong demand for these properties in premium locations. This reflects the nature of travelers frequenting these areas, such as tourists or business travelers willing to pay for comfort.
Other neighbourhood groups (like Staten Island and Queens) are showing a more balanced demand for both Private Rooms and Entire Homes, indicating a diverse range of guests with varying budgets.

#### positive business impact
Strategic Pricing and Inventory Management: The insights gathered can help Airbnb hosts and property managers adjust their pricing strategies based on demand for different room types in various neighbourhoods.
Marketing Strategies: By identifying which room types are most popular in specific areas, businesses can tailor their marketing campaigns to highlight those properties, attracting more guests.
Focus on Improvements: Understanding trends in guest preferences can guide hosts in enhancing their properties, focusing on amenities and services that align with what travelers are seeking.

### 6. Reviews Based on Price in Different Neighbourhood Groups
#### insights found from the chart
Low-Priced Listings Have More Reviews, This suggest that budget-friendly accommodations are more popular and receive more bookings, leading to higher review counts.
High-Priced Listings Have Fewer Reviews, This indicate that luxury or expensive listings are booked less frequently or cater to a more niche market.
Manhattan: Manhattan has shown a broader price range, with some listings priced extremely high, but many of these expensive listings received fewer reviews. Mid-range priced listings in Manhattan seem to got more reviews.
Brooklyn: Brooklyn has shown a denser cluster of listings with moderate pricing, and these moderately priced listings tend to have higher review counts.
Bronx: The Bronx has shown lower-priced listings overall, and some of them likely got a high number of reviews, indicating popularity in budget accommodation.

#### positive business impact
Positive Business Impact: Insights help property owners refine pricing strategies, focus on high-demand neighborhoods, and improve guest experiences, leading to better business performance.

Risks: Negative growth may occur due to market oversaturation, underutilization of high-end properties, or mismatches between offerings and customer preferences. Addressing these potential issues with strategic changes can mitigate negative outcomes and promote sustained growth.

### 7. Average Availability Year-round by Neighbourhood Group
#### insights found from the chart
From the bar chart demonstrating average availability year-round across different neighbourhood groups, the key insight is that areas like Manhattan and Brooklyn tend to have lower availability, indicating that properties in these neighborhoods are booked more frequently, likely due to higher demand. In contrast, neighborhoods such as the Bronx and Staten Island show higher availability, suggesting lower booking rates or less popularity among travelers.

#### positive business impact
The gained insights can create a positive business impact by highlighting high-demand areas like Manhattan and Brooklyn, where properties have lower availability due to frequent bookings. This allows hosts to focus on optimizing pricing and managing high-demand listings more effectively. Conversely, neighborhoods with higher availability, such as the Bronx and Staten Island, might require targeted marketing or adjusted pricing strategies to improve occupancy.

A potential risk for negative growth is oversaturation in popular areas, leading to increased competition and price drops. Additionally, properties in lower-demand areas might struggle with low occupancy, negatively affecting revenue unless strategies are adjusted accordingly.

### 8. Room count across NYC based on the listing of room types
#### insights found from the chart
Manhattan has the highest number of listed properties, with Entire home/apt making up around 25.7% of the total listings, followed by Brooklyn at approximately 21%.
Private rooms are more common in Brooklyn, accounting for 20.6% of the total listings, followed by Manhattan with 16.2%. Additionally, 6.9% of private rooms are located in Queens.
In summary, Brooklyn, Queens, and the Bronx have a higher proportion of private room listings, while Manhattan, which has the most listings in all of NYC, primarily features Entire home/apt room types.

#### positive business impact
The gained insights can drive a positive business impact by helping hosts focus on offering Entire Home/Apt listings, which are in higher demand and typically managed by professional hosts. This can guide investment decisions, allowing hosts to scale their property portfolios more effectively. For smaller hosts, focusing on Private Rooms can attract budget-conscious travelers.

However, a potential for negative growth arises if hosts overly concentrate on one room type, leading to market saturation, especially in the Entire Home/Apt segment. This could drive down prices and reduce profitability. Additionally, neglecting Shared Rooms may miss out on niche markets.

### 9. Number of Reviews vs. Reviews per Month
#### insights found from the chart
Listings with higher reviews per month is generally tend to accumulate a larger number of total reviews, indicating higher activity and guest turnover.

#### positive business impact
The insights from the scatter plot positively impact the business by identifying high-performing listings with frequent reviews, allowing hosts to model successful strategies for pricing or guest experiences. Properties with high reviews per month but fewer total reviews indicate newer or recently improved listings, which can help focus marketing efforts.

However, listings with consistently low reviews per month and total reviews suggest lower demand or issues that could lead to negative growth if not addressed. These properties may require adjustments in pricing, amenities, or marketing to remain competitive.

### 10. Distance from Prime Location to Availability by Room Type
#### insights found from the chart
Availability Trends: Listings closer to the prime location shown varying availability patterns compared to those further away, indicating demand fluctuations based on proximity.
Room Type Differences: Different room types (entire home/apt, private room, shared room) have distinct availability trends, highlighting preferences among guests.

#### positive business impact
The insights gained from the scatter plot can indeed help to understanding the correlation between proximity to prime locations and availability can inform pricing strategies, leading to optimized occupancy rates and increased revenue for hosts.

### 11. Average Price vs Year of Last Review
#### insights found from the chart
As we can see in the above line chart, the average price was initially between 160-180 Dollar in 2011. In 2012, it slightly decreased, but in 2013, it substantially increased to 260$. In 2014, it significantly dropped to 160 Dollar, and after 2014, it continued to decrease until 2017. However, in 2018, it started rising again.

#### positive business impact
Knowing that prices increased significantly in 2013 and then dropped again by 2014 can help businesses assess factors that contributed to price fluctuations. By understanding historical trends, Airbnb hosts can adjust their pricing strategies to capitalize on periods when prices typically rise (like in 2018).

If the price drop from 2014 to 2017 was due to lower demand, it might indicate that customer preferences or external factors (e.g., regulations, competition) affected prices. Businesses can leverage these insights to improve customer experiences, increase amenities, or focus on competitive pricing during lower demand periods.

### 12. Proportion of Host Listings by Room type
#### insights found from the chart
the pie chart shows a larger slice(71.3%) for "Entire home/apt," it indicates that this room type has the highest share of host listings, which can inform business decisions related to room offerings. lower slice(2.0%) for "Shared room" indicating the lower share of host listings and medium Slice (26.7%) for "Private room" indicating the average share of host listings.

#### positive business impact
The pie chart shows that "Entire home/apt" makes up 71.3% of host listings, indicating it is the most preferred room type among hosts and guests. This suggests a high demand for entire homes/apartments, making it a lucrative focus for business expansion.

Meanwhile, "Private rooms" (26.7%) also hold significant market share, offering opportunities for mid-range, budget-conscious travelers. The lower share (2.0%) for "Shared rooms" suggests limited demand, so businesses should allocate fewer resources to this option and instead focus on the more popular room types to maximize profitability.

### 13. Correlation Heatmap
#### insights found from the chart
Weak correlations exist between price and minimum nights, number of reviews, and reviews per month, indicating that price does not significantly influence these factors.
A strong positive correlation between the number of reviews and reviews per month indicates popular listings receive consistent engagement. Listings with more reviews tend to have higher availability.
A weak positive correlation with availability suggests hosts with more listings might have properties available more frequently.

### 14. Price vs. Minimum Nights in Different Neighbourhood_group
#### insights found from the chart
Price Correlation: Price shown varying relationships with other factors, like availability and minimum nights, indicating pricing's influence on demand.
Reviews: A possible correlation between the number of reviews and reviews per month suggests high guest turnover for certain listings.
Distribution Patterns: The distributions of price, reviews, and availability indicate whether these variables are skewed or evenly spread across the dataset.
Outliers: Several outliers are identified, such as listings with extreme prices or unusually long minimum night requirements.

## Solution to Business Objective
- Airbnb host should offer discounts or special deals during off-peak seasons to attract more bookings in less popular times, especially in neighborhoods with lower occupancy.
- Focus on Popular Room Types: There should be Highlight entire homes/apartments in marketing campaigns for areas like Manhattan and Brooklyn, which can attract tourists seeking privacy and space.
- Promote Private Rooms in Budget-Friendly Areas: Create targeted ads for private rooms in neighborhoods like Brooklyn, Queens, and the Bronx to appeal to budget-conscious travelers.
- Should encourage hosts to enhance their listings with high-quality photos, detailed descriptions, and amenities that meet the needs of travelers, such as Wi-Fi, kitchen facilities, and flexible check-in options. so that we can imporve listings.
- Encourage Multi-Property Listings: Support successful hosts in expanding their portfolios to increase the number of listings in high-demand neighborhoods_group such as Manhattan, Brooklyn and so on, thereby capturing more market share.
- Airbnb host should implement a system for collecting guest feedback after their stay to identify areas for improvement and adapt strategies accordingly.
- Must foster a community among hosts in less popular neighborhoods to share insights and support each other in improving their listings and marketing strategies.

## Conclusion
- Room Type Preferences: Entire homes/apartments are the most popular option, particularly in high-demand areas like Manhattan and Brooklyn, while shared rooms are the least favored across all neighborhoods.
- Price and Reviews: Lower-priced listings in areas like Brooklyn, Bronx, and Staten Island receive more reviews, suggesting a strong demand for budget-friendly accommodations. High-priced listings in Manhattan tend to receive fewer reviews, indicating a niche market for luxury stays.
- Demand Fluctuation: Areas closer to prime locations, such as Manhattan, have lower availability, reflecting higher demand, whereas neighborhoods like the Bronx and Staten Island show higher availability due to lower booking rates.
- Pricing Strategies: Price shows weak correlations with availability, minimum nights, and reviews, indicating the need for flexible pricing based on demand trends and historical performance.
- Host Listings and Guest Engagement: Hosts with multiple listings tend to maintain higher availability, and properties with higher review counts show consistent guest turnover, especially in mid-range listings in Manhattan and Brooklyn.

In conclusion, targeting pricing strategies based on neighborhood demand, offering varied room types in budget-friendly areas, and leveraging guest feedback for improvements can help businesses enhance customer satisfaction and optimize profitability. Adjusting availability and pricing based on historical trends will also help maintain a competitive edge.



