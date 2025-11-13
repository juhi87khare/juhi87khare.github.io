---
name: IS445 Homework - UFO Sightings Analysis
tools: [Python, Altair, Vega-Lite, Data Visualization]
image: https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv
description: Interactive Altair/Vega-Lite visualizations analyzing UFO sightings patterns across time and geography
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# IS445 Homework: UFO Sightings Interactive Visualizations

## Project Overview

This project explores patterns in UFO sightings using the NUFORC (National UFO Reporting Center) dataset. Two complementary interactive visualizations reveal trends in reported UFO encounters across different time periods and geographic locations in the United States.

---

## Visualization 1: UFO Sightings by Shape Over Time

<vegachart schema-url="{{ site.baseurl }}/assets/json/visualization1_ufo_shapes.json" style="width: 100%"></vegachart>

### Description
This line chart visualizes the temporal trends of different UFO shape categories from 1910 to 2014. Each line represents a different UFO shape category, with the height indicating the annual count of sightings.

### Design Choices
- **Encoding Types**: 
  - X-axis: Year (temporal, ordinal)
  - Y-axis: Count of sightings (quantitative)
  - Color: UFO shape type (nominal, categorical)
  - Opacity: Interactive selection (highlights selected shape)
- **Color Scheme**: Tableau20 palette provides distinct colors for the top 5 UFO shapes (light, triangle, circle, fireball, unknown)
- **Interactivity**: Dropdown selector allows users to filter and highlight specific UFO shapes while keeping other shapes visible at reduced opacity.

### Data Transformations
- Filtered dataset to US-only sightings
- Aggregated records by year and shape type
- Selected top 5 UFO shapes by frequency

---

## Visualization 2: Geographic Distribution of UFO Sightings

<vegachart schema-url="{{ site.baseurl }}/assets/json/visualization2_ufo_geographic.json" style="width: 100%"></vegachart>

### Description
This scatter plot shows the spatial distribution of UFO sightings across the United States. Each point represents a reported UFO sighting.

### Design Choices
- **Encoding Types**:
  - X-axis: Longitude (quantitative, geographic)
  - Y-axis: Latitude (quantitative, geographic)
  - Size: Duration of sighting (quantitative)
  - Color: Decade of sighting (nominal, temporal grouping)
- **Color Scheme**: Viridis palette (colorblind-friendly)
- **Interactivity**: Pan and zoom capabilities for exploration

---

## Data & Analysis

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/ufo-scrubbed-geocoded-time-standardized-00.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/juhi87khare/juhi87khare.github.io/blob/main/python_notebooks/hw.ipynb" text="The Analysis" %}
</div>
