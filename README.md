# Project 2: Inferring Significant Locations

This project uses GPS data collected from Google Maps Timeline and applies clustering techniques and place labeling through the Google Places API to identify frequently visited and personally meaningful locations.

## Hypothesis
GPS clusters representing repeated visits can be accurately labeled using the Google Places API and manually verified to show meaningful locations.


## Data
- Source: Google Takeout (Maps Timeline)
- Date Range: February 5 to March 25, 2025
- Total Records: 259 visit points
- Filtered: Visits lasting more than 5 minutes
- Fields: Latitude, Longitude, Start Time, End Time, Duration


## Methods
- DBSCAN was used to group spatially close GPS points into meaningful clusters.
- Cluster centroids were queried using the Google Places API to assign place names and types.
- Each cluster label was verified and categorized as:
  - Correct – label matched the exact place
  - Partial – label referred to a nearby location
  - Incorrect – label was unrelated or unvisited
- Visualizations in Code:
  - Map of clustered locations (Figure 1)
  - Bar chart showing label accuracy count (Figure 2)
  - Pie chart showing label accuracy percentages (Figure 3)
  - Top 10 most visited locations (Figure 4)

## Results
- Total Clusters Analyzed: 30
- Correct Labels: 19 (61.29%)
- Partially Correct Labels: 5 (16.13%)
- Incorrect Labels: 7 (22.58%)
- Most Visited Location: "My Apartment"

## Limitations
- The Google Places API occasionally returned nearby but incorrect or vague labels, especially for residential areas.
- Manual label verification is subjective and not scalable.
- Clustering is sensitive to parameter tuning such as search radius and minimum points.
- The dataset reflects a single individual’s activity over a limited two-month period.

## Conclusion, Future Work, and Insights
Clustering GPS data and labeling with public APIs can uncover meaningful behavioral patterns. The method successfully identified significant places and revealed that automated labeling tools can be effective but should be paired with human validation. Future improvements could include integrating more data across a longer timeframe and refining evaluation methods.
