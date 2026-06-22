# Research References and Variable Codebook
**Course:** Adolescent Behavioral Data Analytics (2026)  
**Project Scope:** Mental Health Indicators and Physical Activity Behaviors  
**Student ID:** 113370220  

---

## 1. Academic Reference & Data Source

### Institutional Source
* **Data Provider:** Centers for Disease Control and Prevention (CDC), National Center for HIV/AIDS, Viral Hepatitis, STD, and TB Prevention.
* **Dataset Name:** Youth Risk Behavior Survey (YRBS), 2007 National Dataset.
* **Data Link:** [CDC YRBS Questionnaires, Data, and Documentation](https://www.cdc.gov/yrbs/index.html)

### Citation Syntax
> Centers for Disease Control and Prevention (CDC). (2008). *Youth Risk Behavior Surveillance — United States, 2007*. Morbidity and Mortality Weekly Report (MMWR), 57(SS04), 1-131.

---

## 2. Data Engineering & Variable Codebook

This section details how the raw CDC YRBS variables were systematically isolated, encoded, and filtered using pure Python scripting to achieve the final analytic sample of **$N = 13,657$**.

### Independent Variable (IV): Emotional Distress Indicator
* **Original CDC Question Identifier:** `Q24`
* **Original Survey Question:** *"During the past 12 months, did you ever feel so sad or hopeless almost every day for two weeks or more in a row that you stopped doing some usual activities?"*
* **Analytical Column Name:** `SadOrHopeless`
* **Python Re-coding and Filtering Rules:**
  * Raw values of `1` (Yes) were mapped to `1`.
  * Raw values of `2` (No) were mapped to `0`.
  * Missing entries (` `), invalid responses, and non-responses (`3`, `4`, etc.) were rigorously dropped to eliminate skewness.

### Dependent Variable (DV): Weekly Exercise Frequency
* **Original CDC Question Identifier:** `Q79`
* **Original Survey Question:** *"During the past 7 days, on how many days were you physically active for a total of at least 60 minutes per day?"*
* **Analytical Column Name:** `PhysicalActivity5OrMoreDays`
* **Python Ordinal Scale Mapping (Score 1-8):**
  * `1` $\rightarrow$ 0 days of physical activity per week
  * `2` $\rightarrow$ 1 day of physical activity per week
  * `3` $\rightarrow$ 2 days of physical activity per week
  * `4` $\rightarrow$ 3 days of physical activity per week
  * `5` $\rightarrow$ 4 days of physical activity per week
  * `6` $\rightarrow$ 5 days of physical activity per week
  * `7` $\rightarrow$ 6 days of physical activity per week
  * `8` $\rightarrow$ 7 days of physical activity per week
  * *Data Cleaning Rule:* Any student row containing an empty or out-of-bounds index for this question was completely discarded.

---

## 3. Supplementary Demographic Indicators

To construct advanced stratification layouts (such as the Boxplot and Lollipop visualizations), basic background markers were processed from the raw survey matrix:

| Analytical Column | CDC Survey Question Ref | Representation Scope / Grouping Strategy |
| :--- | :--- | :--- |
| **Age** | `Q1` | Categorized from `<= 14` years old up to `18+` years old. Used to evaluate age-based mental health gap metrics. |
| **Weight** | Derived Anthropometric Vector | Extracted from the validated physical attributes column. Measured in kilograms (kg) to build statistical central tendency control baselines (Mean: 68.55 kg, Median: 65.32 kg). |

---

## 4. Analytic Sub-Sample Summary Matrix

Following the execution of the custom automated data pre-processing script, the structural integrity of the workspace dataset is defined by the following distribution:

* **Total Valid Sample Power ($N$):** 13,657 records
  * **Not Sad Control Group Layer:** $n = 9,566$ students ($70.04\%$)
  * **Sad/Hopeless Cohort Group Layer:** $n = 4,091$ students ($29.96\%$)
* **Mathematical Variance Framework:** One-Way Analysis of Variance (ANOVA) testing for behavioral dispersion limits.