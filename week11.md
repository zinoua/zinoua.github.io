---
layout: default
title: Project Update – Week 11
permalink: /week11/
---

[Home](/) | [Week 9](/week9/) | [Week 11](/week11/) | [Week 12](/week12/)

---

# Project Update – Week 11


# Project Update – Week 11

**Is Syria's 2006-2010 Drought Unprecedented? A Historical and Modern Perspective.**

## 1. Data sources and why I chose them

My question is whether the 2006-2010 drought in Syria was unusual compared with natural climate variability, and how it coincided with changes in agriculture, water use, and population patterns. I combined modern climate data, cave records of past moisture conditions and Syria-specific agriculture, water, and population data.

**Modern climate**

- [NOAA PDSI](https://psl.noaa.gov/data/gridded/data.pdsi.html) (self-calibrated Palmer Drought Severity Index): monthly, 2.5° grid, 1850-2014. I chose it because it measures relative dryness using temperature and precipitation. Real data for my region only start in 1876, and it's a computed index, not a direct measurement.
- [CRU TS 4.09](https://catalogue.ceda.ac.uk/uuid/9cf07e92afaa405da4f40b6733f362d3/) temperature (tmp) and potential evapotranspiration (pet): monthly, 0.5° grid, land only, from 1901-2024. I chose it to check regional warming and how strongly the air pulls moisture from the ground.

**Past climate (cave δ¹⁸O records from NOAA Palaeoclimatology).** At Gejkar cave, higher δ¹⁸O is generally associated with drier conditions

- [Gejkar Cave](https://www.ncei.noaa.gov/access/paleo-search/study/40686): 841 measurements from 415 BCE to 2012 CE. This is my main record because it runs through 2006-2010.
- [Soreq Cave](https://www.ncei.noaa.gov/access/paleo-search/study/5423): goes back about 184,000 years and ends in 1950 CE. I use it as context only, because its samples are too far apart (median about 60 years) to test a five-year event.
- [Peqiin Cave](https://www.ncei.noaa.gov/access/paleo-search/study/5423): its youngest sample is 14,000 years old, so it has no Holocene data. It's Pleistocene context only.

**Syria-specific data**

- [FAOSTAT](https://www.fao.org/faostat/en/#data/QCL) crop yield and production for wheat, barley, lentils, and seed cotton, 1961–2014. Wheat, barley, and lentils are mostly rainfed and cotton is irrigated, so I can compare how each type held up.
- [AQUASTAT](https://data.apps.fao.org/aquastat/?lang=en): ten irrigation and water-use variables, mostly 1993–2014.
- [UN Population Data Portal](https://population.un.org/dataportal/): urban share, urban growth rate, and urban population for Syria, 1950–2014.

## 2. How I got the data

Everything is in my [project data folder](https://drive.google.com/drive/folders/1SlS2CBP3NEIGqpVvbBkQ1oh_Lz2Y7Hsj). PDSI, the cave files, FAOSTAT, AQUASTAT, and the UN data came straight from their portals. CRU TS came from CEDA, which needs a free login. My first downloads saved a login page instead of the data, so I had to redo them. I drew the Fertile Crescent polygon myself in Google Earth.

## 3. What each dataset can and can't tell me

- **PDSI:** can show how unusual 2006-2010 was over about 140 years. Coverage is thinner before 1897, when only 1-14 of the region's 19 grid cells report, so the early record is noisier. It can't isolate Syria or any one cave site, because the grid is coarse and my polygon is narrow and irregular. I used “all_touched=True”, which keeps any cell the polygon touches, and I haven't tested how much that choice matters.
- **CRU TS:** can show regional warming. PDSI is already built from temperature, so a PDSI–temperature correlation isn't independent evidence.
- **Gejkar:** can compare 2006-2010 with about 2,400 years, with a measurement every 2–3 years for most of the record and about one a year since 1885. Can't speak for Syria (the cave is in Iraq), and ages between dated points are interpolated.
- **Soreq and Peqiin:** give long context but are too sparse for a five-year event. Peqiin can't speak to the Holocene at all. I don't compare raw δ¹⁸O values across caves, because each cave has its own baseline.
- **FAOSTAT:** all values are official, but they're national, so I can't separate the drought from policy or conflict.
- **AQUASTAT:** supports the buildup before the drought. In its legend, E means estimate and I means imputed (carry-forward or interpolation). For 2006-2010 only groundwater-irrigated area isn't flagged E or I.
- **UN data:** shows urban population change, which includes births, deaths, and war displacement, so it can't show that the drought caused migration.

## 4. Cleaning and wrangling

- Clipped PDSI and CRU TS to my polygon, took regional monthly means, and trimmed PDSI to 1876 onward. Neither series has missing months.
- Cave files: separated the metadata from the data tables. Soreq and Peqiin weren't in age order, so I sorted them and dropped rows with no age (21 for Soreq, 3 for Peqiin). Ages in years before present count back from 1950, so I converted them to calendar years. Soreq and Peqiin ages are in thousands of years, so I multiplied by 1000 first.
- Rows with an age but no δ18O (14 in Soreq, 18 in Peqiin) are left out of the binned averages.
- Resampling the caves: I started with 100-year bins for Gejkar and Soreq and 500-year bins for Peqiin (at 100 years, over 90% of Peqiin's bins held a single sample). Each bin keeps its mean, min, max, and sample count, and gaps are flagged instead of filled. After realizing 100-year bins blend 2006-2010 with 1985-2005, I built five-year windows for Gejkar that need at least three samples.
- AQUASTAT: dropped bookkeeping columns, kept the Symbol column, and flagged repeated values. My repeated-value flag caught 121 of the 252 values marked E or I.
- UN, FAOSTAT, CRU: dropped unnecessary columns and joined temperature and PET into one table.

## 5. What I've learned so far

For Gejkar, I kept only five-year windows with at least three measurements, which left 94 windows, including 2006-2010. That window has a mean δ18O of −3.14‰ (VPDB) from five samples. It is higher (drier) than all 93 other windows. The next driest is 2001-2005 at −3.66‰.

This doesn't prove the drought was unprecedented. The qualifying windows only cover two stretches, 415 BCE to about 350 CE and about 1896 to 2010 CE. From about 351 to 933 CE (about 580 years), the record has no samples, and from about 933 to 1896, sampling is roughly one sample every three years, so a five-year window rarely yields three samples. Requiring at least 2, 3, or 4 samples per window leaves 313, 93, or 46 qualifying historical windows, respectively. The 2006–2010 interval still has the highest mean δ¹⁸O in all three comparisons, suggesting that its ranking is robust to the minimum-sample thresholds I tested, even though historical coverage changes substantially. With the 2-sample rule, 144 of those windows start between 933 and 1896 CE, so even in the stretch the 3-sample version misses, no window is as dry as 2006-2010. Two-sample means are noisier, so I treat the 3-sample version as my main result. I use the combined cave plot for regional context, and I don't compare raw δ18O across caves because each cave has its own baseline. The same number at two different caves doesn't mean the same amount of dryness, as δ18O is shaped by more than rainfall. It depends on where the water vapour came from, how far it travelled, the local temperature, the cave's elevation and position, and how water moves through the rock above the cave before it drips onto the stalagmite. Every cave has its own mix of those factors.

**The other datasets:**

- **PDSI:** May 2008 was the driest month in my regional PDSI series (−4.96). The average PDSI during 2006-2010 was approximately −1.42, lower than 88% of individual monthly observations in the record. However, this comparison does not establish how unusual the five-year drought was relative to other five-year periods. I will investigate that during the next stage of analysis.
- **FAOSTAT**: in 2008, wheat, barley, and lentil yields were about 48%, 80%, and 79% below 2006. Cotton rose 24% in 2008 and was 14% below 2006 by 2010. So the rainfed crops took the big hit in 2008 while irrigated cotton held up better.
- **UN population:** Syria's annual urban population growth rate peaked at 7.32% in 2007, the highest of the 65 years in the file, up from 3.09% in 2004.
- **AQUASTAT:** groundwater-irrigated area dropped about 24% between 2004 and 2009 (864,700 to 656,200 ha). It is the only variable in the drought window that isn't flagged as estimated or imputed.
- **CRU TS:** Temperature and potential evapotranspiration (PET) have a strong positive correlation in the monthly regional data (r = 0.95). This makes sense because temperature is one of the variables used to calculate PET, and both follow seasonal cycles. However, PET also incorporates other atmospheric conditions, including vapour pressure and cloud cover, so the two variables are not interchangeable. I would need to remove seasonal variation or examine longer-term trends before determining how much additional information PET provides.

**6. Challenges and next steps**

- **"Unprecedented" depends on the comparison period.** Gejkar covers about 2,400 years, not the whole Holocene, and the recent rise sits on top of a longer drying trend. "The most extreme point on a long trend" is a different claim from "unprecedented."
- **Sampling is uneven.** Peqiin has gaps of up to 14,500 years, and five-year Gejkar windows with at least three samples are missing from about 350 to 1896 CE.
- **Data quality.** AQUASTAT is mostly estimated or imputed in the drought window, and urban growth turns sharply negative after 2011 (−8.5% in 2013), when the war becomes a bigger factor than climate.

## Sources and help

I used AI tools to help me understand speleothem age conventions and to write and debug the cleaning, binning, and plotting code. At some point, I also realised that 100-year bins were too coarse for a five-year event, and I built a new window analysis with help using AI tools.
