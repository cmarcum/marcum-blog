---
layout: post
title: "A Really `Cool` New Data Set from Census"
date: 2026-05-12
tags: [general, open data, government]
---

Late last month, the US Census Bureau released a really cool new data product: the [Local Air Conditioning Estimates](https://www.census.gov/data/experimental-data-products/lace.html) or LACE. An experimental data product, LACE provides insights into air conditioning prevalence across the United States. This new data product is significant because it fills a critical information gap in our knowledge about energy use potential and vulnerability to extreme heat. 

One of the things I'm really excited about is the underlying methodology. The LACE estimates were derived using cross-survey modeling and leveraged machine learning to integrate detailed housing data from the American Housing Survey (AHS) with the comprehensive geographic coverage of the American Community Survey (ACS). Census is innovating here! 

## 
I am still a gerontologist at heart and I know one of the major perennial issues elders face each year is the challege of summer heat. Summer heat is especially dangerous for older adults because aging bodies lose several of the systems that normally protect people from overheating. I merged the new LACE estimates with ACS 5-year data regarding the population aged 65 and older at the county-level. By combining these datasets, we can visualize the distribution of households without air conditioning alongside the concentration of older residents. The code [is available here](https://github.com/cmarcum/talks-and-posts/tree/main/2026-06-12-LACE-and-Age) (and requires a free Census API key).

The map below visualizes these metrics by representing the percentage of occupied households without air conditioning. Darker tones indicate a higher proportion of homes lacking cooling systems. If you hover over a county with your cursor (or finger if you're on a mobile device), a pop-up will display the percentage of households without AC and the percentage of the local population aged 65 or older. While I did not look at the bivariate correlation between the two, one thing I did notice in the viz is Appalachia looks particularly exposed due to its combination of high elder population and low AC coverage. It can get HOT in them hollers (today's [heat index is extreme](https://www.wpc.ncep.noaa.gov/heatrisk/) in many of those places). 

<div class="map-container" style="margin: 20px 0;">
  <iframe 
    src="{{ '/assets/leaflets/lace_o65_map.html' | relative_url }}" 
    width="100%" 
    height="600px" 
    style="border: none; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);" 
    title="Choropleth / Heatmap of County-Level Percent of Households with Air Conditioning">
  </iframe>
</div>
