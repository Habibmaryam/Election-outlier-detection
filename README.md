# Outlier Detection Report
---

## 1. Methodology used for analysis
Geospatial Analysis:
Libraries Used: The analysis was performed using Python . Python libraries such as geopy for geospatial calculations, folium for map visualizations, and standard data manipulation libraries like pandas and numpy. Additionally, libraries such as requests, matplotlib, Sklearn and Scipy were used.

### Dataset:
The full addresses were used to generate latitudes and longitudes using geocoding methods. The analysis uses a dataset containing polling units with their respective latitude and longitude coordinates.

---
### Data Preprocessing: 

Data was cleaned and checked for missing values in the Sokoto crosschecked data set. Only one missing value was found in the longitude and latitude columns and dropped. Latitude and longitude values were converted from degrees to radians to facilitate the calculation of distances using the Haversine formula.

---
### Conversion of longitude and latitude coordinates to Radians.

The latitude and longitude values in the main_df DataFrame are converted from degrees to radians. This is often necessary for geographic calculations, as many libraries and algorithms expect coordinates in radians.
The numpy library is imported for its mathematical functions, specifically the radians() function. Two new columns, 'Latitude_radians' and 'Longitude_radians', are created in the main_df DataFrame to store the converted values. The np.radians() function is applied to the 'Latitude' and 'Longitude' columns of main_df, converting the values from degrees to radians. The converted values are stored in the newly created 'Latitude_radians' and 'Longitude_radians' columns.

The distance between each coordinate was calculated in miles to determine which points were closer to each other using the haversine formula. This was then stored in the distance data frame which was created initially.

The pairwise distance was also calculated to identify the neighbors around them.

### Calculating the outlier score
Outlier Scores: Z-scores were calculated for the distances to identify outliers. A high z-score indicates that a polling unit is geographically distant from others, suggesting it could be an outlier.


---
### 2. Summary of Findings
The analysis revealed several polling units that are significantly farther from others, indicating potential outliers. Polling units were ranked based on their outlier scores for each political party, with higher scores indicating more significant outliers.

---

### 3. Detailed Examples of the Top 3 Outliers
   
Here are the top 3 outliers identified in the analysis which is also show in the table below:

Outlier 1:
Polling Unit: Gagi ward B
Distance: Significant distance from the nearest polling units.
Outlier Score: Highest z-score indicating it is the most geographically isolated polling unit = 3.78

Outlier 2:
Polling Unit: Tudun wada ward A
Distance: Also shows a substantial distance from other polling units.
Outlier Score: Second highest z-score ~ 2.20

Outlier 3:
Polling Unit: S/Birni West ward A
Distance: Another polling unit with a significant distance from the rest.
Outlier Score: Third highest z-score ~ 2.16


---
### 4. Conclusion

Key Insights:
Geographical Isolation: The top outliers are geographically isolated from other polling units, which could impact voter accessibility and the efficiency of electoral processes.
Potential Issues: These outliers might indicate logistical challenges or errors in the dataset that need further investigation.

---
# The End
