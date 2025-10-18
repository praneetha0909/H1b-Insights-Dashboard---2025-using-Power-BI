# H1B Petition Insights Dashboard---2025

An interactive Power BI Dashboard that provides analytical insights into USCIS H-1B visa petitions for FY2025.
This project visualizes petition trends, employer performance, and approval statistics across the United States.


## Project Overview
This dashboard helps analyze official H-1B petition data to identify patterns and key insights, including:

- Top employers filing H-1B petitions
- States with the highest petition volume
- Approval and denial trends by case type
- Overall approval rate across employers


## Key Features

### KPI Cards
- Total Petitions: 310K
- Total Approvals: 304K
- Total Denials: 6K
- Total Employers: 43K
- Approval Rate: 98%
- Top Employer: AMAZON COM SERVICES LLC

### Visual Components
- Map Visualization (Azure Map): Displays petition distribution by state
- Donut Chart: Shows overall approval vs. denial share
- Bar Chart: Displays approvals and denials by case type
- Column Chart: Approval and denial count by fiscal year
- Employer Ranking Chart: Top employers by petition count

### Filters and Slicers
- Decision: Approval / Denial
- Petitioner State
- Case Type

### Design Highlights
- Clean and minimal layout with shadowed KPI cards
- Light gray background (#F7F7F7) for visual depth
- Consistent color palette: green to yellow (#2E7D32 → #FBC02D)
- DAX-based text wrapping for employer names


## Tools and Technologies

| Tool / Technology | Purpose |
|--------------------|----------|
| Power BI Desktop | Dashboard design and data modeling |
| DAX | Custom calculations, KPIs, and measures |
| Power Query | Data cleaning and transformation |
| Azure Map Visual | Geographic petition visualization |
| USCIS Dataset (FY2025) | Data source for analysis |


## DAX Measures

-- Total Petitions
Total Petitions = SUM('Raw_USCIS'[Count])

-- Total Approvals
Total Approvals = CALCULATE(SUM('Raw_USCIS'[Count]), 'Raw_USCIS'[Decision] = "Approval")

-- Total Denials
Total Denials = CALCULATE(SUM('Raw_USCIS'[Count]), 'Raw_USCIS'[Decision] = "Denial")

-- Approval Rate
Approval Rate = DIVIDE([Total Approvals], [Total Petitions])

-- Employer Name Wrap
Employer_Name_Wrapped =
IF(
    LEN('Raw_USCIS'[Employer (Petitioner) Name]) > 15,
    SUBSTITUTE('Raw_USCIS'[Employer (Petitioner) Name], " ", UNICHAR(10), 1),
    'Raw_USCIS'[Employer (Petitioner) Name]
)


## Dashboard Preview
![H1B Petition Dashboard](./uscis%20h1b.jpg)


## How to Use

1. Clone or download this repository.
2. Open the `.pbix` file in Power BI Desktop (Version 2024 or later).
3. Load or refresh the dataset if required.
4. Use slicers to interact and explore insights by Decision, State, and Case Type.


## Example Insights

- Amazon Com Services LLC leads all employers with over 10K petitions filed.
- Texas and California are the top petitioning states.
- The overall approval rate is 98% for FY2025.


## Future Enhancements

- Multi-year comparison (FY2023–FY2025)
- Predictive modeling for approval rate trends
- Publish to Power BI Service for real-time refresh


## Author

Praneetha Mukkamala  
M.S. Computer Science, University of Texas at Arlington  
Dallas–Fort Worth, Texas  

Email: mukkamalapraneetha@gmail.com  
LinkedIn: https://linkedin.com/in/praneethamss 
GitHub: https://github.com/praneetha0909
