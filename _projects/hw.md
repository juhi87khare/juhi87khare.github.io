---
name: IS445 Homework - Illinois License Analysis
tools: [Python, Altair, Vega-Lite, Data Visualization]
image: assets/pngs/licenses_thumb.png
description: Altair/Vega-Lite exports from Workspace.ipynb that examine Illinois professional licensing patterns using licenses_fall2022.csv
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# IS445 Homework: Illinois Professional Licensing Visualizations

## Project Overview

The Altair charts for this page are authored in `python_notebooks/Workspace.ipynb`, then exported to lightweight Vega-Lite JSON specs (`assets/json/licenses_*.json`) so they can be reused on the static Jekyll site without rerunning the notebook. Both charts use `licenses_fall2022.csv`, a snapshot of Illinois Department of Financial and Professional Regulation (IDFPR) records containing 10k licenses across dozens of professions. I standardized the categorical text, parsed the date stamps, and engineered an `issue_year` helper column so I could explore both the current mix of active credentials and how issuance volume changes through time.

---

## Visualization 1: Active Licenses by Profession

<vegachart schema-url="{{ site.baseurl }}/assets/json/licenses_active_by_type.json" style="width: 100%"></vegachart>

I filtered the dataset to rows whose `License Status` equals **ACTIVE**, grouped by `License Type`, and sorted the counts to surface the ten most common credentials. The horizontal bar chart encodes license type on the vertical axis, while the x-axis shows a quantitative count of active credentials; tooltips report exact totals. I kept the palette to a single saturated blue so the viewer focuses on length/comparison rather than decoding additional categories. This view immediately highlights how cosmetology and nursing dominate the registry while specialized boards (like respiratory care) trail far behind.

---

## Visualization 2: Interactive Issue Trends for Top Professions

<vegachart schema-url="{{ site.baseurl }}/assets/json/licenses_issue_trends.json" style="width: 100%"></vegachart>

To examine how licensing surges change over time, I parsed `Original Issue Date` into a proper timestamp, extracted the year, kept the five busiest license types overall, and aggregated counts by year/type combination. The line chart uses year on the x-axis, issuance counts on the y-axis, and color to distinguish professions. A dropdown-powered Altair selection injects custom interactivity: picking a profession from the list dims the non-selected lines (via the opacity channel), which makes it much easier to inspect the temporal rhythm for one license without losing the global context. Tooltips expose the exact number of licenses issued for that profession in each year.

---

## Data & Analysis

<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/juhi87khare/juhi87khare.github.io/blob/main/python_notebooks/Workspace.ipynb" text="The Analysis" %}
</div>

