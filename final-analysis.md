---
layout: default
title: Final Analysis – Syria's 2006–2010 Drought
permalink: /final-analysis.html
---

[Home](/) | [Week 9](/week9.html) | [Week 11](/week11.html) | [Week 12](/week12.html) | [Final Analysis](/final-analysis.html)

---

# Was Syria's 2006–2010 Drought Unprecedented?

### A historical and modern perspective

**CS-215 Data Science Final Project - Final Analysis**

## The central finding

Was the drought that affected Syria between 2006 and 2010 unlike anything the region had experienced before? My analysis suggests that there is no single answer without first defining what *unprecedented* means: 

unprecedented in drought severity?
unprecedented in the climate conditions accompanying it?  
unprecedented over the past century, or over tens of thousands of years?

The regional Palmer Drought Severity Index (PDSI) places 2006–2010 among the driest five-year periods in the instrumental record, but an earlier episode around 1958–1963 was slightly drier by that measure. At Gejkar Cave in northern Iraq, the modern interval has the highest average oxygen-isotope value among the five-year windows with enough samples for comparison, although gaps and dating uncertainties prevent that result from establishing a drought record across the entire past 2,400 years. Meanwhile, temperature data show that the 2006–2010 drought took place under substantially warmer conditions than the earlier severe drought period.

The broader picture is therefore more interesting than a simple yes or no. The drought was exceptionally severe, but its historical ranking depends on the evidence examined. The agricultural, irrigation, and population records also show why climate severity alone cannot explain what happened in Syria during those years.

## 1. What does the historical climate evidence tell us?

The longest perspective in this project comes from speleothems—mineral deposits formed in caves that preserve chemical evidence of past environmental conditions. At Gejkar Cave, higher oxygen-isotope values (δ¹⁸O) are generally associated with drier conditions, although temperature, moisture sources, and cave processes also influence the signal.

The **2006–2010 Gejkar window averaged −3.137‰**, higher than all **93 qualifying historical five-year windows** in my main comparison. That ranking held when I changed the minimum number of measurements required in each window from three to two or four. Within the intervals that can be compared using this method, the modern value stands out.

But the record is not continuous. Gejkar has no measurements between approximately 351 and 933 CE, and much of the period from 933 to 1896 CE is too sparsely sampled for reliable five-year comparisons. The cave is also in Iraq, not Syria, and its isotope measurements cannot be translated directly into a regional drought index. I examined Soreq and Peqiin caves for longer-term context, but neither permits a five-year comparison with 2006–2010. **The highest observed five-year isotope mean is not proof of the driest five-year period across the full historical record.**

<iframe
  src="/assets/gejkar_5yr.html"
  width="100%"
  height="560"
  style="border:none;"
  title="Interactive Gejkar Cave five-year isotope comparison">
</iframe>

*Figure 1. Five-year Gejkar Cave δ¹⁸O means. The bars show the range of measurements in each qualifying window, not statistical confidence intervals. The shaded intervals indicate missing or sparse sampling.*

The instrumental PDSI record offers a different comparison. Instead of irregularly spaced cave measurements, it provides monthly estimates of regional dryness. I compared the 2006–2010 average against overlapping 60-month periods ending before 2006.

The modern drought averaged **−1.416 PDSI**. Of **1,501 earlier rolling five-year windows**, only **eight** were as dry or drier. All eight overlap within a single earlier drought episode, rather than representing eight separate events. The driest earlier window, **April 1958–March 1963**, averaged approximately **−1.589 PDSI**. By this measure, 2006–2010 was exceptional, but **not the driest five-year period**.

![Rolling five-year PDSI for the Fertile Crescent](/assets/pdsi_5yr.png)

*Figure 2. Rolling five-year mean PDSI in the Fertile Crescent. Lower values represent drier conditions; the earlier 1958–1963 episode falls below the 2006–2010 mean.*

These findings are not necessarily contradictory. Gejkar reflects conditions at one cave and an unevenly sampled proxy record, while PDSI represents a broader region over a shorter, monthly instrumental record. The five-year comparisons also use different windowing methods. Neither record can establish how every part of Syria experienced a particular drought, and neither supports a definitive claim that 2006–2010 was unprecedented throughout the Holocene.

## 2. If an earlier drought was drier, what was different about 2006–2010?

The earlier PDSI minimum raises an important question: did two similarly severe droughts occur under the same climatic conditions? To investigate, I compared regional temperature and potential evapotranspiration (PET) during April 1958–March 1963 and January 2006–December 2010, using the same 60-month duration.

The modern period averaged **21.21°C**, compared with **20.32°C** during the earlier drought—a difference of approximately **0.90°C**. It also had **35 months** above the corresponding calendar month's 1961–1990 90th-percentile temperature threshold, compared with **12 months** in 1958–1963. The warmer conditions were not confined to summer: the modern drought had higher average temperature anomalies in ten of the twelve calendar months.

Estimated PET was higher too, though by a smaller proportion: approximately **1,826 mm/year** during 2006–2010 versus **1,795 mm/year** during 1958–1963, a difference of about **31 mm/year (1.7%)**. Of the 1,201 overlapping five-year windows ending before 2006, none was as warm as 2006–2010, while one had slightly higher PET. These are rankings against *earlier* windows, not against the full record through 2024.

![Seasonal temperature and PET anomalies in the two drought periods](/assets/cru_seasonal_anomalies.png)

*Figure 3. Average temperature and PET anomalies by calendar month during the two five-year drought episodes, measured against the 1961–1990 reference period.*

This comparison matters because similar drought-index values can occur in different thermal environments. **The modern drought was not uniquely severe by PDSI, but it coincided with much more persistent warmth and somewhat higher estimated evaporative demand.** PET describes the atmosphere's potential demand for water; it does not measure water actually lost from fields or soils. Temperature also contributes to PET and PDSI calculations, so the indicators are not fully independent. The analysis describes these differences but does not determine how much warming caused or intensified the drought.

## 3. What do the agricultural and irrigation records add?

A drought index cannot show by itself how farms and livelihoods were affected. National FAOSTAT data reveal substantial changes during 2006–2010, but not a uniform decline across crops or years. Compared with the 2001–2005 average, mean yields fell **16.5% for wheat**, **31.9% for lentils**, and **14.8% for seed cotton**. Barley's average yield, unexpectedly, was **1.3% higher** across the drought period—even though its yield in 2008 was **66.8% below** the pre-drought baseline.

That contrast illustrates why annual extremes and multi-year averages need to be read together. In 2008, wheat and lentils also reached their lowest yields of the drought interval. Seed cotton followed a different pattern: its lowest drought-period yield came in 2010. National figures cannot tell us whether these differences reflect rainfall, irrigation, crop management, or other economic and environmental conditions, but they show that crops did not follow a single trajectory.

![Syrian crop yields relative to their 2001–2005 averages](/assets/fao_normalized_yields.png)

*Figure 4. Annual yields of four Syrian crops expressed relative to each crop's 2001–2005 average (100). A five-year average can conceal sharp losses in individual years.*

Yield per hectare is also different from total production. For seed cotton, average yield fell **14.8%**, but total production fell **31.1%**. Calculating harvested area from production divided by yield suggests that the area harvested for cotton also decreased, by about **18.8%** between the two five-year periods. These figures point to changes in both productivity and harvested area, without identifying what caused them.

AQUASTAT adds a separate water-infrastructure perspective. Between **2004 and 2009**, Syria's recorded area equipped for groundwater irrigation fell from **864.7 to 656.2 thousand hectares (−24.1%)**, while total area equipped for irrigation fell **13.9%**. Both series partially recovered in 2010. However, land *equipped* for irrigation is not necessarily land actually irrigated, and the total-area series includes estimated observations. These figures do not measure groundwater extraction, water delivered to farms, or the direct effect of drought on irrigation systems.

Taken together, the agricultural and irrigation records suggest that changing crop output, harvested area, and irrigation infrastructure were important parts of the period's agricultural context. They do not establish a causal chain from regional drought severity to specific national crop losses. That would require more geographically detailed evidence, including information on rainfall, irrigation access, farming practices, and policy.

## 4. Does population growth demonstrate drought-related migration?

The UN estimates show another striking change: Syria's population living in **cities and towns** grew from approximately **14.47 million in 2005 to 18.10 million in 2010**, an increase of **25.1%**. Average annual logarithmic growth in this category rose from **3.02% in 2001–2005** to **4.48% in 2006–2010**. The strongest annual growth rates occurred in **2006 and 2007**, before the especially poor 2008 harvests recorded for several crops.

That timing complicates a straightforward story in which the worst national harvests first occurred and were then followed by a measurable movement into cities. It does not rule out drought-related displacement: livelihoods can come under pressure before a national yield series reaches its lowest point. But the UN figures do not track people leaving rural communities, and they cannot distinguish internal migration from births, international migration, or changes in how settlements are classified. The *cities and towns* category is also broader than some conventional definitions of urban population.

The safest conclusion is that **rapid population growth in cities and towns coincided with a period of agricultural and water stress**, against a background of longer-term urbanization and other demographic pressures. It would be misleading to attribute the entire increase to drought. Evidence from household surveys, migration records, and historical accounts would be needed to identify how many people moved because of drought-related losses and when those movements occurred.

## 5. What can we conclude?

The question in this project's title turns out to have several answers. In the regional PDSI record, **2006–2010 was exceptionally dry but not unprecedented**: a five-year interval around 1958–1963 was slightly drier. At Gejkar Cave, **2006–2010 had the highest mean δ¹⁸O among the historical windows that met the sampling requirement**, but gaps and age uncertainty prevent a claim about every five-year period in the cave's history, much less the whole Holocene. The modern drought also occurred in a **markedly warmer climate** than the earlier severe PDSI episode, with somewhat higher estimated PET.

The human-context datasets raise a different question from whether the drought broke a climate record. Syrian crop yields and production changed unevenly, irrigation-equipped area contracted, and the estimated population in cities and towns grew rapidly. Those patterns occurred during overlapping years, but their coexistence is not evidence that one caused the others. Climate conditions interacted with agricultural systems and demographic trends that cannot be reconstructed from national aggregates alone.

**My main conclusion is therefore not that Syria experienced an unprecedented drought in every historical sense. It is that an exceptionally dry period occurred under unusually warm conditions, while agriculture, irrigation infrastructure, and settlement patterns were also changing.** Understanding the consequences requires examining those conditions together without treating correlations as causal proof.

The most useful next steps would be to test the climate comparison with finer-scale data for Syria itself, assess Gejkar's sensitivity to different five-year window placements and age uncertainty, and investigate crop-specific irrigation and documented migration. Those analyses could clarify what was unusual about the drought—and what made communities vulnerable to its effects.

---

*For the calculations, data preparation, figures, and dataset-specific limitations behind this synthesis, see [Week 12: Exploratory Analysis and Interactive Visualization](/week12.html). Earlier stages of the project are documented in [Week 11](/week11.html) and [Week 9](/week9.html).*
