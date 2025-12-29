# Voter Registration Matching
# Overview
This project matches Pennsylvania voter registration records to Philadelphia real estate ownership data to help identify owner-occupied properties. The City of Philadelphia’s Department of Revenue does not formally store owner-occupancy status for parcels, yet this information is a key eligibility factor for several Real Estate Tax Assistance programs.
This script leverages voter registration data as a proxy to infer owner occupancy by performing name and address matching between voter records and property ownership records.
# Objectives
- Ingest and clean voter registration data for Philadelphia
- Standardize and parse addresses using Passyunk
- Query property ownership data from SQL Server
- Perform fuzzy matching on names and addresses
- Identify likely owner-occupied parcels
- Export a finalized matching dataset for downstream use

# Data Sources
1. **Voter Registration Data**
    - Source: Pennsylvania Department of State

2. **Property Ownership Data**
    - Source: City of Philadelphia internal databases (e.g., REVALI)
    - Accessed via SQL Server using pyodbc 

# Dependencies

This project requires the following Python packages:
```
pandas
numpy
pyodbc
sqlalchemy
passyunk
python-Levenshtein
re
glob
```
*Note: re and glob are part of the standard python library.* 

# Configuration
At the top of the notebook, set the following variables before running:
- yearmn = 'YYYYMM'
- load_date = 'MM/DD/YYYY'

These values are used for versioning outputs, tracking data refresh dates, and naming exported files.

# Maintainer
Julia Flanagan
Data Analyst
City of Philadelphia – Department of Revenue
