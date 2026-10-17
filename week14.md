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

The main analysis is now complete. I have compared the 2006–2010 drought with earlier periods using Gejkar Cave oxygen-isotope measurements and regional PDSI, examined temperature and potential evapotranspiration (PET) during the earlier severe drought around 1958–1963, and investigated changes in Syrian crop yields, irrigation-equipped area, and population patterns. I have also brought these findings together in a [Final Analysis](/final-analysis.html), organized around my research questions rather than around individual datasets.

One important finding is that **the historical ranking depends on the measure used**. The modern interval has the highest mean δ¹⁸O among qualifying Gejkar five-year windows, but an earlier interval was slightly drier in the regional PDSI record. The modern drought also occurred under substantially warmer conditions. Reconciling these findings has made me more attentive to differences in geographic coverage, time resolution, and uncertainty.

The remaining work is mostly to polish the presentation: check that links and figures display correctly, proofread the final narrative, strengthen sources for the historical and human context, and prepare to present the results to the class.

## 2. New technique: interactive visualization with Plotly

For my new technique, I implemented an **interactive Plotly visualization** of the Gejkar Cave isotope record. Instead of a static scatterplot, readers can hover over five-year windows to inspect the dates, number of samples, mean δ¹⁸O, and observed minimum and maximum. The modern interval is highlighted, and shaded regions indicate where historical sampling is missing or sparse.

I learned this by experimenting with the Python plotting code and using AI-assisted explanations and debugging when I encountered unfamiliar options or errors. I checked the resulting graph against the calculated five-year summaries, including the sample counts and the meaning of its vertical bars: these show the observed range, **not confidence intervals**. I also learned how to export the interactive figure as HTML and embed it within my Markdown-based GitHub Pages website.

The result appears in my [Week 12 update](/week12.html). Interactivity is especially useful here because readers can inspect individual five-year windows and recognize that the historical record is not sampled evenly, rather than taking the apparent ranking at face value.

## 3. Communication strategy

I plan to tell the story in three stages: **how severe the drought was historically**, **what made its climatic conditions different**, and **what the agricultural, irrigation, and population records reveal about the drought period**. 

I will select a few visuals that directly advance this narrative: the interactive Gejkar graph, the five-year PDSI plot, the seasonal temperature/PET comparison, and the normalized crop-yield plot. The more detailed figures and methods will remain available in Week 12. To compensate for the class presentation, I plan to condense my findings from both [Week 12](/week12.html) and [Final Analysis webpage](/final-analysis.html) into a short slide presentation. 
