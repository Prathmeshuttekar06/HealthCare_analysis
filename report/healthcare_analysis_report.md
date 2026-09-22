# Healthcare Data Analysis Report

## 1. Executive Summary

This project analyzes patient, admission, billing, and treatment-test data from the cleaned healthcare dataset. The analysis combines Python-based exploratory analysis, exported visualizations, and a Tableau dashboard to identify broad patterns in the patient population and hospital activity.

The cleaned dataset contains **54,966 patient records** and **17 fields**. The population is almost evenly split by gender, the largest age group is patients aged 65 and above, and Arthritis is the most frequent medical condition. Elective admissions are slightly more common than Urgent and Emergency admissions. Average billing amounts are highest for Obesity and Diabetes in this dataset, although the differences between conditions are relatively small.

## 2. Project Objectives

- Understand the demographic composition of the patient population.
- Compare the frequency of major medical conditions.
- Examine admission types and hospital utilization patterns.
- Compare billing amounts across medical conditions and admission types.
- Analyze average length of stay by medical condition.
- Explore the relationship between patient age and billing amount.
- Summarize test-result patterns by medical condition.

## 3. Data and Preparation

The analysis uses `Data/healthcare_cleaned.csv`. The dataset includes patient demographics, blood type, medical condition, admission and discharge dates, provider and hospital details, insurance, billing amount, admission type, medication, test results, length of stay, and age group.

The analysis workflow performs the following preparation steps:

1. Removes duplicate records.
2. Converts admission and discharge dates to date values.
3. Converts billing amounts to numeric values.
4. Calculates length of stay from the admission and discharge dates.
5. Groups ages into Under 18, 18-34, 35-49, 50-64, and 65+ categories.

The cleaned CSV contains **54,966 records**, **17 columns**, and no duplicate rows were detected during this report preparation. The source notebook is available at `Notebook/healthcare_analysis.ipynb`.

## 4. Descriptive Findings

### 4.1 Demographics

| Measure | Result |
|---|---:|
| Male patients | 27,496 |
| Female patients | 27,470 |
| Mean patient age | 51.54 years |
| Largest age group | 65+ |
| Patients aged 65+ | 16,923 |
| Patients under 18 | 116 |

The gender distribution is effectively balanced. Older adults form the largest age segment, while patients under 18 represent a very small portion of the records. This population structure should be considered when interpreting condition, billing, and utilization patterns.

### 4.2 Medical Conditions

| Medical condition | Patient records |
|---|---:|
| Arthritis | 9,218 |
| Diabetes | 9,216 |
| Hypertension | 9,151 |
| Obesity | 9,146 |
| Cancer | 9,140 |
| Asthma | 9,095 |

Arthritis is the most frequent condition, but all six conditions occur at similar volumes. The small spread between the highest and lowest counts suggests that the dataset is relatively balanced across these condition categories.

### 4.3 Admission Types

| Admission type | Patient records |
|---|---:|
| Elective | 18,473 |
| Urgent | 18,391 |
| Emergency | 18,102 |

Elective admissions are the most common, followed closely by Urgent and Emergency admissions. The differences are modest, so admission type does not show a strongly dominant category in this dataset.

## 5. Billing and Utilization Analysis

### 5.1 Overall Billing and Length of Stay

| Measure | Result |
|---|---:|
| Mean billing amount | 25,544.31 |
| Median billing amount | 25,543.05 |
| Mean length of stay | 15.50 days |

The mean and median billing amounts are very close, indicating that the overall billing distribution is centered without a large separation between these two summary measures. The average recorded stay is approximately 15.5 days.

### 5.2 Billing and Stay by Condition

| Medical condition | Mean billing amount | Mean length of stay |
|---|---:|---:|
| Obesity | 25,804.36 | 15.45 days |
| Diabetes | 25,660.48 | 15.43 days |
| Asthma | 25,633.46 | 15.68 days |
| Arthritis | 25,511.78 | 15.50 days |
| Hypertension | 25,503.06 | 15.44 days |
| Cancer | 25,152.32 | 15.50 days |

Obesity has the highest average billing amount, while Cancer has the lowest among the six conditions. Asthma has the longest average stay. The average lengths of stay are tightly grouped, so condition-specific differences in duration are limited in this dataset.

## 6. Visual Analysis and Dashboard

The `Visuals/` folder contains charts for:

- Patient count by medical condition
- Average billing amount by medical condition
- Billing amount distribution by admission type
- Age versus billing amount
- Average length of stay by medical condition

The Tableau dashboard is available in two formats:

- `tableau/HealthCare_dashboard.twb` - Tableau workbook definition in XML format.
- `tableau/HealthCare_dashboard.twbx` - Packaged workbook containing the workbook and cleaned CSV data.

The `.twbx` file is the recommended file for opening the dashboard because it includes the data source used by the workbook.

## 7. Key Conclusions

1. The dataset is large enough to compare several conditions and admission categories, with 54,966 records available for analysis.
2. The patient population is nearly evenly split by gender and is concentrated in older age groups.
3. Medical-condition counts are relatively balanced, with Arthritis marginally the most common condition.
4. Elective, Urgent, and Emergency admissions occur at similar frequencies.
5. Average billing amounts vary by condition, with Obesity highest and Cancer lowest in this dataset.
6. Average length of stay is stable across conditions at approximately 15.4 to 15.7 days.

## 8. Limitations and Next Steps

This is a descriptive analysis. It does not establish causal relationships between medical conditions, admission types, length of stay, and billing amounts. The dataset also does not provide enough context to evaluate clinical outcomes, treatment effectiveness, readmission risk, or whether billing amounts reflect actual paid costs.

Recommended next steps include:

- Validate date and length-of-stay definitions with the data owner.
- Investigate billing differences by insurance provider, hospital, and admission type.
- Examine test results and medication patterns alongside outcomes.
- Add time-based analysis to identify changes in admissions and billing.
- Use statistical testing or predictive modeling for deeper analysis.