# Assignment 3: Chicago Crime Data Analysis and Geospatial Visualization

## Overview
This project uses SQL and Python to analyze crime data from Chicago, with a focus on violent and gun-related crimes across police districts. By performing data queries and geospatial mapping, the project aims to provide insights into crime patterns, density, and proximity to police stations, visualized on interactive maps.

## Project Objectives
- Execute SQL queries to retrieve and process crime data by district, creating a clean dataset for analysis.
- Perform geospatial analysis to identify crime hotspots and visualize crime patterns across districts.
- Create interactive maps to display crime frequency, density, and proximity to police stations.

## Techniques and Tools Used
- **Data Querying**: SQL with PostgreSQL (using psycopg2) for querying and filtering data from the Chicago Crime and Police Stations datasets.
- **Data Visualization**: 
  - Folium for creating interactive maps, including Choropleth maps with marker clusters.
  - Seaborn for time-series scatterplot analysis of crime occurrences by hour.
- **Geospatial Analysis**: Using geospatial queries to analyze crime locations, calculate distances, and map crime density.

## Key Analysis Steps

### 1. Data Selection and Preparation
Selected key fields (`district`, `ward`, `arrest`, `primary_type`, `location_description`) from the crime dataset and loaded them into a DataFrame (`new_df`). This data served as the foundation for analysis and visualizations, confirmed through `.info()` and `.head()` outputs.

### 2. Arrest Patterns by Crime Type
Created a crosstab of `primary_type` and `arrest` status to analyze arrest rates by crime type. For example, **Assault** crimes demonstrated a higher arrest likelihood, suggesting a targeted focus on these offenses.

### 3. Gun Crime Density by District
Calculated gun crime density in each district, revealing areas with high concentrations of gun-related incidents relative to district size.

### 4. Mapping Total Crimes and Violent Crimes by District
- Generated a Choropleth map illustrating total crime numbers by district, with shading intensity proportional to crime frequency.
- Created another Choropleth map for violent crimes leading to arrests, featuring pins at police stations to show total violent crimes per hour for each district.

### 5. Detailed Mapping of Gun-Related Crimes by Location
Filtered gun-related crimes by `location_description` (RESIDENCE or STREET) and created marker clusters:
  - **Green markers** for residential locations.
  - **Red markers** for street locations.
Markers were placed at crime locations, showing spatial patterns of gun-related incidents.

### 6. Mapping the Farthest Gun Crimes from Police Stations
Identified and mapped the gun crime occurring at the farthest distance from each police station in every district. For each district:
- A Choropleth map was shaded by the number of gun crimes per district.
- Each district had a pop-up displaying the district number and the block where the farthest gun crime occurred.
- A small circle marker (radius of 5) marked the exact location of each farthest gun crime.

### 7. Crime Timing Trends
Using Seaborn, produced a scatterplot to examine hourly crime patterns for THEFT, BATTERY, ASSAULT, and ROBBERY:
- Crimes were lowest around 5 am, increasing through the day and peaking from 2 pm to 7 pm.
- **Theft** was the most frequent crime during peak hours, occurring 1.5 times more than battery and four times more than assault and robbery.

## Findings
- **Crime Density and Hotspots**: Identified districts with high overall and gun crime densities, allowing for targeted resource allocation.
- **Proximity to Police Stations**: Mapped the farthest gun crimes from each police station, providing insights into potential response challenges in remote areas.
- **Time-Based Crime Patterns**: Discovered high-frequency crime windows, supporting data-driven scheduling for law enforcement patrols.

This project demonstrates SQL, Python, and geospatial analysis techniques to uncover patterns in crime data, supporting strategic decision-making for public safety in Chicago.
