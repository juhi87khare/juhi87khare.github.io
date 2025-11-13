---
name: Homework, Vega/Altair Plots
tools: [Python, Altair, vega-lite]
image: assets/pngs/fromvegaeditor.png
description: A series of plots in a few ways.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Plots Using Altair, A few Ways


<vegachart schema-url="{{ site.baseurl }}/assets/json/direct_from_editor.json" style="width: 100%"></vegachart>


# 2. From Vega-Specs to JSON with Altair in Python

We start from just copying the specification from our [Starboard notebook](https://starboard.gg/jnaiman/inClass_week10_spring2023-nJGY2kn) of previous weeks using the `from_dict` function in Altair.  With some judicious use of adding/subtracting quotation marks (we have to be a bit more careful with these in Python) we can recreate a simple histogram showing the count of records in our [Mobility dataset](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/mobility.csv) as a function of state:

<vegachart schema-url="{{ site.baseurl }}/assets/json/chart1.json" style="width: 100%"></vegachart>

We did this by saving our Altair chart as a JSON file in our assets folder in this Jekyll page's repository and embedding it using the `vegachart` plug in HTML tag:
```
<vegachart schema-url="{{ site.baseurl }}/assets/json/chart1.json" style="width: 100%"></vegachart>
```

# 3. Dashboard Building

For more complex layouts and to support some interactivity and linking of data, we can start to making some of our plots more "Altair friendly".  For example, breaking our two dashboard plots from our prior [Starboard notebook](https://starboard.gg/nb/n9nb6N8) into to charts and then using the `Hconcat` function in Altair to put them side-by-side:

<vegachart schema-url="{{ site.baseurl }}/assets/json/static_mobility.json" style="width: 100%"></vegachart>


<!-- If I want to have some control over the size, I can put this `vegachart` tag within an HTML `div` tag:

<div width="100px">
<vegachart schema-url="{{ site.baseurl }}/assets/json/static_mobility.json" style="width:600px"></vegachart>
</div>
-->

Now with interactivity:
<vegachart schema-url="{{ site.baseurl }}/assets/json/dashboard_mobility.json" style="width: 100%"></vegachart>

Neat!  But still, there are some weird things with this side-by-side concatination thing.

Let's re-make this plot once again, only using Altair syntax (not translating from vega-lite with `from_dict`).


# 4. Use Altair to make the chart

We first started making a scatter plot with Altair:
<vegachart schema-url="{{ site.baseurl }}/assets/json/population_scatter.json" style="width:600px"></vegachart>

And then we re-did the Mobility Dashboard, but this time using all Altair-style calls:
<vegachart schema-url="{{ site.baseurl }}/assets/json/altair_mobility_dashboard.json" style="width: 100%"></vegachart>

# 5. Python Analysis + Altair Plotting

Finally, we can do all of the data transformations and analysis in Python and then use Altair to export the cleaned/transformed data.

<vegachart schema-url="{{ site.baseurl }}/assets/json/altair_mobility_data_dashboard.json" style="width: 100%"></vegachart>



<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_bcubcg_fall2022/blob/main/data/mobility.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_bcubcg_fall2022/blob/main/week11/prep_notebook_week11.ipynb" text="The Analysis" %}
</div>

