# Analysis of Ottawa Neighbourhoods by Safety using KMeans


## Introduction
Ottawa is consistently ranked as one of Canada’s safest cities, but some areas within the city offer quieter and statistically safer environments. As a new immigrant, student, or someone who prioritizes security, you might ask, "Which neighborhood or ward is the safest to settle in?"

## Problem Statement
The goal of this project was to analyze all 23 Ottawa wards, grouping and ranking them from the safest to the most dangerous using machine learning and data visualization techniques. I conducted the analysis by focusing on the following crime types:
- Auto Theft
- Bike Theft
- Criminal Offenses (e.g., Theft, Assaults, Break and Enter)
- Hate Crime
- Homicide
- Shootings


## Data Structure
The data for this project was obtained from the Ottawa Police Data Portal and includes:
1. Neighborhood Boundaries Map (GeoJSON):
    - Geospatial data for the city, divided into wards, which was critical for creating map visualizations.
2. Criminal Incident Records:
    - Reports for each crime type (Auto Theft, Bike Theft, Criminal Offenses, Hate Crime, Homicide, and Shootings), which served as benchmarks for the analysis.

All datasets are available in the 'Data' folder.


## Insights



## Machine Learning
### Clustering Ottawa Wards
A clustering algorithm, “k-means”, was used to group the neighbourhoods in order of safety/crime rate. KMeans clustering algorithm, an unsupervised machine learning technique, to group Ottawa’s wards based on their safety and crime rates.

### Steps for Clustering Ottawa Wards
The steps below were used to segment the wards:

1. Data Wrangling: 
    - This process involves combined and aggregated all the records by ward, counting each crime type (e.g., Hate Crime, Auto Theft) to create a single DataFrame with individual safety types as columns.

2. Determine the Optimal Number of Clusters:
    - Used the “Elbow Method” to find the ideal number of clusters. While the first elbow suggested three clusters, I opted for six to provide a more granular grouping.

3. Cluster Analysis:
    - Compared the average number of crimes per group to evaluate and interpret the clusters.


## Results
The clustering results ranked wards into six categories of safety. The clusters and their respective safety levels are as follows:

- Most Dangerous Wards:
    - Cluster 3 (pink): Rideau-Vanier
    - Cluster 1 (green): Somerset

- Moderately Safe Wards:
    - Cluster 5 (light blue): Gloucester-Southgate
    - Cluster 2 (purple): Barrhaven West, Kitchissippi, Capital, Orleans East-Cumberland, Orleans South-Navan

- Safest Wards:
    - Cluster 0 (blue): Bay, College, Knoxdale-Merivale, River, Alta Vista, Beacon Hill-Cyrville, Rideau-Rockcliffe
    - Cluster 4 (light green): Orleans West-Innes, Osgoode, Riverside South-Findlay Creek, Rideau-Jock, Stittsville, Kanata South, Kanata North, West Carleton-March

The final safety rankings were visualized on a map using GeoPandas.

Below are the cluster and their corresponding wards:
3 - Rideau-Vanier
1 - Somerset
5 - Gloucester-Southgate
2 - Barrhaven West, Kitchissippi, Capital, Orlean East-Cumberland, Orleans South-Navan
0 - Bay, College, Knoxdale-Merivale, River, Alta Vista, Beacon Hill-Cyrville, Rideau-Rockcliffe
4 - Orlean West-Innes, Osgode, Riverside South-Findlay Creek, Rideau-Jock, Stittsville, Kanata South, Kanata North, West Carleton-March

![alts text](https://github.com/Lekan-E/Analysis-of-Ottawa-Neighbourhoods-by-Safety/blob/abbe9f00112a2091c6a5e5208ec2fbf2d7e2131c/Images/clustermap2.png)

## Insights Deep-Dive
From the results of our analysis, we can make the following deductions:
- the further away from the downtown otttawa, th
