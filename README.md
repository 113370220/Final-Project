## Student Information
- **游子涵**
- **Student ID**: 113370220

## Project Repository
- https://github.com/113370220/Final-Project

## Presentation Video
- [填入你錄好上傳到 YouTube 的影片網址]

---

# Research Project: Teenage Mental Health Status and Physical Activity

## 1. Research Question
Does an adolescent's mental health status (specifically, persistent feelings of sadness or hopelessness) significantly influence their physical activity levels?

## 2. Variables & Data Source
- **Dataset**: CDC Youth Risk Behavior Survey (YRBS) 2007
- **Independent Variable (IV)**: `SadOrHopeless` (Categorical: 1 = Yes, 2 = No)
- **Dependent Variable (DV)**: `PhysicalActivity5OrMoreDays` (Ordinal Scale: 1 to 8, representing the frequency of exercising for 60+ minutes)

## 3. Data Cleaning & Methodology
The data preparation was executed using Python. All missing values, non-responses, and invalid entries were filtered out, resulting in a final robust sample size of **13,657 students**. 
A One-Way ANOVA (Analysis of Variance) approach was used to examine the mean differences in physical activity between the two mental health groups.

## 4. Descriptive Statistics & Results

| Mental_Health | Sample_Size | Mean_Score | Std_Dev |
| :--- | :--- | :--- | :--- |
| Not Sad | 9566 | 4.17 | 2.57 |
| Sad/Hopeless | 4091 | 3.74 | 2.53 |

### Statistical Testing
- **F-statistic**: 79.4678
- **p-value**: < 0.0001 (Highly Significant)

## 5. Interpretation & Conclusion
The statistical analysis reveals a highly significant difference between the two groups. Students who did not experience persistent feelings of sadness or hopelessness in the past 12 months reported a higher frequency of physical activity (Mean = 4.17) than those who suffered from emotional distress (Mean = 3.74).

This indicates a clear negative association between psychological distress and physical lifestyle habits among teenagers. Mental health issues may act as a barrier to physical exercise, or conversely, regular exercise may serve as a protective factor for mental well-being.# Final-Project
Research project on teenage mental health status and physical activity using YRBS 2007 dataset.
