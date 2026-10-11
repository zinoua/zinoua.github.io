---
layout: default
title: Project Update – Week 12
permalink: /week12/
---

[Home](/) |

---

# Project Update – Week 12

**Is Syria's 2006–2010 Drought Unprecedented? A Historical and Modern Perspective**

## 1. From data preparation to exploratory analysis

After  obtaining and cleaning my datasets, I've started focusing more on exploratory analysis and visualizing what the data reveal.

One of the main challenges is comparing a five-year drought with a paleoclimate record that spans roughly 2,400 years but has uneven sampling. I developed five-year windows for the Gejkar Cave δ¹⁸O record and am now using those results to investigate how unusual the 2006–2010 period appears in the historical record.

This week, I also began working with Plotly to make the visualizations interactive, rather than relying only on static Matplotlib figures.

## 2. Interactive visualization: Gejkar Cave

The figure below shows the mean δ¹⁸O of qualifying five-year windows from Gejkar Cave in northern Iraq. Higher δ¹⁸O values are generally associated with drier conditions at this site.

Each point represents a five-year window with at least three measurements. The vertical bars show the minimum and maximum observed δ¹⁸O values within each window, rather than statistical uncertainty.

The 2006–2010 interval is highlighted in red. Hovering over the points reveals the years covered, mean δ¹⁸O, number of samples, and minimum and maximum measurements.

<iframe
  src="/assets/gejkar_5yr.html"
  width="100%"
  height="600"
  style="border:none;"
  title="Interactive Gejkar visualization">
</iframe>

## 3. What the Gejkar analysis reveals

The 2006–2010 window has a mean δ¹⁸O of −3.137‰ VPDB, calculated from five measurements. It has the highest mean among the 94 qualifying five-year windows in the analysis. The next highest is 2001–2005, with a mean of approximately −3.66‰.

However, the plot also reveals an important limitation. The record contains no measurements between approximately 351 and 933 CE, and sampling between 933 and 1896 is generally too sparse for five-year windows to meet the three-sample requirement.

I also tested whether changing the minimum number of samples would affect the result:

| Minimum samples | Historical windows retained | Windows with equal or higher mean δ¹⁸O |
|---|---:|---:|
| 2 | 313 | 0 |
| 3 | 93 | 0 |
| 4 | 46 | 0 |

The modern interval remains the highest under all three requirements. This suggests that the finding is robust to the particular sample thresholds I tested, although the amount of historical coverage changes substantially.

This still doesn't establish that the Syrian drought was unprecedented. Gejkar is a regional paleoclimate proxy, not a direct rainfall record for Syria, and uneven sampling and age-model uncertainty limit comparisons of short events across the historical record.

## 4. Exploring the modern drought record

My next comparison focuses on the NOAA Palmer Drought Severity Index (PDSI), which provides monthly instrumental-era drought estimates for the Fertile Crescent.

My preliminary analysis identified May 2008 as the driest individual month in the regional series, with a PDSI value of approximately −4.96.

However, the main question is not whether one month was exceptionally dry. I want to determine how unusual the average conditions during 2006–2010 were compared with other five-year periods.

I plan to calculate historical five-year PDSI averages and visualize the result. This will provide an instrumental comparison to place alongside the longer Gejkar record, although the two measure different aspects of climate.

## 5. Challenges and next steps

The main challenge continues to be determining what comparisons the available data can support. The cave records have uneven sampling and uncertain historical dates, while the regional PDSI record has a much shorter timeline and relatively coarse spatial resolution.

For the final project, I plan to focus on three questions:

1. How unusual was the 2006–2010 drought compared with earlier five-year periods in the modern PDSI record?
2. How does the Gejkar δ¹⁸O signal during 2006–2010 compare with qualifying historical intervals?
3. How did agricultural yields change during the drought, and how do those changes relate to regional drought conditions?

I will also use temperature, PET, water-use, and population data where they help provide context, while recognizing that associations between these variables do not necessarily establish causation.

The goal is to develop the exploratory findings into a more complete analysis, with visualizations and a narrative that clearly explains both the results and their limitations.
