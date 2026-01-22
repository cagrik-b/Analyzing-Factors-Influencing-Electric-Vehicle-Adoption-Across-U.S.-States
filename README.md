### Analyzing Factors Influencing Electric Vehicle Adoption Across U.S. States ###
***Çağrı KARAKAŞ 33916***


*I am Çağrı Karakaş. My student number is 33916. I am a Data Science and Analytics major at Sabancı University. This repository documents my project where I am going to investigate electric vehicle adoption rates and the reasons behind these rates by analyzing related US data.*



## Contents ##

1) [Introduction](#1-introduction)
2) [Project Idea](#2-project-idea-and-objective)
3) [Motivation](#3-motivation)
4) [Data Sources and Information](#5-data-sources-and-information)
5) [Methodology](#4-methodology)
6) [Hypothesis](#6-hypothesis)
7) [Reults](#7-results)
8) [Important Findings](#8-important-findings)
9) [Limitations and Future Work](#9-limitations-and-future-work)


## 1. Introduction ##

***The Rise of Electric Vehicles(EVs)***

The move toward electric vehicles has marked an incredible shift in personal transportation, motivated by goals like lowering greenhouse gas emissions, lessening fossil fuel usage, and enhancing urban air quality. In recent years, EV technology has progressed significantly, as battery prices have decreased and driving distances have expanded, making them a more logical choice for drivers to prefer, producers to manufacture, and governments to promote.

Governments and producers are making significant investments to electrification in transportation throughout the globe. Nevertheless, the actual preference of EVs among consumers is not consistent and uniform. Examining various places, such as the states in the US, shows considerably different rates of electric vehicle adoption among the public sphere.

Common knowledge and current studies indicate several major elements affecting this trend: the initial expense of EVs cmpared to conventional vehicles, the accessibility and quantity of charging points, governmental incentives, charging costs, and also consumer vision and awareness on the environment. The United States presents a notably fascinating opportunity for study because of the access to comprehensive state-level data on numerous potential influences, and clear indications of distinct differences in adoption rates across various states. Although we may anticipate that states which have more economic prosperity stricter environmental policies will take the lead, the actual situation is mostly more complicated. This situation intends to apply data science and analytical methods to investigate these cases.



## 2. Project Idea and Objective ##

It is known that electric vehicles (EVs) are becoming more and more common. However, when you check the relevant data and statistics, some states seem to be far ahead while others fall behind in EV adoption. It’s easy to assume that wealthier states or those with more public charging stations tend to have more EVs. Still, I’m curious about the states that don’t follow this simple trend. Why might a state with an average income have a surprisingly high number of EVs? Or why might a wealthy state have fewer than expected? 

This project will examine state-level data to see which factors—money, infrastructure, socioeconomic and sociocultural levels of people, environmental situations—really can explain the difference in EV adoption rates. Specifically, states that stand out, whether they are performing much better or worse than a basic and predictable model would suggest, and possible reasons for these differences will be investigated in this project.

***Core Question***

What other criteria, beside from the basic ones, such as affluence and the availability of chargers, contribute to the explanation of why certain US states exhibit markedly higher or lower adoption rates of electric vehicles than others?



## 3. Motivation ##

The drive for electric cars is more than simply a trend; it's a cruical part of solving more ceomprehensive global issues like air pollution and climate change. Identifying what factors, other than price or charger availability, truly motivate people to purchase EVs is a difficult task with significant challenge not only for government policies but also business strategies. Since working in business analytics department in the future is in one of my plans for the future, I thought this project could be a nice starting point.

In addition to the usefulness; I am not educated well enough in this subject, so I'm actually interested in the trends and. Are financial incentives and charging stations the only factors influencing EV adoption, or do other factors like population education, population density, or even air quality have a big impact? It seems like apuzzle to solve using statistics why some states appear to adopt EVs at a faster rate than others. It's an opportunity to determine whether the evidence confirms widely held opinions or perhaps provides a more complex picture.

Moreover; this subject is a up-to-date topic, so it seemed to me like a suitable and interesting choice to apply the modeling and data analysis methods that I am currently learning in DSA210. Also; thanks to the abundance of publicly available data on the topic i prefered US states as the reference place.



## 5. Data Sources and Information ##

*Note: 2024 data will be used, since it is the only common and most recent year for all data*
*Note: All data can be seen in the repository*

**Primary (Dependent) Variable**

  -*Data*: Electric Vehicle (BEV) Registrations per capita (for 2023 but updated    for 2024).

  -*Source*: U.S. Department of Energy (DOE) Alternative Fuels Data Center (AFDC).

  -*Collection Method*: Downloaded state-level EV registration counts from 
    https://afdc.energy.gov/data/search?q=electric+vehicle+registrations.

**Enrichment (Independent) Variables**

***Economic Factors:***

  -*Data*: Dollar GDP per capita (2024), Median Household Income (2024 ACS 1-Year Estimates).

  -*Source*: Bureau of Economic Analysis (BEA), U.S. Census Bureau (ACS Table S1901).

  -*Collection Method*: GDP: Downloaded state-level CSV from
   https://www.bea.gov/data/gdp/gdp-state
    Income: Downloaded state-level CSV by searching for Table S1901 on
    https://data.census.gov/

***Infrastructure Factors:***

  -*Data*: Public Charging Ports(2024)

  -*Source*: U.S. Department of Energy, Alternative Fuels Data Center (AFDC)

  -*Collection Method*: Downloaded national station database CSV from
    https://afdc.energy.gov/data_download
   
***Demographic Factors:***

  -*Data*: Population and Population Density (2024), Educational Attainment (% Bachelor's degree+, age 25+, 2024 ACS 1-Year Estimates).

  -*Source*: Kaggle, U.S. Census Bureau (Population Estimates Program / ACS Table S1501).

  -*Collection Method*:Population and Population Density: Downloaded state estimates from
    https://www.kaggle.com/datasets/dataanalyst001/us-states-ranked-by-population-2024
    Educational Attainment: Downloaded state-level CSV by searching for Table S1501 on
    https://data.census.gov/

***Environmental Factors:***

  -*Data*: Average Median Daily AQI (2024).

  -*Source*: Environmental Protection Agency (EPA) AirData.

  -*Collection Method*: Downloaded annual state summary CSV from
    https://www.epa.gov/outdoor-air-quality-data
    

## 4. Methodology ##

**a. Motivation and Project Idea**
  
-Decided on a relevant, up-to-date topic with a motivation concerning in personal future plans, curiosity and world problems.

**b. Data Collection**
 
-Various government and trustworthy data sources examined. Useful and relevant data selected.

**c. Exploratory Data Analysis**

-Data cleaned and relevant information selected.
  
-Summary statistics calculated.
  
-Various visualisations for the data displayed.
  
-Correlations calculated.

**d. Hypothesis Testing**

-Shapiro-Wilk Test used to check normality in order to decide which hypothesis tests to be conducted.
  
-Spearmann Rank Correlation has been utilised to test the baseline hypothesis.
  
-Mann–Whitney U Test and Kruskal–Wallis Test used to test the deviation hypothesis.

**e. Machine Learning**

-Multiple Linear Regression was used as a baseline model for prediction.

-KNN Regression was used to catch local patterns.

-Decision Tree and Random Forest Regression was conducted for non-linear decision rules.

-Corss-Validation techniques were utilised for model comparison and prediction evaluation.


## 6. Hypothesis ##   

**Overall Relationship**

*Null Hypothesis (H₀)*: The combined economic, infrastructure, demographic, and environmental characteristics of a state do not statistically significantly correlate with its EV adoption rate (EVs per capita).

*Alternative Hypothesis (H₁)*: EV adoption rates will be substantially greater in states with attributes that are generally linked to higher adoption, such as wealth, more chargers, more education, denser populations, and possibly worse air quality.

**Deviation from Baseline**

*Null Hypothesis (H₀-deviation)*: No other measured factors, such as population density, educational attainment, or air quality, significantly explain the remaining variation in EV adoption rates after controlling for core economic (GDP per capita) and infrastructure (chargeing station availability) factors.

*Alternative Hypothesis (H₁-deviation)*: Some states do differ from observed EV adoption levels, and this is largely explained by factors other than basic wealth and charger abundance. (For example, negative residuals (lower-than-expected adoption) may be linked to lower educational attainment, whereas positive residuals (higher-than-expected adoption) may be linked to higher population density or worse air quality.)


## 7. Results ##

### Exploratory Data Analysis (EDA)

The exploratory analysis revealed substantial variation in electric vehicle (EV) adoption across U.S. states. EV registration counts are unevenly distributed, with a small number of states accounting for a large share of total registrations. Similar patterns were observed in key explanatory variables such as GDP, charging infrastructure, and educational attainment, indicating meaningful structural differences between states.

Visualizations and summary statistics suggested clear upward trends between EV registrations and several variables, particularly GDP, number of charging stations, and education level. These patterns provided early evidence that economic capacity and infrastructure availability are strongly linked to EV adoption. In contrast, population density, household income, and air quality showed weaker and less consistent visual relationships with EV registrations.

Overall, the EDA supported the project’s initial motivation by highlighting that EV adoption is not uniform across states and appears to be influenced by a combination of economic, infrastructural, and demographic factors.

---

### Hypothesis Testing

The results consistently supported the alternative hypotheses.

For the overall relationship hypothesis, all examined variables demonstrated statistically significant associations with EV registrations. This led to the rejection of the null hypothesis, confirming that state-level economic, infrastructural, demographic, and environmental characteristics are related to EV adoption rates.

More importantly, the deviation-from-baseline hypothesis was also supported. While GDP and charging infrastructure emerged as the strongest predictors, educational attainment remained significant even after accounting for these core factors. This suggests that EV adoption is influenced not only by material conditions such as wealth and infrastructure, but also by broader social factors that may reflect awareness, attitudes, or readiness to adopt new technologies.

Variables such as population density and air quality showed weaker effects, indicating that their influence on EV adoption is secondary compared to economic and infrastructure-related drivers.

| Hypothesis | Variables Tested | Test(s) Used | Result | Decision |
|-------------|------------------|--------------|---------|-----------|
| **Overall Relationship (H₁)** | GDP, HI, EA Info, CS Count, Density, AQI | Spearman Correlation | All p < 0.05 | Reject H₀ (Significant) |
| **Deviation from Baseline (H₂)** | EA Info, Density, AQI, CS Count | Mann–Whitney U, Kruskal–Wallis | Partial (Education, Chargers significant) | Partial Rejection of H₀-deviation |

---

### Machine Learning Results

The machine learning analysis was conducted to evaluate whether the relationships identified in the earlier phases remain relevant when all variables are considered jointly in a predictive framework. Among the tested models, multiple linear regression achieved the best performance, explaining approximately 62% of the variation in EV registrations across states.

The strong performance of the linear model reinforces the findings from both the exploratory analysis and hypothesis testing. It suggests that the key factors influencing EV adoption operate in a relatively systematic and additive manner at the state level. More complex models did not improve predictive accuracy, likely due to the small sample size and the aggregated nature of the data.

Overall, the machine learning results serve as a validation step, confirming that the relationships identified earlier are not only statistically significant but also useful for prediction.

| Model | R² | RMSE |
|------|----|------|
| Linear Regression | 0.624 | 199407.40 |
| KNN Regression | 0.119| 305420.98 |
| Decision Tree | 0.098| 309047.58 |
| Random Forest | 0.187 | 293338.84 |


## 8. Important Findings ##

- **Economic capacity and charging infrastructure are the primary drivers of EV adoption.**  
  States with higher GDP levels and more extensive charging networks consistently show higher EV registration rates across all stages of the analysis.

- **Educational attainment plays a meaningful role beyond economic factors.**  
  Even after accounting for wealth and infrastructure, education remains an important factor, supporting the project’s deviation-from-baseline hypothesis.

- **Simpler models effectively capture EV adoption patterns.**  
  The success of linear regression indicates that EV adoption responds in a largely proportional manner to changes in key structural variables.

- **Demographic and environmental factors have weaker effects.**  
  Population density and air quality are associated with EV adoption, but their influence is smaller compared to economic and infrastructure-related factors.

- **Results are consistent across methods.**  
  The alignment between EDA, hypothesis testing, and machine learning strengthens confidence in the conclusions and supports the overall validity of the project.

Together, these findings suggest that differences in EV adoption across U.S. states reflect broader structural and social conditions rather than isolated or random effects, directly addressing the project’s core research question.


## 9. Limitations and Future Work

### Limitations

This study is subject to several limitations that should be considered when interpreting the results. First, the analysis is based on state-level aggregated data, which may mask important within-state variation. Differences across cities or regions within the same state, such as urban–rural divides or local policy differences, are not captured in the current dataset.

Second, the relatively small sample size, limited to the 50 U.S. states, constrains the complexity of statistical and machine learning models that can be reliably applied. While this makes simpler models more appropriate, it also limits the ability to explore more detailed interaction effects or non-linear relationships.

Third, the study relies on a single cross-sectional snapshot of data. As a result, temporal dynamics—such as how changes in charging infrastructure or economic conditions affect EV adoption over time—cannot be examined. Additionally, some potentially relevant factors, such as state-level policy incentives, fuel prices, and consumer attitudes toward environmental issues, are not explicitly included due to data availability constraints.

Finally, although machine learning models were used to assess predictive relationships, the results should not be interpreted as causal. The identified associations indicate patterns rather than direct cause-and-effect relationships.

---

### Future Work

Future research could address these limitations in several ways. One natural way would be to add **time-series or panel data**, allowing for the analysis of trends in EV adoption and the impact of policy changes over time. This would provide stronger insights into the dynamics of EV adoption rather than static relationships.

Another promising direction would be to conduct the analysis at a more granular geographic level, such as countries or metropolitan areas. This could help uncover localized patterns and better capture the influence of urbanization, infrastructure placement, and regional policy differences.

Future studies could also expand the set of explanatory variables by including information on **government incentives**, **fuel prices**, **vehicle availability**, or **consumer attitudes toward sustainability**. Incorporating such variables may help explain deviations in EV adoption that are not fully captured by economic and infrastructural factors alone.






    



