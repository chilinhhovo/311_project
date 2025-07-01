# 311_project

Google Sheet: https://docs.google.com/spreadsheets/d/1yW8JHae1dCQA4LnUtDtUxLWFNXSIf7DNthM75sbaDWI/edit?usp=sharing

Goal: Identify which elevator complaints occurred in rent-stabilized buildings using NYC’s official rent-stabilized building lists
## source data: 
Rent-Stabilized List: Parsed PDF files (2023) from https://rentguidelinesboard.cityofnewyork.us/resources/rent-stabilized-building-lists/
Complaint Data: 311 elevator complaints with incident addresses https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/about_data 

## Cleaning & Parsing: 
Converted rent-stabilized PDFs using pdfplumber
Extracted street address ranges (e.g. “100 TO 110 MAIN ST”) and normalized them
Cleaned 311 addresses into house number + street

## Matching Logic: 
Matched complaints to buildings by:
Same street name
House number falling within building's range

## Challenges
PDF parsing was messy and required custom logic
Address inconsistencies (spelling, formatting) made exact matches hard
311 complaints had many repeated and strange logs
Manual spot checks revealed gaps, NYC doesn’t offer an easily mergeable rent-stabilization dataset
 
