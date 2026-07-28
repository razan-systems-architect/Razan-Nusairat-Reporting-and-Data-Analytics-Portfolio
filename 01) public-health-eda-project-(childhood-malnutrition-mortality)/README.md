# Childhood Malnutrition-Mortality Burden Project (Exploratory Data Analysis)

## Project Highlights
• Initially a Predictive Modelling System (Prediction of Childhood Mortality Risk)
• Evolved into Exploratory Data Analysis through data exploration and analysis.
• Integrated data from WHO + UNICEF + World Bank datasets.
• Developed into an evidence-based public health analysis integrated with an interactive 
  Power BI reporting system.

## Tech Stack
Excel, Power Query, BigQuery, SQL, DirectQuery, DAX Measures, Power BI 

## Queries and DAX Measures
## SQL Query
SELECT 
  who_mortality_data.`Year`,
  who_mortality_data.`Region Name`,
  who_mortality_data.`Country Name`, 
  who_mortality_data.`World Bank Income Classification`,
  who_mortality_data.`Total Number of Deaths`,
  who_mortality_data.`Number of Deaths Per 100000 of Population`, 
  unicef_nutrition_data.`Average Wasting`,  
  unicef_nutrition_data.`Average Stunting`
FROM `predictive-nutrition-system.who_unicef_health_and_nutrition_datasets.who_mortality_dataset` AS who_mortality_data
LEFT JOIN `predictive-nutrition-system.who_unicef_health_and_nutrition_datasets.unicef_who_worldbank_malnutrition_data` AS unicef_nutrition_data
  ON unicef_nutrition_data.`ISO Code` = who_mortality_data.`Country Code` 
  AND who_mortality_data.`Year` = unicef_nutrition_data.`Year`
  WHERE who_mortality_data.`World Bank Income Classification` IN ('Lower middle income', 'Upper middle income');

## DAX Measures
Number of Rows with both wasting + stunting values = CALCULATE(COUNTROWS(Malnutrition_Mortality_Predictive_Model), FILTER (Malnutrition_Mortality_Predictive_Model, NOT(ISBLANK(Malnutrition_Mortality_Predictive_Model[Average Wasting Value]))))

Countries with the Full Dataset = CALCULATE([Total Number of Countries],Malnutrition_Mortality_Predictive_Model[Average Stunting Value] <> BLANK(),Malnutrition_Mortality_Predictive_Model[Average Wasting Value] <> BLANK())

Number of Deaths for Countries with the Full Dataset = CALCULATE([Total Number of Deaths],FILTER(Malnutrition_Mortality_Predictive_Model, NOT(ISBLANK(Malnutrition_Mortality_Predictive_Model[Average Wasting Value]))))


