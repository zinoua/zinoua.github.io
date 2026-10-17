---
layout: default
title: Project Update – Week 14
permalink: /week14.html
---

[Home](/) | [Week 9](/week9.html) | [Week 11](/week11.html) | [Week 12](/week12.html) | [Week 14](/week14.html) | [Final Analysis](/final-analysis.html)

---

# Project Update – Week 14

**Is Syria's 2006–2010 Drought Unprecedented? A Historical and Modern Perspective**

## 1. Project progress

The main analysis is now complete. I have compared the 2006–2010 drought with earlier periods using Gejkar Cave oxygen-isotope measurements and regional PDSI, examined temperature and potential evapotranspiration (PET) during the earlier severe drought around 1958–1963, and investigated changes in Syrian crop yields, irrigation-equipped area, and population patterns. I have also brought these findings together in a [Final Analysis](/final-analysis.html), organised around my research questions rather than around individual datasets.

One important finding is that **the historical ranking depends on the measure used**. The 2006-2010 drought period has the highest mean δ¹⁸O among qualifying Gejkar five-year windows, but the 1958–1963 drought was slightly drier in the regional PDSI record. However, the 2006-2010 drought also occurred under substantially warmer conditions. These findings have made me more attentive to differences in geographic coverage, time resolution, and uncertainty.

The remaining work is mostly to polish the webpage: check that links and figures display correctly, proofread the final narrative

## 2. New technique: Speleothem Record Binning & Interactive Visualisation with Plotly

The main new technique I explored was aggregating climate records into time windows of comparable duration. My original cave plots used 100-year bins, and that introduced a major problem, as they were too coarse to evaluate a drought lasting only five years. The 2006–2010 measurements were essentially combined and washed away with earlier decades. I therefore learned how to group the irregular Gejkar isotope measurements into non-overlapping five-year bins, calculating the mean, minimum, maximum, and number of samples in each. I required at least three measurements per 5-year window for the analysis and tested how the result changed with two or four samples. 

For the PDSI record, I used a slightly different approach because the data are recorded monthly rather than at irregular intervals. I calculated the average PDSI over 60 consecutive months (five years), then moved that window forward by one month and repeated the calculation across the historical record. Unlike the fixed five-year bins used for Gejkar, these overlapping windows allowed me to identify severe drought periods regardless of when they began or ended. I could then compare the average PDSI for 2006–2010 with earlier five-year periods to determine how unusual its overall severity was, rather than judging the drought based on its single driest month.

I learned these approaches by working through the Python code, using AI tools to clarify unfamiliar concepts and help debug the binning and plotting steps, and checking the calculations and sample counts against the source data. As a further extension, I used Plotly to turn the Gejkar five-year summaries into an interactive graph. Readers can hover to see each window's dates, isotope values, and sample count, while shaded areas make gaps in the cave record visible. The vertical bars show the observed minimum–maximum range, not confidence intervals. The finished visualisation and comparisons appear in my Week 12 update.

## 3. Communication strategy

I plan to tell the story in three stages: **how severe the drought was historically**, **what made its climatic conditions different**, and **what the agricultural, irrigation, and population records reveal about the drought period**. 

I will select a few visuals that directly advance this narrative: the interactive Gejkar graph, the five-year PDSI plot, the seasonal temperature/PET comparison, and the normalized crop-yield plot. The more detailed figures and methods will remain available in Week 12. To compensate for the class presentation, I plan to condense my findings from both [Week 12 Update](/week12.html) and [Final Analysis webpage](/final-analysis.html) into a short slide presentation. 
