# DSC563 - Visualization Work for Module 5

**Overview**:
- Author: Jeffrey Sirard (MBA student, class of 2027)
- Purpose: For Data Visualization (DSC-563)
- Instructor: Professor Michael McCarthy
- Structure: This README.md serves as a guide to this GitHub repository. The contents include evidence of coursework and context for the final Module 5 presentation in VoiceThread.
- Questions: Email jasirard@utica.edu.

**Background**:
- The purpose of this data visualization is to demonstrate skills learned in DSC-563 Module 5; The audience and questions are hypothetical.
- Learning Objective: Coordinated visual analysis.
- Intended audience: CDC’s High Obesity Program (HOP) leadership team.
- Question: Which counties should be prioritized for obesity intervention funding?

**Relevant Links**:
- Collab URL: 
- GitHub Repository URL: https://github.com/jasirard/DSC563_M05
- GitHub Profile URL: https://github.com/jasirard
- Tableau Evidence URL: 

**Assessment Guidance**:

   - GitHub Repository (Public): https://github.com/jasirard/DSC563_M05
   - GitHub Profile: https://github.com/jasirard
   - All project files are located in the repository; Click to open each file.
   - Evidence (screenshots, before/after charts, etc.) are contained within the Tableau packaged workbook and PowerPoint presentation (see File Directory).

**File Directory**:
- **sirard_jeffrey_M5_workbook.ipynb**: Google Colab workbook for Module 5 assignment practice using a simulated dataset.
- **workshop_sessions.csv**: Simulated dataset from Google Colab workbook; Seed "23" was used to generate.
- **sirard_jeffrey_M5_Practice.twb**: Tableau practice workbook for Module 5 using simulated dataset.
- **PLACES_Local_Data_for_Better_Health,_County_Data,_2025_release_20261105.zip**: Compressed CDC "PLACES" dataset used for Module 5 analysis and Tableau visualization work.
- **sirard_jeffrey_m5_Tableau_V1.twbx**: Tableau packaged workbook used for CDC dataset analysis; Includes evidence.
- **DSC 563 Module 5 Presentation.pptx**: PowerPoint presentation for DSC 563 Module 5 VoiceThread; Includes evidence.
- **README.md**: This document!

**Dataset Summary** (CDC PLACES 2023):

_i. Basic Information_:
- Title: CDC PLACES 2023 County Data
- Columns: 22 
- Rows: 229,298 
- Units: Percentage (%)
  
_ii. Assessment/Handling of Null Values_: 
- LocationName is NULL on the national "US" summary row (LocationID = "59"). 
- Data_Value_Footnote_Symbol and Data_Value_Footnote are NULL on standard county rows and populated only where estimates are suppressed or based on partial state reporting 
- All calculated fields exclude missing values using NOT ISNULL([Data_Value]) and NOT ISNULL([LocationID]).
  
_iii. Data Preparation, Calculations, and Filters_:
- Excluded National Summary Row ([StateAbbr] != "US"): Prevents the U.S. total row from double-counting population or skewing county/state averages. 
- Isolated Prevalence Type ([DataValueTypeID] = "CrdPrv"): Separates crude prevalence from age-adjusted prevalence (AgeAdjPrv) so the two are never averaged together. 
- Deduplicated Population Denominator: Weighted rates multiply [Data_Value] * [TotalPop18plus] strictly within a single MeasureId and DataValueTypeID so TotalPop18plus is counted once per county rather than ~70+ times (i.e., dataset is long-form structure) 
- Population Classification: Categorized counties by TotalPopulation into Rural (<50k), Suburban (50k–250k), and Urban (>250k)
- Derived Measure: Calculated Estimated Obese Adults for population impact scatterplot using: Adult Population × (Obesity Prevalence ÷ 100).
  
_iv. Data Source and Reuse Information_:
   - Data source: Centers for Disease Control and Prevention (CDC). (2026). PLACES: Local Data for Better Health, County Data 2023 release [Dataset]. U.S. Department of Health and Human Services.
   - URL: https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-County-Data-20/h3ej-a9ec/about_data
   - Status: Last updated September 2026.
   - Reuse: Free public-domain access; Required attribution (credit CDC as the free source); No endorsement or alteration.
   - Note: Due to this dataset being model-based adult estimates, the CDC recommends against using this data to evaluate policies or programs and suggests avoiding time-series comparisons or rankings. In the case of this repository, the dataset is being used for educational purposes only.
