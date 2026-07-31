## Annual Misconduct Tracking Dashboard
The Annual Misconduct Tracking Dashboard is the division's first live Power BI reporting system. It provides a standardized framework for managing annual operational statistics through an interactive Power BI dashboard. The purpose of this dashboard is to provide an executive-level overview of the activities and achievements of the Investigations Division and support evidence-based decision-making.

*This is a sanitized version of the original dashboard; confidential information has been removed and/or anonymised for portfolio publication.

## Project Highlights
• Replaced manual statistics work that relied on Excel spreadsheets with a live, interactive reporting system.

• Designed an automated reporting structure that reduced data extraction and reporting time by more than 80%  

• Designed while maintaining confidentiality through controlled visualization of sensitive operational data.

• Provides a full overview of the complete complaint lifecycle (number of complaints, allegations, intake processing time,
investigation closure time, investigation outcomes, allegation distribution by location, and backlog monitoring.

## Development Process and Tech Stack
Excel sheet restructuring -> Power Query -> Reporting Framework Design + Data Visualization + KPI Reporting -> Power BI -> DAX Measures

## DAX Measures
Number of Complaints = COUNT('All Data (2026+Past Cases) (2)'[Primary Allegation])

Total Number of Allegations = COUNTA('All Data (2026+Past Cases) (2)'[Primary Allegation]) + COUNTA('All Data (2026+Past Cases) (2)'[Secondary Allegation])

DAX measure used to identify the most frequent allegation category for executive reporting.


Top Category of Allegations = MAXX(TOPN(1, VALUES('All Data (2026+Past Cases) (2)'[Primary Allegation]),
[# of Complaints],DESC),'All Data (2026+Past Cases) (2)'[Primary Allegation])
