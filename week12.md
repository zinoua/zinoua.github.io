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

*Figure 1. Interactive Gejkar Cave δ¹⁸O comparison using non-overlapping five-year windows with at least three samples. Vertical ranges show the observed minimum and maximum, not confidence intervals.*

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

*Table 1. Sensitivity of the Gejkar comparison to the minimum number of measurements required in each five-year window. Historical windows exclude 2006–2010.*

The modern interval remains the highest under all three thresholds. This makes the result less dependent on my choice of minimum sample count, but the number of historical windows available for comparison changes considerably. These five-year windows are also non-overlapping, so their placement may influence which historical events are captured.

**This does not establish that the 2006–2010 drought was unprecedented across the entire historical record.** Gejkar is a cave in northern Iraq rather than a direct rainfall record for Syria, and gaps, irregular sampling, and age uncertainty limit comparisons of short events.

## 4. PDSI: comparing five-year drought severity

My earlier PDSI plot showed monthly drought conditions across the Fertile Crescent and identified **May 2008** as the driest individual month in my regional series, at approximately **−4.96**. But one extreme month cannot tell us whether an entire five-year drought was unprecedented.

To compare periods of equal duration, I calculated a **60-month rolling mean** of regional PDSI. Each point represents the average of that month and the preceding 59 months, giving a full five years of observations. Lower PDSI values indicate drier conditions. I compared the January 2006–December 2010 mean with rolling windows ending before 2006.

![Five-year rolling average PDSI for the Fertile Crescent, highlighting the 1958–1963 and 2006–2010 drought intervals](/assets/pdsi_5yr.png)

*Figure 2. Regional PDSI averaged over rolling 60-month windows. Each point is plotted at the end of its five-year window. The highlighted intervals identify the modern drought and the driest earlier comparison period.*

The **2006–2010 mean PDSI was −1.416**. Of the **1,501 earlier rolling five-year windows**, approximately **99.5% had higher (wetter) mean PDSI**. Only eight earlier windows were as dry or drier.

Those eight windows were not eight separate drought events. They overlap heavily and all belong to an earlier dry episode around **1958–1963**. The lowest earlier five-year mean was approximately **−1.589**, for **April 1958–March 1963**.

This means that **2006–2010 was exceptionally dry in the instrumental regional record, but not the driest five-year interval** under this method. Because the rolling windows overlap, their count should not be treated as a count of independent drought events.

There are also spatial limitations. PDSI is available on a coarse 2.5° grid, and I included all grid cells touched by my Fertile Crescent polygon. The number of available regional cells also changes during the early part of the record. I still need to test how sensitive the historical comparison is to these choices before drawing a final conclusion.

## 5. Comparing the two climate records

The Gejkar and PDSI results offer different perspectives. The 2006–2010 isotope mean is the highest among qualifying Gejkar windows, while the regional PDSI record includes an earlier five-year interval around 1958–1963 that was drier by its index.

This is not necessarily a contradiction. The cave record reflects local environmental and hydrological processes, whereas regional PDSI estimates drought conditions across a much larger area. Their time coverage, sampling frequency, and uncertainties are also different. I cannot directly convert Gejkar δ¹⁸O values into PDSI values or assume that they describe identical drought conditions.

Together, they suggest that the answer to whether the drought was “unprecedented” depends on **which indicator, region, and timescale** I use.

## 6. Agricultural responses to the drought: FAOSTAT analysis

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

*Table 2. Changes are relative to the 2001–2005 average. Production refers to total national output rather than yield per hectare.*

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

## 7. Temperature and potential evapotranspiration: comparing two severe droughts

My PDSI analysis found that the 2006–2010 drought was exceptionally severe, but not unprecedented within the regional instrumental record. An earlier episode around 1958–1963 recorded a slightly lower five-year mean PDSI, indicating more severe drought conditions according to that measure.

However, similar PDSI values do not necessarily mean two droughts occurred under identical climatic conditions. I therefore used CRU TS regional temperature and potential evapotranspiration (PET) records to examine whether the modern drought occurred under different thermal and atmospheric evaporative-demand conditions.

### Long-term temperature and PET trends

![Regional temperature and PET in the Fertile Crescent, 1901–2024](/assets/cru_long_term.png)

*Figure 5. Annual mean regional temperature (°C) and annual total potential evapotranspiration (mm/year) from 1901–2024. Dashed lines represent linear trends, while shaded intervals identify the two drought periods. The annual observations summarize calendar years, whereas the drought comparisons use exact 60-month intervals.*

The temperature record shows a long-term warming trend of approximately **0.14°C per decade** between 1901 and 2024. Annual PET also increased, at approximately **5.61 mm/year per decade**. Both records exhibit considerable year-to-year variability, and the fitted lines describe overall trends rather than changes occurring uniformly throughout the period.

The modern drought occurred within the warmer portion of the instrumental record. However, the figure also shows that several years after 2010 experienced similarly high or higher annual temperatures. Therefore, the historical unusualness of 2006–2010 needs to be assessed using comparable five-year periods rather than individual years.

### Comparing the 1958–1963 and 2006–2010 droughts

I compared the two droughts using equal 60-month windows: April 1958–March 1963 and January 2006–December 2010. I also calculated anomalies against a common 1961–1990 climatological reference period.

| Measurement | 1958–1963 | 2006–2010 |
|---|---:|---:|
| Mean temperature | 20.32°C | 21.21°C |
| Temperature anomaly | +0.37°C | +1.26°C |
| Annual-equivalent PET | 1,795.02 mm | 1,826.01 mm |
| PET anomaly | +1.80% | +3.56% |
| Exceptionally warm months | 12 of 60 | 35 of 60 |
| Exceptionally high-PET months | 13 of 60 | 21 of 60 |

*Table 3. Temperature and PET anomalies are relative to 1961–1990. Exceptional months exceed the 90th percentile for their respective calendar month during that reference period.*

The modern drought was **0.90°C warmer** than the earlier episode. Its annual-equivalent PET was also higher by approximately **31 mm/year**, representing a difference of **1.7%**.

The temperature contrast is more pronounced than the PET contrast. This is important because higher temperatures do not necessarily produce an equivalent proportional increase in estimated PET, which depends on additional meteorological conditions.

The frequency of exceptional months provides another perspective. During 2006–2010, 35 of 60 months exceeded the historical 90th-percentile temperature threshold, compared with 12 months during the earlier drought. Exceptionally high-PET months were also more frequent, increasing from 13 to 21.

These results suggest that unusually warm conditions were more persistent during the modern drought, although the choice of climatological reference influences the exceptional-month counts.

### How unusual were these conditions historically?

I compared the 2006–2010 temperature and PET averages with **1,201 earlier overlapping 60-month windows**, covering five-year periods ending before January 2006.

None of the earlier windows had an average temperature as high as 2006–2010. The warmest earlier window, March 1998–February 2003, averaged 21.11°C, compared with 21.21°C during the modern drought.

PET was also near its historical maximum. Only one earlier window, February 1998–January 2003, had a higher annual-equivalent PET: 1,826.45 mm/year compared with 1,826.01 mm/year during 2006–2010.

This places the modern drought among the warmest and highest-PET five-year periods recorded before 2006. However, the rolling windows overlap and cannot be interpreted as independent climate events. These rankings also exclude later periods, so they do not establish that 2006–2010 was the warmest interval in the complete record through 2024.

### Seasonal differences between the droughts

To investigate whether the differences were concentrated in particular seasons, I calculated monthly temperature and PET anomalies relative to the 1961–1990 average for each calendar month.

![Monthly temperature and PET anomalies during the two droughts](/assets/cru_seasonal_anomalies.png)

*Figure 6. Average monthly temperature and PET anomalies during April 1958–March 1963 and January 2006–December 2010, relative to the corresponding calendar-month averages for 1961–1990. Each bar represents the average of five observations of that calendar month.*

The modern drought had higher temperature anomalies than the earlier drought in **10 of the 12 calendar months**, with January and December being the exceptions. Particularly large differences occurred in March, June, August, September, and October.

This indicates that the warmer conditions during 2006–2010 were not restricted to summer but extended across much of the year.

The PET pattern was less uniform. The modern drought had higher monthly PET anomalies in eight of the twelve calendar months, with especially noticeable differences in March and June. The earlier drought had higher PET anomalies in January, May, October, and December.

This seasonal variation helps explain why the overall temperature difference between the two droughts was more pronounced than the PET difference.

### Connecting climate conditions with agricultural changes

The CRU results add context to the FAOSTAT analysis. Wheat, barley, and lentils all recorded their lowest drought-period yields in 2008, which also stands out as a particularly warm, high-PET year in the regional CRU graphs.

This coincidence is worth investigating, but it does not establish that temperature or PET caused those agricultural declines. Crop yields also depend on precipitation timing, soil moisture, irrigation, agricultural management, and other environmental and economic factors.

Furthermore, the climatic results represent averages across the Fertile Crescent, while FAOSTAT reports national agricultural statistics for Syria. The datasets therefore differ in their spatial coverage.

### Limitations and interpretation

Taken together, the PDSI and CRU analyses demonstrate an important distinction. The earlier 1958–1963 drought was slightly more severe according to regional five-year mean PDSI, but the 2006–2010 drought occurred under distinctly warmer conditions and somewhat higher estimated potential evapotranspiration.

Several limitations remain. The 1961–1990 climatological baseline overlaps with the earlier drought and represents a retrospective reference rather than the climate immediately preceding that event. Historical temperature and PET estimates are also subject to uncertainties associated with observational coverage and gridded-data reconstruction.

Finally, PET represents potential evaporative demand rather than actual evaporation or soil-water loss. Because PET estimates depend partly on temperature, the two variables are not fully independent indicators.

Overall, these findings suggest that the 2006–2010 drought was not unprecedented in every measure of drought severity, but it occurred under climatic conditions that differed substantially from the earlier severe episode. This distinction is central to evaluating the historical unusualness of the modern drought.

## 8. Irrigation and water resources in Syria: AQUASTAT analysis

Having examined the climatic conditions and agricultural changes associated with the 2006–2010 drought, I turned to FAO's AQUASTAT database to investigate Syria's irrigation infrastructure and water-resource context.

The dataset contains ten water-related variables, including agricultural and municipal water withdrawals, renewable water resources, water stress, and land equipped for irrigation. However, my initial inspection revealed important limitations. Many observations were estimated or imputed, and several variables repeated identical values across consecutive years. Agricultural water withdrawal, for example, remained at 14.67 billion m³/year throughout 2004–2010, but every observation was flagged as imputed. These values cannot reliably demonstrate whether agricultural water withdrawals changed during the drought.

I therefore focused on two variables that provided more informative year-to-year comparisons: **area equipped for irrigation by groundwater** and **total area equipped for irrigation**.

### Changes in irrigation-equipped area

![Area equipped for irrigation in Syria, 1993–2014](/assets/aquastat_irrigation.png)

*Figure 7. Changes in groundwater-equipped and total irrigation-equipped area in Syria from 1993–2014, measured in thousand hectares. Circles represent values not flagged as imputed (A/E), including estimates, while X markers identify imputed values (I). The shaded region marks the 2006–2010 drought.*

Both series increased throughout the 1990s and early 2000s, reaching their highest values around 2004. They subsequently declined, with particularly sharp decreases during the drought period, before partially recovering in 2010.

The decline was more pronounced for groundwater-equipped irrigation area than for total equipped irrigation area.

| Measurement | 2004 | 2006 | 2009 | 2010 |
|---|---:|---:|---:|---:|
| Groundwater-equipped area (thousand ha) | 864.7 | 851.1 | 656.2 | 726.8 |
| Total equipped area (thousand ha) | 1,438.7 | 1,401.8 | 1,238.3 | 1,341.0 |

*Table 4. Selected AQUASTAT irrigation-area values before and during the drought.*

Groundwater-equipped irrigation area declined from **864.7 thousand hectares in 2004 to 656.2 thousand hectares in 2009**, a reduction of approximately **24.1%**. Looking specifically at 2006–2009, the decline was approximately **22.9%**. Although the area increased to 726.8 thousand hectares in 2010, it remained substantially below the 2004 level.

Total irrigation-equipped area followed a similar, though less severe, trajectory. It declined from 1,438.7 thousand hectares in 2004 to 1,238.3 thousand hectares in 2009, a decrease of approximately **13.9%**. Between 2006 and 2009, the decline was **11.7%**. By 2010, it had partially recovered to 1,341.0 thousand hectares.

These results indicate that the AQUASTAT series recorded a contraction in irrigation-equipped area during the drought, especially in the area equipped to use groundwater. The different magnitudes of decline raise questions about the vulnerability of groundwater-based irrigation and the factors influencing changes in irrigation infrastructure.

### Connecting irrigation with agricultural productivity

The AQUASTAT findings provide useful context for the FAOSTAT analysis. During the same drought interval, average yields declined for wheat, lentils, and seed cotton, while national production also fell for these crops. FAOSTAT additionally indicated a reduction in implied harvested area of approximately 18.8% for cotton and 10.3% for wheat when comparing 2006–2010 with 2001–2005.

These observations suggest that changes in irrigation infrastructure and agricultural land use are worth investigating together. However, the two datasets measure different things. AQUASTAT reports the area equipped for irrigation, while the FAOSTAT calculations estimate harvested area from crop production and yield. Neither establishes how much irrigation water was actually available to individual farms.

Furthermore, the AQUASTAT figures represent national irrigation infrastructure, whereas the FAOSTAT observations cover specific crops. The available data cannot establish that reductions in irrigation-equipped area directly caused the declines in crop yields or production.

### Limitations and interpretation

The AQUASTAT analysis has several limitations that affect how its results should be interpreted.

First, **area equipped for irrigation does not represent actual water use**. Land may be equipped for irrigation without being irrigated in a particular year. Likewise, changes in equipped area do not directly measure groundwater extraction, falling water tables, or water shortages.

Second, **the reliability of individual observations varies**. Some values are estimated (E), others are imputed (I), and the original dataset also contains values flagged A. The graph distinguishes imputed values from the others, but circles should not automatically be interpreted as independently measured observations. The total irrigation-equipped area series, in particular, contains estimated values during the drought period.

Finally, the timing of the irrigation-area decline coincides with the drought, but this does not establish causation. Changes in infrastructure, water-management policies, economic conditions, and other agricultural factors could also contribute to the observed patterns.

Overall, AQUASTAT provides evidence of a substantial decline in Syria's recorded irrigation-equipped area during the 2006–2010 drought, particularly for groundwater-equipped irrigation. It adds an important water-management dimension to the climate and agricultural analyses, while also demonstrating the limitations of using estimated national statistics to reconstruct annual drought impacts.

## 9. Population growth, urbanization, and rural displacement

Having examined the climatic, agricultural, and irrigation-related dimensions of the drought, I turned to its demographic context. The 2006–2010 drought was not simply an environmental event. For many rural Syrian communities dependent on farming and livestock, declining agricultural productivity and water shortages threatened their livelihoods and encouraged families to seek work and opportunities elsewhere.

To investigate population changes during this period, I used estimates from the UN Population Data Portal covering 1950–2014. The dataset includes the population living in cities and towns, its share of Syria's total population, and annual population growth rates.

### Historical population and urbanization trends

![Syria population in cities and towns, 1950–2014](/assets/un_urban_population.png)

*Figure 8. Estimated population living in Syria's cities and towns (millions) and its percentage of the national population from 1950–2014. The shaded periods distinguish the 2006–2010 drought from the subsequent conflict years. These are UN model-based estimates using the degree-of-urbanization classification.*

The first figure shows a long-term increase in both the number and proportion of people living in cities and towns. This trend began decades before the drought, meaning that urbanization was already underway.

However, the period surrounding the drought shows a noticeable acceleration in population growth.

Between **2005 and 2010**, the estimated population in cities and towns increased from **14.47 million to 18.10 million**, a rise of approximately **25.1%**, or 3.63 million people.

The share of the national population living in cities and towns also increased from **76.89% to 80.49%**, an increase of approximately **3.59 percentage points**.

These changes indicate that the cities-and-towns population grew faster than the country's overall population during this period. However, the figures do not establish how much of that growth resulted from migration rather than natural population increase or changes in settlement classification.

### Did population growth accelerate during the drought?

To examine the timing more closely, I calculated annual logarithmic population growth rates from consecutive UN population estimates.

![Annual population growth in Syria's cities and towns, 1990–2014](/assets/un_population_growth.png)

*Figure 9. Annual population growth in Syria's cities and towns, calculated from consecutive UN population estimates. These rates are not direct measurements of migration. The drought period is highlighted separately from the subsequent conflict years.*

The annual growth data reveal that the increase was not evenly distributed across the drought period.

| Period | Mean annual population growth |
|---|---:|
| 1996–2005 | 3.21% |
| 2001–2005 | 3.02% |
| 2006–2010 | 4.48% |

*Table 5. Mean annual logarithmic growth rates calculated from the UN cities-and-towns population estimates.*

Average annual growth increased by **1.46 percentage points** between the preceding five-year period and the drought interval.

The increase was particularly pronounced in 2006 and 2007, when calculated annual growth reached approximately **5.35% and 7.14%**, respectively. Growth then slowed to 4.44% in 2008, 2.40% in 2009, and 3.05% in 2010.

This suggests that the population-growth acceleration was concentrated in the earlier years of the drought rather than sustained at the same rate throughout 2006–2010.

After 2011, the estimated population in cities and towns began declining, reaching approximately 15.84 million by 2014. These later changes occurred during the Syrian civil war and must be distinguished from the pre-conflict drought period.

The UN population estimates provide demographic context, and there are also direct historical accounts and studies that highlight how drought-related agricultural hardship encouraged migration from Syria's countryside.

### Connecting population changes with agricultural and water stress

The timing of the population changes is particularly interesting when considered alongside the other datasets.

FAOSTAT showed substantial yield declines for wheat and lentils during 2006–2010, with especially severe losses in 2008. AQUASTAT recorded declining irrigation-equipped area over much of the same period, particularly for groundwater-equipped irrigation.

Meanwhile, our UN population analysis identifies unusually rapid growth in cities and towns during 2006–2007.

These findings are consistent with a period of mounting pressure on rural livelihoods and changing settlement patterns. However, the strongest measured population-growth acceleration occurred before the worst agricultural year in our FAOSTAT dataset. This does not rule out drought-related migration: rural households may have faced water shortages, livestock losses, and declining incomes before the most severe national crop-yield declines became visible.

At the same time, Syria's demographic changes were shaped by other factors, including long-standing urbanization, economic conditions, government agricultural policies, natural population growth, and the arrival of refugees from Iraq. It would therefore be misleading to attribute the entire increase in the cities-and-towns population to drought.

### Limitations and interpretation

There are several important limitations to this analysis.

First, the UN data are **model-based population estimates**, not direct annual counts of people moving from rural communities to cities. The standardized *Cities and towns* classification also includes towns and semi-dense settlements and should not automatically be equated with Syria's nationally defined urban population.

Second, the annual growth rates calculated from consecutive population estimates differ from the UN's separately reported growth-rate indicator in several years. I used the rates calculated from population counts to maintain consistency with the plotted population series, but the differences remain an unresolved methodological limitation.

Third, urban population growth is not equivalent to rural-to-urban migration. Population growth can reflect births, deaths, international migration, internal movement, and settlement reclassification. The UN series cannot isolate these contributions.

Overall, the UN data show a marked acceleration in the growth of Syria's cities-and-towns population during the drought period, particularly around 2006–2007. When considered alongside historical accounts and research on rural displacement, these findings provide an important demographic dimension to the drought.

The evidence suggests that the consequences of the drought cannot be understood through climate records alone. Agricultural vulnerability, water-management practices, economic conditions, and the ability of rural communities to adapt all shaped how people experienced and responded to the crisis.
