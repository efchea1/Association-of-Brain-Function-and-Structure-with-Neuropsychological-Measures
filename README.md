# Association-of-Brain-Function-and-Structure-with-Neuropsychological-Measures
Used R to explore whether Diffusion Tensor Imaging (DTI) biomarkers (Fractional Anisotropy (FA), Mean Diffusivity (MD)) relate to cognitive function `Test of Variables of Attention (TOVA)` in Hurler syndrome. Significant group differences in FA/MD values were found, but no differential impact on TOVA d-prime by group. The analysis involved t-tests, regression models, and interaction terms.

## Statistical Analysis Plan (SAP)
**NOTE:** Only the Statistical Analysis Plan (SAP) and the code used for the data analysis are posted on this repository. The Statistical Analysis Report and the dataset used will not be posted.

## INTRODUCTION
Hurler syndrome is a rare genetic disorder in which patients are clinically classified as either having an attenuated or severe form of the disease. Treatment protocols vary substantially between these two groups. Patients with the severe form typically undergo bone marrow transplantation, while those with the attenuated form receive enzyme replacement therapy. Despite treatment, both groups continue to experience cognitive impairments. These impairments may be associated with alterations in white matter integrity resulting from the disease itself or its treatment. This study aims to investigate whether fractional anisotropy (FA) and mean diffusivity (MD), two imaging biomarkers derived from Diffusion Tensor Imaging (DTI), are associated with cognitive functioning. Cognitive function is assessed using the Test of Variables of Attention (TOVA), a standardized neuropsychological tool. Specifically, the analysis examines whether the associations between FA and MD values and TOVA performance scores differ significantly between the severe and attenuated patient groups.

## DATASET
The dataset used for this analysis, titled "DTI data.csv", includes clinical, imaging, and neuropsychological variables. The primary clinical covariate is the patient group classification (severe versus attenuated). Neuropsychological functioning is evaluated through several TOVA components, including d-prime (TOVAd), omission errors (TOVAOm), commission errors (TOVACom), reaction time (TOVART), and variability (TovaVAR). Imaging measures of white matter integrity consist of FA and MD values obtained from DTI scans.

Several data transformations were performed before analysis. The Group variable was recoded as a categorical factor with two levels: "attenuated" (coded as 1) and "severe" (coded as 2). The variable Age, initially recorded in months, was converted to years for interpretability. Additionally, the Medical Risk Factors variable was renamed for clarity and recoded into a binary indicator variable. Patients with one or more medical risk factors (i.e., MedRisk > 0) were coded as “1”, while those without were coded as “0”.

## EXPLORATORY DATA ANALYSIS (EDA)
To explore the structure of the data and identify potential group differences, descriptive statistics were calculated for all key variables (FA, MD, and TOVA components), stratified by patient group. These summaries are presented in Table 1. Two-sample t-tests were conducted to compare FA and MD values between the attenuated and severe groups, with statistical significance set at p < 0.05. In addition, Pearson correlation analyses were performed separately within each group to assess the relationships among FA, MD, and TOVAd. To aid visual interpretation, scatterplots were generated showing the associations between FA and TOVAd and between MD and TOVAd, stratified by patient group.

## METHOD
The primary analytic approach consists of linear regression models with interaction terms to evaluate whether the associations between imaging measures (FA and MD) and cognitive performance differ by patient group. Three models were fit:
Model 1 examines TOVAd as a function of FA, group, and their interaction term.
Model 2 models TOVAd based on MD, group, and their interaction.
Model 3 includes both FA and MD as predictors, along with group and all relevant interaction terms.


Linear regression with interaction terms is appropriate for this analysis, as it allows for the testing of effect modification by group status. All analyses were conducted using complete cases only. Standard model validation procedures, including the examination of residuals, were used to assess adherence to linear regression assumptions. The primary outcome of interest is TOVA d-prime (TOVAd), with additional exploratory analyses for other TOVA components. The models were evaluated using regression coefficients, standard errors, t-statistics, and p-values. Analyses were performed using R version 4.3.2, and a two-sided p-value of less than 0.05 was considered statistically significant.
