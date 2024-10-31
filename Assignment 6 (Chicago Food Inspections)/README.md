# Food Safety and Risk Analysis of Chicago Children Daycare Facilities

## Overview
This project analyzes food inspection data in Chicago, with a focus on child-serving facilities, to highlight inspection hotspots and identify frequent violators. Using ElasticSearch for NoSQL querying and Folium for geospatial visualization, this project investigates high-risk facilities with recurrent violations, aiming to improve inspection resource allocation and public health safety. The dataset comprises 164,953 inspection records from 2010 to 2018.

## Objective
To identify inspection hotspots across Chicago’s child-centered facilities and highlight frequent violators using NoSQL query techniques and heatmap visualizations. The goal is to enable city inspectors to target high-risk facilities effectively.

## Tools and Technologies
- **Python**: For data analysis.
- **ElasticSearch**: To perform NoSQL queries for retrieving inspection data.
- **Folium**: For heatmap visualization of high-risk and frequently violated inspection locations.

## Methodology
1. **Comparative Query Analysis**:  
   Child-related facilities were identified using terms like “Children” and “Child,” accounting for potential misspellings and variations.
   
   - **Experiment 1**: Regular expression query for "Children" yielded 601 hits, maximizing recall but possibly reducing precision.
   - **Experiment 2**: Fuzzy search for "Children" with fuzziness set to 1 returned 196 hits, optimizing precision with fewer results.
   - **Experiment 3**: Fuzzy search for "Children’s" resulted in 505 hits, balancing precision and recall.
   
   Queries for “Child” yielded even more results, with non-fuzzy searches returning the most hits (774) and “Child’s” with fuzziness returning the fewest (24). Compared to "Children," these queries broaden the dataset and capture more records, increasing recall but reducing precision in some cases.

3. **Frequent Violators Analysis**:
   - **Experiment 4**: Facilities serving children that failed inspections with high-risk levels at least five times were identified and plotted on a heatmap.
   - A table of frequent violators, showing the DBA name, number of violations, and business licenses, highlights repeat offenders with three or more licenses issued.

4. **Heatmap Analysis**:
   - Facilities with high-risk violations and MICE DROPPINGS in their inspection reports were plotted on a city-wide heatmap. The keyword "MICE DROPPINGS" matched 4,549 records, illustrating prevalent rodent issues in certain areas.

## Summary
This project provides critical insights into inspection patterns across Chicago, pinpointing high-risk and frequently violated child-serving facilities. Query experimentation with ElasticSearch improves precision and recall, while heatmap visualizations reveal hotspots to guide more efficient allocation of inspection resources. These findings underscore the importance of targeted inspection strategies to safeguard public health in Chicago’s child-centered food facilities.

