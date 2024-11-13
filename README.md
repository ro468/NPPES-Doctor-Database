# US Database Doctor Analysis

## Goal
This project conducts an in-depth analysis of healthcare provider data from CMS NPI files to uncover trends in practice areas, credential types, and deactivation patterns. Through this analysis, we gain insights into the distribution and classification of healthcare providers, presented via visualizations such as pie charts and bar charts.

## Data Source
The dataset is sourced from the CMS National Plan and Provider Enumeration System (NPPES), specifically from NPI Files:
- **Monthly Full Replacement Files**: Complete NPI records.
- **Deactivation Files**: Records of deactivated NPIs, often due to job transitions, retirement, or death. (`NPPES Deactivated NPI Report 20241014.xlsx`)

## Dataset Overview
The primary file (`npidata_pfile_20050523-20241013.csv`) is approximately 10 GB in size and contains:
- **Rows**: 8,576,349 individual provider records
- **Columns**: 330 attributes covering a range of provider details

### Data Preparation and Cleaning
1. **Credential Standardization**: Removed punctuation from `Provider Credential Text` for consistent credential analysis (e.g., "M.D." to "MD").
2. **Deactivation Data Merging**:
   - Renamed ambiguous columns for clarity.
   - Merged deactivated NPI data with active records to separate active providers from deactivated ones.

### Analysis Steps
1. **Top 10 Credential Types**:
   - Identified the most common credentials, with "MD" having the highest frequency, followed by "DDS" and "DO".

2. **Deactivated Data Separation**:
   - Filtered out deactivated NPIs to retain only active providers.
   - Resulted in two datasets:
     - **Matched Data**: 289,373 rows (deactivated providers).
     - **Unmatched Data**: 8,286,976 rows (active providers).

3. **Counts of Active Doctors by Practice**:
   - Counted active doctors based on their practice type, with the top 10 credential types as follows:
     - MD: 1,046,161
     - DDS: 156,420
     - DO: 133,364
     - ...

4. **Visualization**:
   - Created bar and pie charts to visualize the distribution of healthcare provider specialties, showing counts and relative percentages of each credential type.

### Interactive Doctor Search Feature
Using `Pandas`, the code includes functionality to search for specific doctors by first and last names. This allows both interactive and batch searching, with results displaying relevant details for matched records.

---

## Visualizations
- **Bar Chart**: Shows total doctors by specialty.
- **Pie Chart**: Displays the percentage of each specialty among all providers.

## Technologies Used
- **Python**: Data manipulation and analysis
- **Pandas**: Data cleaning, transformation, and analysis
- **Matplotlib / Seaborn**: Data visualization

---

## Usage
1. Download the latest NPI data from CMS.('https://download.cms.gov/nppes/NPI_Files.html')
2. Run the analysis script to generate charts and filtered datasets.
3. Use the search feature for doctor-specific queries.

---

## Results
This project demonstrates how healthcare provider data can be analyzed to identify key trends and support strategic decision-making in the healthcare industry.
