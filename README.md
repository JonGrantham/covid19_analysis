# Data Description

## Nexoid COVID-19 Survival Calculator Vulnerability Data

[Nexoid](https://www.covid19survivalcalculator.com/) is a software company based in London. It has a data research team that uses collected user data to calculate the risk index of COVID-19 to people with different vulnerabilities.

Data is gathered from the [survival calculator](https://www.covid19survivalcalculator.com/en/calculator), which is a survey that asks questions on biometrics, behaviors, living environments, medical records, etc. Nexoid then analyzes it and calculates the infection rate and mortality rate per different factors, based on over 820,000 entries of submitted data. Read the [methodology](https://www.covid19survivalcalculator.com/en/research).

## Dataset

The survival calculator provides a complete dataset of all responses submitted. It contains information such as the respondents'

- geographical information
- behavior
- segmentation
- health conditions
- medications
- risk values

For complete details of all questions asked, visit the [COVID-19 Survival Calculator](https://www.covid19survivalcalculator.com/en/calculator).

Data is updated periodically, and is available back till _March 24th, 2020_.

## Accessing Data 

You can download all responses at the survival calculator's [website](https://www.covid19survivalcalculator.com/en/download). (~180 MB total)

Metadata describing the response analysis are [available](https://www.covid19survivalcalculator.com/en/download) as separate files, listed together with the master dataset.

Last updated _September 25th, 2020_.

## Structure

All survey responses are recorded in `master_dataset.csv`.

### Field Description

| Field | Description | Type | Example |
|-|-|-|-|
| `survey_date` | Date on which the data was collected, in the format `M/D/YYYY` | string | 3/24/2020 |
| `region` | [2-letter continent code](https://datahub.io/JohnSnowLabs/country-and-continent-codes-list) in which the data was collected (based on IP address). Possible values are: <ul><li>`AF` for Africa</li><li>`AN` for Antarctica</li><li>`AS` for Asia</li><li>`EU` for Europe</li><li>`NA` for North America</li><li>`OC` for Oceania</li><li>`SA` for South and Central America</li></ul> | string | NA |
| `country` | [2-letter country code](https://www.iban.com/country-codes) representing the country in which the data was collected (based on IP address) | string | US |
| `ip_latitude` | Latitude associated with the IP address of submission | string | 38.5415 |
| `ip_longitude` | Longitude associated with the IP address of submission | string | -121.4968 |
| `ip_accuracy` | Accuracy of the geolocation associated with the IP address of submission, in terms of the maximum distance (in km) of error  | integer | 5 |
| `sex` | Sex of the respondent. Possible values are: `male` and `female` | string | female |
| `age` | Age range of the respondent, in intervals of 10 years | string | 40_50 |
| `height` | Height of the respondent, in cm | integer | 170 |
| `weight` | Weight of the respondent, in kg | integer | 102 |
| `bmi` | [Body mass index](https://en.wikipedia.org/wiki/Body_mass_index) of the respondent | float | 35.2 |
| `blood_type` | Blood type of the respondent. Possible values are: <ul><li>`ap` for A+</li><li>`an` for A-</li><li>`bp` for B+</li><li>`bn` for B-</li><li>`abp` for AB+</li><li>`abn` for AB-</li><li>`op` for O+</li><li>`on` for O-</li><li>`unknown`</li></ul> | string | bp |
| `insurance` | Does the respondent have private health insurance? Possible values are: `yes` and `no` | string | yes |
| `income` | Income level of the respondent. Possible values are: <ul><li>`high`</li><li>`med`</li><li>`low`</li><li>`blank` for respondent on social welfare/government support</li></ul> | string | high |
| `race` | Race of the respondent. Possible values are: <ul><li>`white`</li><li>`mixed`</li><li>`asian`</li><li>`black`</li><li>`hispanic`</li><li>`other`</li></ul> | string | white |
| `immigrant` | Is the respondent a native or an immigrant to the country he/she is in? Possible values are `native` and `immigrant`. | string | native |
| `smoking` | Does the respondent smoke or vape? Possible values are: <ul><li>`never` for never smoked or vaped</li><li>`vape` for vaping or using e-cigarettes</li><li>`yeslight` for light smoking (1-5 per day)</li><li>`yesmedium` for medium smoking (6-20 per day)</li><li>`yesheavy` for heavy smoking (>20 per day)</li><li>`quit0` for recently quit</li><li>`quit5` for quit >5 years ago</li><li>`quit10` for quit >10 years ago</li></ul> | string | quit10 |
| `alcohol` | Number of the days the respondent has consumed **alcohol** over the past 14 days. Values range from `0` to `14`.<br><br>`-1` is reserved for respondents who has never drunk alcohol. | integer | 4 |
| `cannabis` | Number of the days the respondent has consumed **cannabis (marijuana)** over the past 28 days. Values range from `0` to `28`.<br><br>`-1` is reserved for respondents who has never consumed cannabis. | integer | 6 |
| `amphetamines` | Number of the days the respondent has consumed **amphetamines (ice, speed)** over the past 28 days. Values range from `0` to `28`.<br><br>`-1` is reserved for respondents who has never consumed amphetamines. | integer | -1 |
| `cocaine` | Number of the days the respondent has consumed **cocaine** over the past 28 days. Values range from `0` to `28`.<br><br>`-1` is reserved for respondents who has never consumed cocaine. | integer | -1 |
| `lsd` | Number of the days the respondent has consumed **LSD (acid)** over the past 28 days. Values range from `0` to `28`.<br><br>`-1` is reserved for respondents who has never consumed LSD. | integer | -1 |
| `mdma` | Number of the days the respondent has consumed **MDMA (ecstacy)** over the past 28 days. Values range from `0` to `28`.<br><br>`-1` is reserved for respondents who has never consumed MDMA. | integer | -1 |
| `contacts_count` | Number of people the respondent was in close contact with over the past week. Values range from `0` to `20`.<br><br>`21` is reserved for >20 contacts. | integer | 21 |
| `house_count` | How many people you live with other than you | 0-21 people |
| `public_transport_count` | How many times do you catch public transport a week | "0-15 (0 none | 15 = 15 or more)" |
| `working` | Do you work | STRING |
| `worried` | How worried are you about covid 1-5 | 1 not worried 5 very worried |
| `rate_reducing_risk_single` | Opinion do you think you are at risk of infection | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_risk_single_social_distancing` | Opinion do you think social distances will reduce risk of infection | -2 disapprove` +2 approve 0 nutral |
| `rate_reducing_risk_single_washing_hands` | Opinion do you think washing hands will reduce risk of infection | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_risk_house` | Opinion  of someone in house getting infected | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_risk_house_social_distancing` | Opinion does social distancing reducing risk of infection in your house | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_risk_house_washing_hands` | Opinion does washing hands reduce risk of infection in your house | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_risk_house_sanitizer` | Opinion does sanitizer reduce risk of infection in your house | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_mask` | Do you think wearing a mask will reduce the risk of catching covid | 1 not at all 5 will definatly reduce risk |
| `rate_reducing_mask_type` | What type of mark do you use | STRING |
| `rate_reducing_government_action` | Do you approve of government poliices | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_government_control` | Do you approve of government controls | -2 disapprove +2 approve 0 nutral |
| `rate_reducing_government_spend` | Do you approve of government spending  | -2 disapprove +2 approve 0 nutral |
| `covid19_positive` | Are you or have you been covid positive  | "1 yes | 0 no" |
| `covid19_symptoms` | Have you had covid symptoms | "1 yes | 0 no" |
| `covid19_contact` | Have you been in contact with someone who was confirmed covid positive | "1 yes | 0 no" |
| `asthma` | Do you have asthma | "1 yes | 0 no" |
| `kidney_disease` | Do you have kidney disease | "1 yes | 0 no" |
| `liver_disease` | Do you have liver disease | "1 yes | 0 no" |
| `compromised_immune` | Do you have compromised immune | "1 yes | 0 no" |
| `heart_disease` | Do you have heart disease | "1 yes | 0 no" |
| `lung_disease` | Do you have lung disease | "1 yes | 0 no" |
| `diabetes` | Do you have diabetes | "1 yes | 0 no" |
| `hiv_positive` | Do you have hiv | "1 yes | 0 no" |
| `hypertension` | Do you have hypertension | "1 yes | 0 no" |
| `other_chronic` | Do you have other chronic contidtions | "1 yes | 0 no" |
| `nursing_home` | are you in a nursing home | "1 yes | 0 no" |
| `health_worker` | Are you a health worker | "1 yes | 0 no" |
| `prescription_medication` | List of prescription medication | comma seperated list |
| `opinion_infection` | Self rated risk of infection 0 - 100% | 5 - 95 |
| `opinion_mortality` | Do you have opinion_mortality | 5 - 95 |
| `risk_infection` | Nexoid calcuated risk of infection | 5 - 100 % |
| `risk_mortality` | Nexoid caculated risk of mortality | 0.05 - 75% |


**Note**: Fields may be empty.

## Attribution

This dataset is under the [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license. You are free to use it for personal, educational, research, and commercial use provided you attribute the dataset to **Nexoid**.
