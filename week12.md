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

## 6. Challenges and next steps

My remaining work is to investigate the wider impacts of the drought and strengthen the sensitivity checks on the climate results. I plan to:

1. Plot Syrian wheat, barley, lentil, and seed-cotton yields over the full FAOSTAT record to see whether the declines around 2008 stand out from earlier fluctuations.
2. Examine regional temperature and potential evapotranspiration trends, taking seasonal variability into account.
3. Test whether different choices of PDSI spatial coverage change the five-year drought ranking.
4. Use AQUASTAT and UN population data as supporting context without treating national trends as proof that drought caused particular changes in irrigation or migration.

For the final project, I want to bring these analyses together into a clear narrative that distinguishes severe climatic conditions from their possible social and agricultural consequences, while explaining what the data cannot establish.

## Data and methods

The climate analyses use the [NOAA PDSI dataset](https://psl.noaa.gov/data/gridded/data.pdsi.html) and the [NOAA Gejkar Cave paleoclimate record](https://www.ncei.noaa.gov/access/paleo-search/study/40686). More details about the other datasets and cleaning methods are documented in my [Week 11 update](/week11.html).

I used AI assistance to help write, troubleshoot, and refine Python code and visualization methods, and reviewed the outputs against my data and research questions.
