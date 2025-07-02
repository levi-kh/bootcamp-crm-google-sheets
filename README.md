# CRM Automation Project – Bootcamp Lead Management (Google Sheets)

This is a project I built to learn Google Sheets and Excel through a project-based approach. It simulates a CRM system for a fictional online academy offering bootcamp programs to people looking to switch careers into the data field (Data Analyst).


## Context

•	The company runs a bootcamp and collects lead information through a form on their website.

•	Whenever a user submits their info, it automatically flows into a sheet called bootcamp_data. This is the raw data sheet and shouldn’t be edited directly.

•	Leads contain info like:

   - Timestamp
  
   - Full Name

   - Phone Number
  
   - Occupation
  
   - Career Change Intention (“No, I want to learn data analysis to support my current job” or “Yes, interested in a Data Analyst position”)
  
   - Type of Ticket (“Free Intro Class” or “Full Bootcamp Enrollment”)

## How the System Works
[Admin] CRM Lead Tracker (Main file)

•	bootcamp_data: Raw data from form submissions (view-only).

•	source: Copies all data from bootcamp_data, and adds two columns:

  - Sales ID
  - Sales Name
  - These are auto-generated using a round-robin lead assignment formula using ARRAYFORMULA and MOD(ROW()) logic.
  - The data from this sheet will automatically update when bootcamp_data has new data.
  
•	sales_team: Contains the list of salespeople and their IDs. Currently includes:

  -	Joe Martin (1)

  - Michael Wilson (2)
    
  - Elizabeth Johnson (3)
    
•	s_joe_martin, s_michael_wilson, s_elizabeth_johnson: Sheets that show leads for each salesperson, automatically imported from their individual files.

•	tables_admin: Stores summary tables for reporting:

  -	Lead status counts for all sales
    
  - Monthly enrollments (2024 vs 2025)
    
  -	Total enrollments per salesperson
    
•	dashboard_admin: Contains pie charts, line graphs, and other visuals built from tables_admin.

[Sales]  – CRM Tracker (1 file per salesperson)

Each salesperson gets their own file where they can: 

  - View their leads in the my_leads sheet (automatically imported from admin’s source sheet based on their assigned ID).
    
  - Update the status of each lead via dropdown: Contacted, In Progress, Enrolled, Spam, or No Response.
    
  - View filtered sheets for each tag (leads_enrolled, leads_contacted,…)
    
  - graph_me sheet contains: A pie chart showing overall lead status distribution, a line chart comparing enrollments month-by-month in 2024 vs 2025
    
Note: In real life, sales shouldn’t have access to the admin file. Permissions would need to be adjusted to protect privacy and ensure data integrity.

## Why This Project?

I built this project to learn formulas, automation, and dashboards in Google Sheets, simulate a realistic business process, practice structuring multi-file, real-world spreadsheet systems.

It helps reinforce: Dynamic formulas (ARRAYFORMULA, MOD, COUNTIFS, VLOOKUP), Data validation & dropdowns, Filtering with FILTER(), Charting and dashboard design, File permissions and workflow logic

## Timeline Assumptions

•	The bootcamp started collecting leads from January 2024

•	Current simulated date is June 2025

### Let me know if you’d like to collaborate!
