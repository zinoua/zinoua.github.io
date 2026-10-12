---
layout: default
title: Project Update – Week 12
permalink: /week12.html
---

[Home](/) | [Week 9](/week9.html) | [Week 11](/week11.html) | [Week 12](/week12.html)

---

# Project Update – Week 12

**Is Syria's 2006–2010 Drought Unprecedented? A Historical and Modern Perspective**

## 1. From data preparation to exploratory analysis

After spending Week 11 obtaining and cleaning my datasets, I have shifted toward comparing drought conditions across different timescales and visualizing the results. My main challenge is finding fair ways to compare a five-year drought against records with very different sampling frequencies and geographical coverage.

This week, I developed an interactive Plotly visualization for the Gejkar Cave isotope record and expanded my PDSI analysis from individual months to rolling five-year averages. Both analyses investigate the same drought, but they use different measures of climate and cover different historical periods.

## 2. Interactive visualization: Gejkar Cave

The interactive figure below shows mean oxygen-isotope values (δ¹⁸O) for five-year windows in the Gejkar Cave record from northern Iraq. Higher δ¹⁸O values are generally associated with drier conditions at this cave, although the isotope signal is also influenced by factors such as temperature, moisture sources, and cave hydrology.

Each point represents a five-year window containing at least three isotope measurements. The vertical bars show the observed minimum and maximum within that window; they are **not confidence intervals**. The 2006–2010 interval is highlighted in red. Hovering over a point shows its dates, sample count, and isotope measurements.

<iframe
  src="/assets/gejkar_5yr.html"
  width="100%"
  height="600"
  style="border:none;"
  title="Interactive Gejkar Cave five-year isotope comparison">
</iframe>

The shaded areas distinguish a period without samples from a later period with measurements that are too sparse to produce five-year windows meeting the three-sample requirement.

## 3. What the Gejkar analysis reveals

The 2006–2010 window has a mean δ¹⁸O of **−3.137‰ VPDB**, calculated from five measurements. It has the highest mean among the **94 qualifying five-year windows**, including the modern interval. The next highest is 2001–2005, with a mean of approximately −3.66‰.

However, the historical coverage is uneven. There are no cave measurements between approximately 351 and 933 CE. Between about 933 and 1896 CE, measurements exist, but the five-year windows do not meet my main three-sample requirement.

I tested how the result changes when I require different minimum numbers of measurements:

| Minimum samples per window | Historical windows retained | Historical windows with equal or higher mean δ¹⁸O |
|---|---:|---:|
| 2 | 313 | 0 |
| 3 | 93 | 0 |
| 4 | 46 | 0 |

The modern interval remains the highest under all three thresholds. This makes the result less dependent on my choice of minimum sample count, but the number of historical windows available for comparison changes considerably. These five-year windows are also non-overlapping, so their placement may influence which historical events are captured.

**This does not establish that the 2006–2010 drought was unprecedented across the entire historical record.** Gejkar is a cave in northern Iraq rather than a direct rainfall record for Syria, and gaps, irregular sampling, and age uncertainty limit comparisons of short events.

## 4. PDSI: Comparing five-year drought severity

My earlier PDSI plot showed monthly drought conditions across the Fertile Crescent and identified **May 2008** as the driest individual month in my regional series, at approximately **−4.96**. But one extreme month cannot tell us whether an entire five-year drought was unprecedented.

To compare periods of equal duration, I calculated a **60-month rolling mean** of regional PDSI. Each point represents the average of that month and the preceding 59 months, giving a full five years of observations. Lower PDSI values indicate drier conditions. I compared the January 2006–December 2010 mean with rolling windows ending before 2006.

![Five-year rolling average PDSI for the Fertile Crescent, highlighting the 1958–1963 and 2006–2010 drought intervals](/assets/pdsi_5yr.png)

*Figure: Regional PDSI averaged over rolling 60-month windows. Each point is plotted at the end of its five-year window. The highlighted intervals identify the modern drought and the driest earlier comparison period.*

The **2006–2010 mean PDSI was −1.416**. Of the **1,501 earlier rolling five-year windows**, approximately **99.5% had higher (wetter) mean PDSI**. Only eight earlier windows were as dry or drier.

Those eight windows were not eight separate drought events. They overlap heavily and all belong to an earlier dry episode around **1958–1963**. The lowest earlier five-year mean was approximately **−1.589**, for **April 1958–March 1963**.

This means that **2006–2010 was exceptionally dry in the instrumental regional record, but not the driest five-year interval** under this method. Because the rolling windows overlap, their count should not be treated as a count of independent drought events.

There are also spatial limitations. PDSI is available on a coarse 2.5° grid, and I included all grid cells touched by my Fertile Crescent polygon. The number of available regional cells also changes during the early part of the record. I still need to test how sensitive the historical comparison is to these choices before drawing a final conclusion.

## 5. Comparing the two climate records

The Gejkar and PDSI results offer different perspectives. The 2006–2010 isotope mean is the highest among qualifying Gejkar windows, while the regional PDSI record includes an earlier five-year interval around 1958–1963 that was drier by its index.

This is not necessarily a contradiction. The cave record reflects local environmental and hydrological processes, whereas regional PDSI estimates drought conditions across a much larger area. Their time coverage, sampling frequency, and uncertainties are also different. I cannot directly convert Gejkar δ¹⁸O values into PDSI values or assume that they describe identical drought conditions.

Together, they suggest that the answer to whether the drought was “unprecedented” depends on **which indicator, region, and timescale** I use.


## 6. Agricultural Responses to the Drought: FAOSTAT Analysis

Having examined how unusual the 2006–2010 drought was in the climate records, I turned to its agricultural context. Using FAOSTAT data from 1961–2014, I investigated changes in the yields and total production of four major Syrian crops: wheat, barley, lentils, and seed cotton.

I compared average yields during 2006–2010 with the preceding five years (2001–2005). I also examined the full historical record to see how drought-period harvests compared with earlier fluctuations. Because agricultural productivity has changed considerably over time, the recent five-year comparison is more informative than comparing absolute yields across the entire record.

### Historical agricultural yields

The first figure shows annual yields for all four crops from 1961 to 2014, with the drought period highlighted.

![Historical Syrian crop yields, 1961–2014](/assets/fao_historical_yields.png)

*Figure 3. Annual crop yields in Syria, measured in kg/ha. Each crop has its own vertical scale to make its historical fluctuations easier to examine.*

The historical records show substantial fluctuations in productivity, particularly for barley and lentils. Wheat and seed cotton also display longer-term changes, making it difficult to judge the severity of the drought using absolute historical minima alone.

### Comparing crops during 2006–2010

To compare crops with different typical yields, I normalized each annual yield to its crop's 2001–2005 average, setting that baseline to 100. For example, a value of 60 indicates a yield 40% below the pre-drought average.

![Normalized Syrian crop yields, 1996–2010](/assets/fao_normalized_yields.png)

*Figure 4. Crop yields expressed as percentages of their respective 2001–2005 averages. The graph includes earlier years to provide context for the selected baseline.*

The results reveal that the four crops did not respond uniformly during the drought.

| Crop | Average yield change, 2006–2010 | Lowest-yield year | Lowest year vs. baseline | Production change |
|---|---:|---:|---:|---:|
| Wheat | −16.5% | 2008 | −46.0% | −24.3% |
| Barley | +1.3% | 2008 | −66.8% | +8.2% |
| Lentils | −31.9% | 2008 | −77.5% | −33.5% |
| Seed cotton | −14.8% | 2010 | −33.4% | −31.1% |

*Table 1. Changes are relative to the 2001–2005 average. Production refers to total national output rather than yield per hectare.*

**Wheat and lentils experienced substantial declines.** Their average yields during the drought were 16.5% and 31.9% below the preceding five-year averages, respectively. Both reached their lowest drought-period yields in 2008. Lentils experienced the strongest sustained decline of the four crops, and their 2008 yield of 251.3 kg/ha was lower than any year between 1961 and 2005. The previous minimum was 257.5 kg/ha in 1973.

**Barley presents a more complicated pattern.** Its yield in 2008 was 66.8% below the pre-drought average, yet its average across 2006–2010 was actually 1.3% higher. Stronger harvests in other years offset the severe decline in 2008. However, the result is highly sensitive to the chosen baseline. Barley yields in 2000 and 2001 were only 160.9 and 150.1 kg/ha, both lower than the 2008 yield of 182.2 kg/ha. Excluding 2001 from the baseline changes the estimated drought-period yield change from +1.3% to −14.3%. This illustrates how a five-year average can conceal severe annual fluctuations, particularly for highly variable crops.

**Seed cotton followed a different trajectory.** Its 2008 yield was only 3.9% below the pre-drought average, while wheat, barley, and lentils experienced much larger declines that year. Cotton's lowest drought-period yield occurred later, in 2010, at 33.4% below the baseline. The different timing is interesting given cotton's predominantly irrigated cultivation, but the data cannot establish whether irrigation explains the pattern.

### Yield, production, and harvested area

Changes in total agricultural production did not always match changes in yield. This distinction is particularly apparent for cotton, whose average yield declined by 14.8% while national production declined by 31.1%.

To investigate this difference, I estimated annual harvested area using total production divided by yield. Comparing the five-year averages, implied harvested area declined by approximately 18.8% for cotton and 10.3% for wheat. Barley's implied harvested area increased by about 8.0%, while lentils showed a smaller decrease of 1.9%.

These calculations suggest that changes in harvested area accompanied some of the changes in national agricultural output. However, harvested area is not the same as irrigated area, and these statistics do not establish why the changes occurred.

### Limitations and interpretation

The four crops also differ in their cultivation requirements. Barley and lentils are dependent on rainfall, while wheat is largely rainfed, some of it is irrigated, and seed cotton is predominantly irrigated. These differences could help explain their contrasting trajectories, but the national FAOSTAT data do not directly separate rainfed and irrigated production.

Overall, the agricultural records show substantial disruption during the drought interval, especially in 2008, but not a uniform decline across all crops or years. They also demonstrate why distinguishing annual extremes, five-year averages, and total production is important. The observed changes coincided with the drought, but additional evidence would be needed to determine how much was caused by climate rather than agricultural practices, irrigation access, or policy.

## 7. Challenges and next steps

My remaining work is to investigate the wider impacts of the drought and strengthen the sensitivity checks on the climate results. I plan to:

1. Examine regional temperature and potential evapotranspiration trends, taking seasonal variability into account.
2. Test whether different choices of PDSI spatial coverage change the five-year drought ranking.
3. Use AQUASTAT and UN population data as supporting context without treating national trends as proof that drought caused particular changes in irrigation or migration.

For the final project, I want to bring these analyses together into a clear narrative that distinguishes severe climatic conditions from their possible social and agricultural consequences, while explaining what the data cannot establish.

## Data and methods

The climate analyses use the [NOAA PDSI dataset](https://psl.noaa.gov/data/gridded/data.pdsi.html) and the [NOAA Gejkar Cave paleoclimate record](https://www.ncei.noaa.gov/access/paleo-search/study/40686). More details about the other datasets and cleaning methods are documented in my [Week 11 update](/week11.html).

I used AI assistance to help write, troubleshoot, and refine Python code and visualization methods, and reviewed the outputs against my data and research questions.
