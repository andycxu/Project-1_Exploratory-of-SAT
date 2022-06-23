General Assembly Project - 1
Date: Apr. 4, 2022
Author: Chenhao (Andy) Xu

1. Problem Statement
The new format for the SAT was released in March 2016. Since then, levels of participation in multiple states have changed. 
The project aims to provide necessary information for high school students in US mainland to understand the SAT trends including scores and participation rates in the year of 2017 through 2019. In order to let high school students decide their goals for college, the study also discover the relationship of SAT entry score versus universities. Therefore, high school students can easily set up goals for their ideal colleges/universities. 

2. Method of Study
Four data files were used in this project, including sat_2017.csv, sat_2018.csv, sat_2019.csv, and sat_act_by_college.csv. The methods of study followed the step of data cleaning, data exploratory, and data visualization. Data of SAT score by states from 2017 to 2019 helped the understanding of SAT score and participation rate trends after the new sat format introduced. future college students would understand their competitors status in the country or their local region. The college data like accept rate and admission SAT score provided information for future college students to setup their goal college/university and ideal SAT score they need to achieve. 

2.1. Data Cleaning
Four data files were cleaned and details were discuessed in the following. After the data cleaning, cleaned files were saved into 5 new names, sat_17_19.csv, sat_2017_f.csv, sat_2018_f.csv, sat_2019_f.csv, and college.csv.

2.1.1. Data Cleaning of sat scores from 2017 through 2019
During the data cleaning step, raw data was checked for null value and accurateness. For example, data files of sat from 2017 through 2019 should not contain any score under 200 since either reading and writing or math of SAT has the lowest score of 200. If null value or inaccuratness of data happened, specific rows would be dropped due to the information incorrectness. Participation rate shoould be in the range of 0% to 100%. Secondly, useful rows and columns were filtered. Since the project only focus on US mainland, 48 states in mainland and District of Columbia were the targeting study object. Certain rows that includes other locations were dropped due to not part of study object. Since the new format of SAT was introduced in 2016. State government also had different policy of either requiring or not requiring the SAT. By using online source (https://testive.com/state-sat-act/), states were categorized in two groups, either SAT is required or not required, which could help the analysis of SAT scores and participation rate. In addition, in order to let high school students understand more their situations, these 48 states and District of Columbia were assigned into four major geographic regions, Northeast, South, Midwest, and West. The project would provide detailed information of sat score and participation rate for students in different regions and let them know their place of the whole country. Lastly, the cleaning step transferred certain data type from string to float. For example, the participation rate was stored as string and it turned to be numerics for study comparisons. 

2.1.2. Data Cleaning of College Data File
Similar to the previous data cleaning step, the sat_act_by_college.csv file was also followed the same procedure. Firstly, null value and data accurateness was checked. Number of applicants shouldn't be negative number. The accept rate should be in the range of 0% to 100%. SAT scores should be in the range of 400 to 1600. If any row did not meet the requirement, these rows were removed. Incorrect data would harm the data analysis and its accurateness. Secondly, colleges and universities were categorized into three groups by accept rate. College and universities were rated as 'top' if the accept rate was under 10%. College and universities were rated as 'good' if the accept rate was between 10% and 50%. College and universities were rated as 'ok' if the accept rate was more than 50%. Although this method may not be fair since the number of admission students were unknown, it's the best way to categorize colleges and universities based on the available information provided. Tirdly, numeric data stored as string was transferred into int or float data type for ease of analysis. For example, the SAT score was provided in a format of range. In this study, only the lower bound score (the entry score) was considered to study since this project only wants to help students to be admited by the college or university. Lastly, the data from college was for the year of 2021, which does not met the year of SAT scores by states. The project assumed the admission SAT scores of college and unviersities remained in similar through recent years. 

2.2. Data Dictionary
| Feature | Type | Dataset | Description |
|---------|------|---------|-------------|
| State   | obejct | sat_2017_f | States in US mainland | 
| sat_score | int | sat_2017_f | The 25 percentile SAT score of the states in US mailand |
| region | object | sat_2017_f | the region of the states |
| sat_required | object | sat_2017_f | whether the state requires SAT |
| participation | float | sat_2017_f | the participation rate of each state |
| State   | obejct | sat_2018_f | States in US mainland | 
| sat_score | int | sat_2018_f | The 25 percentile SAT score of the states in US mailand |
| region | object | sat_2018_f | the region of the states |
| sat_required | object | sat_2018_f | whether the state requires SAT |
| participation | float | sat_2018_f | the participation rate of each state |
| State   | obejct | sat_2019_f | States in US mainland | 
| sat_score | int | sat_2019_f | The 25 percentile SAT score of the states in US mailand |
| region | object | sat_2019_f | the region of the states |
| sat_required | object | sat_2019_f | whether the state requires SAT |
| participation | float | sat_2019_f | the participation rate of each state |
| State   | obejct | sat_17_19 | States in US mainland | 
| sat_score | int | sat_17_19 | The 25 percentile SAT score of the states in US mailand |
| region | object | ssat_17_19 | the region of the states |
| sat_required | object | sat_17_19 | whether the state requires SAT |
| participation | float | sat_17_19 | the participation rate of each state |
| year | int | sat_17_19 | the year of the data |
| school | object | college | college/univesity names |
| applicant_number | int | college | # of appliant for year 2021 |
| sat_low | int | college | the 25 percentile of SAT score |
| sat_high | float | college | the 75 percentile of SAT score |
| accept_rate | float | college | accept rate of colleges |
| rate | object | college | college rate, top, good, ok |

2.3. Data Exploratory
The data exploratory were the preparation of data visualization. Based on the project goal, eight types of exploratories were made. 
#1. The SAT score comparions of states requiring SAT test and states not requiring SAT test over the US mainland. It provided the information of SAT score trend in states either require or not require SAT test. The SAT scores were calculated as mean of each type of states. 
#2. The SAT participation rate comparions of states requiring SAT test and states not requiring SAT test over the US mainland. It provided the information of SAT particiaption trend in states either require or not require SAT test. The participation rate was calculated as mean value of each type of states. 
#3 - #5. The SAT score comparisons by geographic regions in US mainland from 2017 thorugh 2019. The SAT scores for each regions were calculated as the average score. This specific exploratories can provide information for high school students to know their position in the country and their region. Then, student can decide how much effort should put on the SAT test. 
#6. The entry SAT scores of colleges and unverisities rated in top, good, and ok. The SAT scores were calculated as mean value of each categories. It briefly showed the minimum SAT scores required for each category. 
#7. The scatter figures of number of appliants and accept rate studied if there's any relationship between these two parameters. By calculating the correlation, the correlation score was -0.3, which means there's no close relations between the number of applicants and accept rates.
#8. The scatter figures of lower bound of SAT score and the accept rate studied if there's any relationship between these two parameters. By calculating the correlation, the correlation score was -0.8, which means there are some relations between the SAT entry score and accept rates.

2.4. Data Visualization
The data visualization turned the data exploratory information into figures. figures #1 to #6 were bar figures and figure #7 and #8 were scatter figures. Bar figures clearly showed audience about SAT scores and SAT participation rates over the US mainlan and in geographic regions. Also, bar figures showed college or university minimum admission requirement on SAT scores. The scatter figures studied the relationships between x-value and y-value. The distribution of dots on figures directly provide information fro audience about whether two parameters are related or not. 

3. Conclusion and Recommendation

3.1. Conclusion
#1. The average SAT scores in the states don't require SAT test are higher than the states do require SAT test. This may be because only good students in states don't require SAT test participated SAT exam. 
#2. The average SAT participation rate in the states do require SAT test are higher than the states don't require SAT test. The result was reasonable. 
#3. The average participation rate were slowly increase over all the states in US mainland. 
#4. The average SAT scores from 2017 through 2019 tended to decrease. This may be because the participation rate increased. 
#5. The average SAT scores by regions do not have significant trend. In those states do not require SAT test, the midwest had the highest SAT score overall. in those states do require SAT test, four regions were relativly close to each other. The south region was the leader based on the data from 2017 to 2019. 
#6. The entry level SAT score of college and unversities rated in top, good, and ok followed the path of ratings. The top universities had the highest SAT entry score. 
#7. Due to the unknown of admission number, the ralationships of number of appliants and accept rate of all colleges and universities seems not close correlated. But the distribution showed colleges/universities with accept rate over 50% mostly had less than 10,0000 appliants. 
#8. The relationship of SAT entry score and accept rate were closely related, which tells schools with high requirement of SAT usually had lower accept rate. 

3.2. Recomandation
#1. Although SAT may not required by all universities, a good SAT score may be a good supporter when applying top universities. High school students who aim to apply top universities would better achieve a high SAT scores. 
#2. SAT participation rate was growing which indicated more students realized the importance of SAT and willing to take SAT in order to apply their dream colleges. SAT test is encouraged to be taken by high school students. 
#3. If students want to apply local colleges, the information of SAT score rankings by regions and the scatter graph of accept rate versus number of appliants or SAT entry score could provide recommandations for them based on students' SAT ranking in the region and the accept rate of colleges. 