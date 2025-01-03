# Analysis of Ottawa Neighbourhoods by Safety using KMeans


## Introduction
Ottawa is often ranked as one of Canada’s safest cities, but some areas within the city offer quieter and statistically safer environments. For new immigrants, students, families, or someone who prioritizes security, an important question is, "Which neighborhood or ward is the safest to settle in?"

This project leverages data-driven approaches to rank and group all 23 Ottawa wards by safety, providing actionable insights for residents, policymakers, and anyone considering a move to the city.

## Problem Statement
The goal of this project was to analyze safety across Ottawa's wards, grouping and ranking them from the safest to the most dangerous using machine learning and data visualization techniques. Specifically, the project focuses on six key crime categories to provide a comprehensive view of public safety:
- Auto Theft
- Bike Theft
- Criminal Offenses (e.g., Theft, Assaults, Break and Enter)
- Hate Crime
- Homicide
- Shootings

## Data Structure
The data for this project was obtained from the Ottawa Police Data Portal and includes:
1. Neighborhood Boundaries Map (GeoJSON):
    - Geospatial data for the city, divided into wards, used for creating detailed map visualizations.
2. Criminal Incident Records:
    - Reports for each crime type (Auto Theft, Bike Theft, Criminal Offenses, Hate Crime, Homicide, and Shootings), which served as benchmarks for the analysis.

All datasets are available in the 'Data' folder. - [DATA](https://github.com/Lekan-E/Analysis-of-Ottawa-Neighbourhoods-by-Safety/tree/main/Data)

## Machine Learning
### Clustering Ottawa Wards
A clustering algorithm, “k-means”, was used to group the neighbourhoods in order of safety/crime rate. KMeans clustering algorithm, an unsupervised machine learning technique, to group Ottawa’s wards based on their safety and crime rates.

### Steps for Clustering Ottawa Wards
The steps below were used to segment the wards:

1. Data Wrangling: 
    - This process involves combined and aggregated all the records by ward, counting each crime type (e.g., Hate Crime, Auto Theft) to create a single DataFrame with individual safety types as columns.

    ![alt](https://github.com/Lekan-E/Analysis-of-Ottawa-Neighbourhoods-by-Safety/blob/6b0901e5d5d9f482be54b07e2f5e97cc7c3354d3/Images/image.png)

2. Determine the Optimal Number of Clusters:
    - Used the “Elbow Method” to find the ideal number of clusters. While the first elbow suggested three clusters, I opted for six to provide a more granular grouping.

3. Cluster Analysis:
    - Compared the average number of crimes per group to evaluate and interpret the clusters.

    ![alt](https://github.com/Lekan-E/Analysis-of-Ottawa-Neighbourhoods-by-Safety/blob/2e1c8ef692d1dee3fea4f5674b7868be050cb4a4/Images/thredcluster.png)

Check out the Jupyter Notebook for step-step analysis - [NOTEBOOK](https://github.com/Lekan-E/Analysis-of-Ottawa-Neighbourhoods-by-Safety/blob/main/Analysis%20of%20Ottawa%20Safety%20using%20ML.ipynb)


## Insights Deep-Dive
From the results of the analysis, the following insights were derived about Ottawa’s neighborhoods:

1. Safest but Far-Out Neighborhoods
These wards, located farther from downtown Ottawa, are the safest and offer peaceful, serene communities. They are ideal for families or individuals seeking tranquility. However, these areas often lack amenities within close proximity and heavily rely on private vehicles for transportation.
    - Wards: Osgoode, Riverside South-Findlay Creek, Rideau-Jock, Stittsville, Kanata South, Kanata North, West Carleton-March

2. Most Desirable Neighborhoods
These wards balance safety with better public transit options, connecting residents to downtown Ottawa and surrounding areas. They are especially appealing to students, new immigrants, and those seeking a safe yet accessible community with a good balance of affordability and transit connectivity
    - Wards: Bay, College, Knoxdale-Merivale, River, Alta Vista, Beacon Hill-Cyrville, Rideau-Rockcliffe

3. Safe with Risks
Neighborhoods like Kitchissippi and Capital sit in a "grey zone" between safety and danger. While they provide excellent accessibility to downtown Ottawa, safety risks arise due to the presence of shelters and higher concentrations of vulnerable populations in these areas.
    - Wards: Kitchissippi, Capital

4. Areas to Avoid (If Possible)
The two downtown wards consistently recorded the highest crime rates. While these areas offer proximity to virtually all major city amenities, they come with significant safety risks and higher living costs. These wards are less ideal for long-term residential purposes unless proximity to amenities outweighs safety concerns.
    - Wards: Rideau-Vanier, Somerset


The final safety rankings were visualized on a map using GeoPandas.

![alts text](https://github.com/Lekan-E/Analysis-of-Ottawa-Neighbourhoods-by-Safety/blob/abbe9f00112a2091c6a5e5208ec2fbf2d7e2131c/Images/clustermap2.png)

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

## Safety Rank
An ordered rank of each 23 wards from safest to most dangerous sorted by a generated safety score.
1. West Carleton-March - 293.05
2. Rideau-Jock - 401.90
3. Osgoode - 540.45
4. Riverside South-Findlay Creek - 550.45
5. Stittsville - 731.95
6. Kanata North	- 750.90
7. Barrhaven East - 785.70
8. Orléans East-Cumberland - 817.30
9. Orléans West-Innes - 846.75
10. Kanata South - 894.25
11. Barrhaven West - 1048.75
12.	Orléans South-Navan - 1175.20
13.	Knoxdale-Merivale - 1289.60
14.	River - 1652.45
15.	Beacon Hill-Cyrville - 1687.35
16.	Gloucester-Southgate - 1809.85
17.	Rideau-Rockcliffe - 1879.70
18.	College - 1916.05
19.	Bay	- 1920.15
20.	Alta Vista - 1944.75
21.	Kitchissippi - 2075.85
22.	Capital - 2116.85
23.	Somerset - 6618.55
24.	Rideau-Vanier - 6689.85
