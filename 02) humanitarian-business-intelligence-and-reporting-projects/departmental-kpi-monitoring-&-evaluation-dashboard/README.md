## Department of Operational Governance KPI Monitoring & Evaluation Dashboard
A five-page integrated Power BI reporting system consisting of four divisional pages and a consolidated summary page for an overall executive summary and overview.

## Project Highlights:
• Transformed an Excel-based data model into an integrated reporting system on Power BI. 
• Designed a framework for each divisional page containing a KPI table (KPI baseline and value), 
a column chart for KPI status percentage, KPI count card, and KPI categories and year slicers.
• Developed a four-level KPI performance status classification (Exceed, Meet, Substantially Meet, Does Not Meet) 
to standardize a structured framework that translates qualitative data into quantitative measurements.

## Development Process and Tech Stack
Excel Spreadsheet -> Power Query -> Data Modelling -> Power BI -> Reporting Framework -> UI/UX Design -> DAX Measures

## Queries and DAX Measures
DAX Measures used for "DOG KPIs Summary Page" to translate [KPI Status] into percentages and  calculate the average KPI scores based on selected category slicers and/or year slicers.

AVG KPI Status Score = SWITCH(Append1[KPI Status],"Exceed",100,"Meet",75,"Substantially Meet",50,"Does Not Meet",0,BLANK())
AVG KPI Status Score (DDOG) = CALCULATE(AVERAGE(Append1[AVG KPI Status Score]), Append1[Division]="DDOG Office")
AVG KPI Status Score (SD) = CALCULATE(AVERAGE(Append1[AVG KPI Status Score]),Append1[Division]="Service Delivery")
AVG KPI Status Score (M&E) = CALCULATE(AVERAGE(Append1[AVG KPI Status Score]),Append1[Division]= "Monitoring & Evaluation")
AVG KPI Status Score (Audit) = CALCULATE(AVERAGE(Append1[AVG KPI Status Score]),'Audit (2)'[Division] = "Audit")
