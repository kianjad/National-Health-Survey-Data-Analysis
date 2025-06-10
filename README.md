# National Health Survey Data Analysis: Lifestyle Impact on Health Outcomes

This project investigates health-related hypotheses using comprehensive data from the National Health and Nutrition Examination Survey (NHANES).  It applies statistical modeling to explore the relationships between various lifestyle factors and health outcomes. 

## Key Questions & Hypotheses

**Liver Condition & Diet Quality:** Does the presence of a liver condition influence an individual's self-reported diet quality? 
**Smoking & COPD Diagnosis:** Is increased cigarette consumption associated with higher odds of reporting a COPD diagnosis? 
**Sleep Duration & Depression Severity:** Is insufficient weekday sleep correlated with a greater likelihood of experiencing frequent depressive symptoms? 

## Data Source

The dataset used is from the **National Health and Nutrition Examination Survey (NHANES)**, a program designed to assess the health and nutritional status of adults and children in the United States. 

* **Download:** You can download the raw data from the official NHANES website (https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2017-2020).
* **Preprocessing:** Data cleaning involved filtering for relevant variables, handling missing values by focusing on variables of interest, and converting specific character strings to numeric. Outliers in `smoke_amount` were identified using the IQR method.  Key transformations included creating a binary `sleep_category` and converting ordered factors like `depression` and `diet_survey` to numeric values. 

## Methodology

This study primarily employed **logistic regression models** suited to the outcome variable types: 

* **Ordinal Logistic Regression:** Used for hypotheses with ordinal outcomes (Diet Quality, Depression Severity) via R's `polr()` function from the `MASS` package. 
* **Binary Logistic Regression:** Applied for the hypothesis with a binary outcome (COPD Diagnosis) via R's `glm()` function with `family = binomial`. 

Models included one main predictor based on each hypothesis, with coefficients and p-values interpreted to assess statistical significance. 

## Key Findings

* A **statistically significant association** was found between higher cigarette consumption (`smoke_amount`) and increased odds of reporting a **COPD diagnosis** (p < 0.001, positive coefficient).  This trend was also visually evident with higher smoking categories showing a greater proportion of COPD diagnoses. 
* No statistically significant relationships were found for the hypotheses linking liver condition to diet quality or weekday sleep duration to depressive symptoms. 

## How to Run the Code

1.  **Prerequisites:** Ensure you have R and RStudio installed.
2.  **R Packages:** Install the necessary R packages (e.g., `dplyr`, `ggplot2`, `MASS`, `tidyverse`, etc.
3.  **Data Download:** Download the relevant NHANES dataset.
4.  **Execute R Markdown:** Open the `.Rmd` file in RStudio and knit it to reproduce the analysis and generate the report.

## Technologies Used

* **R**
* **RStudio**
* **R Packages:** (e.g., `dplyr`, `ggplot2`, `MASS`, `tidyr`, `readr`, etc. - *list specific ones from your Rmd*)
* **Markdown**

---

Kian Jadbabaei
