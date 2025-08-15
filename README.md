# Association-of-Brain-Function-and-Structure-with-Neuropsychological-Measures
Used R to explore whether Diffusion Tensor Imaging (DTI) biomarkers (`Fractional Anisotropy (FA),` `Mean Diffusivity (MD)`) relate to cognitive function `Test of Variables of Attention (TOVA)` in Hurler syndrome. Significant group differences in FA/MD values were found, but no differential impact on TOVA d-prime by group. The analysis involved t-tests, regression models, and interaction terms.

## Statistical Analysis Plan (SAP)
**NOTE:** Only the Statistical Analysis Plan (SAP) and the code used for the data analysis are posted on this repository. The Statistical Analysis Report and the dataset used will not be posted.

## INTRODUCTION
Hurler syndrome is a rare lysosomal storage disorder caused by a deficiency in the enzyme alpha-L-iduronidase. Clinically, patients are classified into two primary groups: attenuated and severe. Treatment protocols differ substantially between these groups. Patients with the severe phenotype typically undergo hematopoietic stem cell transplantation (HSCT), whereas those with the attenuated form receive enzyme replacement therapy (ERT). Despite these early interventions, cognitive impairments often persist in both populations.

These impairments may be associated with abnormalities in white matter structure and integrity, which can be detected through Diffusion Tensor Imaging (DTI), a neuroimaging modality that captures microstructural changes in the brain. Two DTI-derived metrics are of primary interest: fractional anisotropy (FA), which reflects axonal organization, and mean diffusivity (MD), which indicates the extent of water diffusion within brain tissue. Generally, higher FA and lower MD values are interpreted as markers of healthier white matter.

This study investigates whether FA and MD are associated with cognitive function, specifically attention, as measured by the Test of Variables of Attention (TOVA). The primary outcome is the TOVA d-prime score (TOVAd). The key objective is to determine whether the associations between these imaging biomarkers and neurocognitive performance differ significantly between the attenuated and severe patient groups.

## DATASET
The dataset titled DTI data.csv includes demographic, clinical, imaging, and neuropsychological data for pediatric patients diagnosed with Hurler syndrome. The clinical group variable distinguishes patients as either attenuated or severe. Demographic variables include sex and age, with age transformed from months to years. Medical risk status is captured by a binary variable (MedRiskBinary), indicating the presence or absence of comorbid medical conditions.
Neuropsychological functioning is assessed using multiple standardized instruments. These include Full Scale IQ (FSIQ), memory (California Verbal Learning Test, CVLT), and spatial ability (Judgment of Line Orientation, JLO). Attention is evaluated using five components of the TOVA: d-prime (TOVAd), omission errors (TOVAOm), commission errors (TOVACom), reaction time (TOVART), and variability (TovaVAR). Imaging variables include FA and MD, both derived from DTI scans and representing markers of white matter microstructure.

**Data Preparation:**

Prior to analysis, several transformations were applied to prepare the dataset. The Group variable was recoded as a factor with two levels: “attenuated” (coded as 1) and “severe” (coded as 2). Age in months was converted to years for interpretability. The MedRisk variable was recoded into a binary indicator (MedRiskBinary), where a value of 1 denotes the presence of one or more medical risk factors. Descriptive statistics for all major variables were then stratified by group to facilitate group-wise comparisons.

## EXPLORATORY DATA ANALYSIS (EDA)
Descriptive statistics for key demographic, clinical, imaging, and cognitive variables are presented in Table 1. Group comparisons of FA and MD values were conducted using two-sample t-tests, with statistical significance set at p < 0.05. To assess the relationship between imaging measures and cognitive performance, Pearson correlation matrices were calculated separately for each group using the variables FA, MD, and TOVAd. To support interpretation, scatterplots were generated for the FA–TOVAd and MD–TOVAd associations, stratified by patient group.

## METHOD
**Primary Analyses:**

To evaluate the relationship between imaging biomarkers and attention performance, three linear regression models were fitted. These models aimed to determine whether group status (attenuated vs. severe) modifies the effect of FA and MD on 

**TOVA d-prime scores:**

**Model 1:** TOVAd predicted by FA, group, and FA × group interaction.

**Model 2:** TOVAd predicted by MD, group, and MD × group interaction.

**Model 3:** TOVAd predicted by both FA and MD, group, and all corresponding interaction terms.

All models were fitted using complete cases. Interaction terms were included to assess potential effect modification by patient group. Model assumptions were validated using standard diagnostic plots, including residuals versus fitted values, Q-Q plots for residual normality, and leverage plots to detect influential data points. These diagnostics revealed no substantial violations, although minor deviations in normality and variance were observed.

**Model Fit And Comparison:**

Model performance was assessed using both R-squared and adjusted R-squared metrics. Additionally, Akaike Information Criterion (AIC) values were calculated for each model to facilitate comparisons of relative model fit, where lower AIC values indicate better model performance.

**Sensitivity Analysis:**

Two sensitivity analyses were conducted to evaluate the robustness of the primary model:
Inclusion of Medical Risk: Model 3 was refitted with the MedRiskBinary variable as an additional covariate. The adjusted R-squared value increased slightly, suggesting a modest improvement in the model's explanatory power.

Exclusion of Influential Observations: Observations with high influence, defined as Cook’s distance greater than 4/n, were excluded. The model was re-estimated on the filtered dataset. Exclusion of influential data points led to a marginal improvement in model stability and adjusted R-squared.

**Effect Size And Strength Of Association:**

To compare the relative contributions of each predictor, standardized regression coefficients (beta weights) were calculated for Model 3. These standardized coefficients provide insight into the strength of association on a common scale. FA showed a stronger association with TOVA d-prime compared to MD. Interaction terms further revealed that the effect of FA on attention performance was more pronounced in the severe group than in the attenuated group, indicating potential effect modification by treatment exposure or disease severity.

**Secondary Analysis:**

In addition to TOVAd, the multivariable regression models were extended to the four other TOVA subscales: TOVAOm, TOVACom, TOVART, and TovaVAR. These exploratory models aimed to assess whether FA and MD are associated with broader aspects of attention and executive functioning. Results were summarized and interpreted in the context of cognitive domains potentially influenced by white matter abnormalities.

This analysis provides evidence that white matter integrity, as measured by FA and MD, is significantly associated with neuropsychological performance in children with Hurler syndrome. The nature of these associations differs by patient group, suggesting that clinical phenotype and treatment modality may moderate the impact of white matter structure on cognitive function. Diagnostic checks and sensitivity analyses support the reliability of these findings. Among the imaging markers, FA emerged as a stronger predictor of attention-related performance, particularly within the severe group. These results underscore the value of DTI biomarkers in understanding neurodevelopmental outcomes in rare genetic disorders.

## 📄 License

This project is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International License](https://creativecommons.org/licenses/by-nc/4.0/).

© 2025 Emmanuel Fle Chea. See the LICENSE file for full terms and usage guidelines.

