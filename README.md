# data512-project
This repository contains the final project for DATA 512: Human Centered Data Science at UW.

Count Assigned: Maricopa County, Arizona, United States

## Goal/Motivation

COVID-19 has had a massive impact on the world in the last couple of years. The rapid spread of COVID-19 endangered lives, disrupted livelihoods, and impacted global trade, the economy, and businesses. The world economy had started to experience significant disruptions and was and is still moving toward a severe recession and an unprecedented economic crisis. All nations have experienced challenges as a result of COVID-19, but many nations have had to deal with a more difficult situation because of their large populations, subpar health services, high rates of poverty, poor socioeconomic conditions, and inadequate social protection systems. According to Dr. William Cockerham, the Chief Sociologist at the University of Alberta, he says “Socioeconomic status is the strongest indicator of health, disease resistance and longevity in medical sociology”. We try to corroborate his theory in our analysis.

The UN’s Framework for the Immediate Socio-Economic Response to the COVID-19 Crisis warned that “The COVID-19 pandemic is far more than a health crisis: it is affecting societies and economies at their core. While the impact of the pandemic will vary from country to country, it will most likely increase poverty and inequalities on a global scale.”.  To educate and customize government and partner responses to the COVID-19 issue and ensure that no one is left behind in this effort, it is essential to assess the implications of the crisis on communities, economies, and vulnerable people. These factors can directly affect the ability to earn, the representation of race or caste in society, education, etc.

Hence, how did the pandemic impact such factors interest us the most? For this analysis, we target the socioeconomic factors primarily but focus mainly on economic ones. We try to do a fine-grained analysis of the socioeconomic implications of COVID-19 in Maricopa County, Arizona in the United States. We understand the implications at the individual level and industry level. The broader level question that this analysis tries to answer is: 
What were the immediate and gradual impacts of COVID-19 on socioeconomic factors at the community and industrial level in Maricopa County in Arizona?


## Research Questions
The five main research questions that we answer using this analysis are: 
1. What was the effect of masking policies on the COVID-19 case count? 
2. What was the influence of the pandemic on the unemployment rate and Civil Labor Force in the county?  
3. How did the socioeconomic factors (Education, Median Household Income, and Gross Domestic Product) change during the early stage of the pandemic?  
4. How did the COVID-19 cases affect the economic indexes of the county in different industries?  
5. What are the other factors that help measure the overall community risk for similar epidemics/pandemics in the future? 


## Datasource Information (Description, Source and License)

Following are the datasets that we used for all of the questions mentioned above.
1. Covid-19 data: 
We use the COVID-19 masking dataset as provided in the Common Analysis part (Question 1). The COVID-19 cases dataset is used for all the questions. a) [John Hopkins University COVID-19 data](https://www.kaggle.com/datasets/antgoldbloom/covid19-data-from-john-hopkins-university) (License: Attribution 4.0 International (CC BY 4.0)). b) [Masking mandates by county](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) (NCHS: Can be used for Statistical reporting and analyses)
c) [The New York Times mask compliance survey data](https://github.com/nytimes/covid-19-data/tree/master/mask-use) (Copyright 2021 by The New York Times Company, used for non-commercial purposes)

2. [Federal Reserve Economic Data, FRED Monthly Data](https://fred.stlouisfed.org/series/LAUCN040130000000004):
The dataset is licensed under FRED® Services General License and is allowed to be used none other than for statistical analysis purposes. This dataset has data points starting from 1990 to 2022 for unemployment rates, Civilian Labor Force participation. It is a two-dimensional dataset with timestamps and the respective measures in either case. We understand the effect of the pandemic (COVID-19 cases) on these two measures. It helps in answering question 2.

3. [CDC’s Agency for Toxic Substances and Disease Registry Data](https://www.openintro.org/data/?data=county_complete):
This dataset keeps a track of the social vulnerability of counties given the diseases or abuse of toxic substances. Social Vulnerability Index (SVI) indicates the relative vulnerability of every U.S. Census tract. Census tracts are subdivisions of counties for which the Census collects statistical data. SVI ranks the tracts on 16 social factors, including unemployment, racial and ethnic minority status, and disability. We have the index values for all of these themes.
The National Center for Health Statistics (NCHS), and Centers for Disease Control and Prevention (CDC), conduct statistical and epidemiological activities under the authority granted by the Public Health Service Act. NCHS survey data are protected by Federal confidentiality laws including Section 308(d) Public Health Service Act and the Confidential Information Protection and Statistical Efficiency Act or CIPSEA. These confidentiality laws state the data collected by NCHS may be used only for statistical reporting and analysis. Since it is the annual patterned data we use it to answer our 3rd and 5th question about the state of the socioeconomic variables before the pandemic and after the pandemic. Median household income and Gross Domestic Product, Education, and Poverty Estimates in different groups. The dataset can be found in United States Counties. 

4. [Argonne National Laboratory Data for Different Sector Information](https://anl.app.box.com/s/q0e8ub9jzjyemg0x1y2clt01hkqxpg76):
This dataset contains the indexes for different industrial sectors across the country. We use it to research question 4. Since this dataset is available from January 2020-April 2022. We will be able to study the impact from almost the start of the pandemic. The data is spread out monthly for each of the counties as the index column and different sectors as the subindex. This dataset is again allowed to be used only for Statistical Analysis purposes and is licensed under DEAR 970.5204. The link for the dataset is US Counties Economic Information.


## Issues and Special Considerations / Limitations

The primary reason we use CDC guidelines as the masking policy is that the data obtained from CDC Policy Survellience shows there were no mask mandates established by the state of Arizona in any of the counties, let alone Maricopa County. The initial intuition was to use the voluntary mask data but it would be unfair to generalize the data obtained from a 2-week survey to a very large timeframe. The voluntary masking survey shows us that 73.4% of the people in Arizona always wore masks and 95% of people wore masks more than sometimes. This timeframe (July 2 - July 14) was when CDC had nationwide guidelines for wearing masks. So, technically our assumption is people in the county were following CDC guidelines religiously without a state mandate. Hence, we use CDC guidelines as the basis of the analysis. In all the datasets mentioned above, the datasets are quite clean in general. 

The other concern is understanding the features accurately, which might require researching socioeconomic terminologies in order to avoid drawing incorrect conclusions. Another concern is here, we are directly correlating the variables like economic impact in industrial sectors and the effect of COVID-19, but it's important to note that these variables might be impacted by various other factors like International relations amongst others. For example, the CDC’s Agency for Toxic Substances and Disease Registry Data measure the impacts of drug consumption and diseases on the economic indexes, but we are just correlating the impact with the disease part.

Some of the other limitations would include,  these results and analysis for Maricopa county in Arizona, US. These results might not hold for other counties in the country. When building the model overall community risk we added certain factors and left out some like the Local Government Revenue index as we thought they would be redundant and as they correlated highly with County Economic Index. But we think adding those features might change the predictive power of the model. Also, many times there are factors like state economic indexes which would be impacting the local index of the communities and they might have some contribution in each of the counties. We consider all the counties as independent of each other which might violate the Independence assumption of linear regression. On the other hand, the time-lagged correlation of the industries with COVID-19 cases was done on the basis of their months. We took the sum of the cases, whereas the other value is a percentage change. Although on the outside, this looks correct, a statistically more appropriate way of doing it could be the percentage change in COVID-19 cases against the percentage change in unemployment. The COVID-19 masking data we used could be incorrect as those are the CDC guidelines and not state mandates. On top of it, the masking survey data is sampled from a specific set of people, extrapolating that could be a simplification assumption that might not be right. Another limiting aspect could be that we do not gauge the long-term impact of Social factors like Education as its the limitation of data available at hand.

## Ethical Considerations
We initially proposed trying to build the models that could have been much more complicated than the current ones. But the human-centered approach helped us pick more interpretable approaches as they result in more transparency. The data we used was also about fairness and hence used as many as communities possible over using specific communities or counties when building the overall community risk index model. Also, the design process involves ethical considerations. It uses masked data produced by the people and is free of other demographic biases. For the data leveraged by the above three methods proposed, differential privacy has been used by adding artificial noise, enabling high-quality results without identifying anyone. To further protect people's privacy, it is ensured that the study leverages no personal information or individual search queries. Finally, the proposed solution of the study is highly reproducible. The methodology proposed can be leveraged to fit any data consisting of people's searches by validating and incorporating the assumptions made in regression and correlation analysis.

## Repository Structure
Here are the main folders in the github data-512-project-common-analysis repository:
```bash
│   Final_Project_Notebook.ipynb
│   LICENSE
│   Part_1_CommonAnalysis_RohitLokwani.ipynb
│   README.md
│   requirements.txt
|
├───documentation
│       Part1_Reflection_Statement.pdf
│       Part1_VisualizationExplanation.pdf
│       Part2_DATA512Project_ ExtensionPlan.pdf
│       Part3_ProjectPresentation.pdf
│       Part4_DATA512ProjectReport_RohitLokwani.pdf
│
├───images
│   ├───EDA
│   │       CLF_trends.png
│   │       CLF_Unemployment_boxplot.png
│   │       COVID_19_cases.png
│   │       EconomicIndex_trends.png
│   │       Economic_value.png
│   │       Percent_Employment_trends.png
│   │       Unemployment_trends.png
│   │
│   └───plots
│           Education.png
│           GDP.png
│           Household_income.png
│           part1_visualization.png
│
└───intermediate_data
        civilian_labor_force_population.csv
        County_by_Industry.csv
        COVID_cases_by_month.csv
        Economic_data_maricopa.csv
        Education_Associate.csv
        Education_bachelors.csv
        Education_highschool.csv
        GDP_trends.csv
        household_income.csv
        unemployed_population.csv
```

## Results/Findings
1. Masking Policies vs COVID-19 cases: 
we see that the mask policies were changed during the increase in cases or when they just started to drop. The masking policies did actually help show some difference in daily infection rate reduction with almost a month’s delay. One important thing to note here, is we do not consider hospitalizations, herd immunity, recovery, or other implicit factors in our analysis. One interesting finding is that after vaccines (Late December 2020) were available, the CDC changed to a closed-space masking policy but still saw an increase in cases reason being people traveling across states during Christmas and New Year. But as we see the 4 months following that had stricter masking policies but with more people getting vaccinated the infection rates dropped and masking policies were made less strict. In summary, if we stick to the timeframe of our research question from February 1, 2020, to 1st October 2021, we see that masking had some impact on daily infection rates with a 1-month delay. This delay includes infection, COVID-19 reports, and case count actually fed-to-database delay.

2. Impact of COVID-19 cases on unemployment and Civil Labor Force
We did a direct correlation of COVID-19 cases against the unemployment rate and civilian labor force. But did not find any direct correlation. For a time-lagged correlation, we see some moderate-to-high correlation between unemployment (-0.57) and the civilian labor force (0.67) against COVID-19 cases. Labor force participation is important as it tells you about the employed and unemployed people in the general populace apart from people with privileged jobs. Overall, these findings inform us of the gradual impact of COVID-19 on people’s jobs and willingness to work.

3. Immediate Impact of COVID-19: 
3.1 Education (Percentage of people with degrees)
We use the data from 2008 to 2020 for this analysis. We see that there was no particular change in the increasing trend of the percentage of degrees obtained by the people before the pandemic and at the start of the pandemic. One of the reasons could be that these degrees are mostly more than 1-year degrees and the graduation dates are usually over the summer (June). Hence, assuming COVID-19 started to hit at the start of January, 6 months Is a very short time to gauge any impact, this can be seen as the limitation of the data. But as an immediate impact of COVID-19, there wasn’t a case of people dropping out immediately at the first sight of COVID-19.

3.2 Change in GDP
We see that the slope changes quite a bit from 2019-2020 as compared to the timeline previous to that. This shows that COVID-19 had started impacting the GDP in some manner, at least showing some slowdown in the economy if not showing a downturn.

3.3 Change in median household income 
Household income is used by economists to arrive at conclusions about the economic health of a given county. We do not see any difference in the trends for it. We see that the household income was stable for the most part of 2020. Although, that is surprising because of the shutdowns in the country this value could have changed unless it equally affected the people in the lower part or the higher part of the distribution. 

4. Gradual Impact of COVID-19
In this experiment, we tried collating the industries and understanding how they were affected by the increase or decrease in COVID-19 cases. We saw that they did show some moderate-to-strong lagged cross-correlation with COVID-19 cases. The results are interpreted as Agriculture, Forestry, Fishing, and Hunting had a crosscorrelation of -0.7621 with COVID-19 cases with a lag of 18 months. So if the COVID-19 cases increase by 100% then there would be a 76.21% reduction in employment 18 months down the line. We can interpret the results for other industries similarly. 

5. Overall impact
We find a correlation between the economic index and with value added by the industry. We see value added against the percentage change in unemployment. Both of these experiments show a very strong correlation without lag (0.97 and 0.99) respectively. 

We then predict overall community risk prediction using five indexes and get that these specific indexes show how important they are in predicting the overall community risk. Per unit change, the socioeconomic index showed a change of 0.43 overall community risk index keeping all other variables constant. Similarly, the model’s results can be interpreted for others, the county economic index, minority status/ language index, and housing stability index. There would be certain factors having some sort of correlation with these respective indexes, which is a part of the future part of the analysis. We tried exploring the first two here. We get the mean absolute percentage error of the overall community risk (measured on a scale of 0 to 5) as 0.07% which is fairly accurate.


## Conclusion
We started with a human-centered approach to this project trying to corroborate Dr. Cockerham’s theory of socioeconomic status being the primary indicator of health and impact. We uncovered the socioeconomic impacts in immediate and gradual perspectives at the individual/community level and industry level. All of this was done keeping in mind the guidelines of code reproducibility, transparency, openness, and fairness for any analysis project. 

Some of the interesting findings were: The impact of masking policies on the COVID-19 cases showed some impact with a lag of 1 month in some cases but that does not guarantee that there was any direct impact. Hence, in the absence of state mandates we use CDC mask recommendation guideline dates but do not use masking as the chief basis of this analysis. We do the correlation analysis using COVID-19 cases instead. Given its effectiveness in decreasing infection, public mask-wearing might still be an appropriate policy response to future outbreaks. Overall, the study provides suggestive evidence about the benefits of wearing masks in public during the various stages of the COVID-19 pandemic. The study also highlights the relevance of public mask-wearing for the ongoing pandemic, where the vaccination rate is precarious, and access to vaccines is still limited in many counties. 

On the economic front, Unemployment and Civil Labor Force participation showed a time-lagged cross-correlation of 0.57 and 0.67 at 21 and 22 months respectively. We did not see any immediate impact of COVID-19 on socioeconomic factors like Median Household Income and Education. On the other hand, the GDP suggested a relative economic slowdown. The gradual impact showed Agriculture and Fisheries industry having a strong negative correlation(-0.71) with COVID-19 at a lag of 18 months amongst other industries. We see that the overall economic index, value added by the sector, and the percentage change in  employment have a very strong correlation (>0.97). We also predict the overall community risk index with a mean absolute percentage error of 0.07%. We identify the important factors that are most important in predicting that which include the Socioeconomic Index and County Economic Index followed by the Minority Status/Language Index. Overall, these findings would help us be better prepared for determining the communities at risk and the most vulnerable industries in the future.

    
### Languages used: Python
