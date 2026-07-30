## Annual Misconduct Tracking Dashboard
This dashboard is the division's first reporting system. It provides a standardized framework for managing annual data and statistics through an interactive Power BI dashboard. The purpose of this dashboard is to provide an executive-level overview of the activities and achievements of the Investigations Division and support evidence-based decision-making.

## Project Highlights
Replaced manual work that relied on Excel spreadsheets with a live, interactive dashboard.
Overview of the complete complaint lifecycle (number of complaints, allegations, intake processing time,
investigated case closure time, investigated cases outcome, and backlog monitoring.

Designed interactive analytical dashboards with dynamic filtering by year, intake decision, allegation category, field office, and investigation outcomes.
Integrated geographical and operational reporting through field office distribution analysis, allegation classifications, and performance trend visualizations.
Balanced transparency with confidentiality by designing a reporting framework that supports operational oversight while protecting sensitive case information.
Created a scalable reporting architecture to support evidence-based decision-making, performance monitoring, and future reporting automation.

*This is a sanitized version of the original dashboard for public portfolio publication.


## Tech Stack
Power BI | Power Query | DAX | KPI Reporting | Data Visualization

## DAX Measures
Number of Complaints = COUNT('All Data (2026+Past Cases) (2)'[Primary Allegation])
Total Number of Allegations = COUNTA('All Data (2026+Past Cases) (2)'[Primary Allegation]) + COUNTA('All Data (2026+Past Cases) (2)'[Secondary Allegation])


