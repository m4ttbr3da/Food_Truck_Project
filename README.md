# Research Motivation and Summary
*Research question: If you were a food truck operator (or aspiring one), where would the most ideal location be to conduct your business?
Using search and location data, is it possible to predict areas that are more likely to draw in customers who will leave Yelp reviews?*

![image](https://user-images.githubusercontent.com/69601778/118575355-22d0e100-b73b-11eb-842a-d03425120c3b.png)


# Hypothesis: Higher review counts across food trucks in Los Angeles can be explained at least in part by location-specific factors such as:
  * Food truck density
  * Population density
  * Median household income
  * Median home price

# Key Assumptions:
  * Review counts are predictive of business success, as higher review counts should correspond with higher overall customer volume.
  * Higher review counts are worth targeting (over review scores for example), as businesses with higher review counts show up higher in search results and create efficient marketing feedback loops.
  * Zipcode level demographic information is representative of the available food truck locations in a given zipcode.
  * The addresses listed on Yelp are reflective of current business locations.

# Food Truck Density by Zipcode in Los Angeles
![image](https://user-images.githubusercontent.com/69601778/118578962-fc627400-b741-11eb-8db4-707bbb66652e.png)


# Summary Results
Looking at the nearly 600 food trucks in our data set:
1) Review counts for food trucks tend to skew very low (generally below 200)
2) Demographic variables appear to play a limited role in predicting higher Yelp review counts for specific food trucks
3) Demographic variables may play a role in explaining average review counts by zipcode

# Summary of Data Collection Process
![image](https://user-images.githubusercontent.com/69601778/118564253-d9759700-b724-11eb-9321-7093329ac194.png)

  * The Yelp Fusion API was the most helpful in pulling the information needed because we could search by “food truck” as a category.  
  * The goal was to capture as many unique businesses listed as food truck in order achieve a higher sample.
  * By utilizing the PyPi module USZIPCODES, which uses census data, we were able to cross match the zip codes attained from the Yelp API call with Median Home Value, Median Household Income, and Population Density in order to analyze the neighborhood.
  * The Google Maps API was helpful for visualizing geographic layout of the food trucks in our data set, using latitude and longitude coordinates from Yelp

# Distribution of Review Counts Across Food Trucks
*Research question: How are review counts distributed among food trucks?* 
  * Hypothesis: Food truck review counts are likely heavily concentrated among the most instagrammable food trucks with the best locations to drive food traffic.
  * Result: Food truck review counts at the are highly concentrated at the high end of the sample; 85% of food trucks in our sample receive 200 reviews or less
 
 ### Review Count Distribution Across L.A. Food Trucks – Initial Pull from Yelp (n = 559)
![image](https://user-images.githubusercontent.com/69601778/118564448-1e99c900-b725-11eb-86d3-f62c1dee7e5b.png)
### Histogram of Review Counts - Filtered for Food Trucks with Under 200 Reviews (n = 474)
![image](https://user-images.githubusercontent.com/69601778/118564473-2bb6b800-b725-11eb-87f7-aad54eb88956.png)

# Linear Regression Analysis
*Research question: Is there a statistical relationship between a food truck’s review count and the demographic features of the zipcode it operates in?*
  * Hypothesis: Food truck review counts are likely to be correlated with areas that have high disposable income – e.g. high median home values, high median household incomes, and low population density.
  * Result: We found virtually zero statistical relationship between individual food truck review counts and median home values, median household incomes, and population density.

## L.A. Food Trucks with Under 200 Reviews - Review Counts vs. Median Household Income
![image](https://user-images.githubusercontent.com/69601778/118579116-49464a80-b742-11eb-951b-3899b8b8b0e7.png)

# Additional Analysis: Average Review Counts by Zipcode
*Research question: Instead of looking at individual review counts, is there a relationship between zipcode-level average review counts and demographic characteristics of the zipcode?*
  * Hypothesis: Average food truck review counts are likely to be correlated with areas that have high disposable income – e.g. high median home values, high median household incomes, and low population density.
  * Result: Among the top 20 zipcodes by average review count, there appears to be a clear visual trend between average review counts by Zipcode and median home values, median household incomes, and population density.

![image](https://user-images.githubusercontent.com/69601778/118564699-a1bb1f00-b725-11eb-8d1d-2e29b2b0bf99.png)
![image](https://user-images.githubusercontent.com/69601778/118564767-c57e6500-b725-11eb-9c85-6d7d155bd95f.png)
![image](https://user-images.githubusercontent.com/69601778/118564779-cadbaf80-b725-11eb-92c6-51c6c881aa9c.png)

# Areas for Further Analysis
  * Segment analysis by cuisine type
  * Could use Google Places to attempt to backfill
  * Normalize values in current linear regression analysis
  * Linear regression on average review counts

 
