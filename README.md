# Global Development & Technology Adoption Analysis

## Project Overview
This Capstone Project delivers an end-to-end data analytics workflow using the World Bank's **World Development Indicators (WDI)** dataset. The objective is to evaluate global trends in technology adoption—specifically focusing on internet penetration, mobile subscription rates, and economic context across nations over time.

---

## Technical Stack & Tools
- **Data Preprocessing & Cleaning:** Python (`pandas`, `numpy`)
- **Data Visualization & Dashboarding:** Power BI Desktop
- **Data Modeling:** Power Query, DAX Measures
- **Documentation & Publishing:** GitHub, PDF Reporting, LinkedIn

---

## Data Cleaning Workflow (Python)
Before importing the dataset into Power BI, Python was used to perform exploratory data analysis, filtering, and data cleaning.

```python
import pandas as pd

# 1. Load raw World Development Indicators dataset
df = pd.read_csv("WDI_CSV.csv")

# 2. Filter key technology and economic indicators
target_indicators = [
    "Individuals using the Internet (% of population)",
    "Mobile cellular subscriptions (per 100 people)",
    "GDP per capita (current US$)",
    "Population, total"
]
cleaned_df = df[df["Indicator Name"].isin(target_indicators)].copy()

# 3. Handle missing values and metadata alignment
cleaned_df.dropna(subset=["Country Code", "Value"], inplace=True)

# 4. Standardize data types
cleaned_df["Year"] = cleaned_df["Year"].astype(int)
cleaned_df["Value"] = cleaned_df["Value"].astype(float)

# 5. Export cleaned dataset for Power BI ingestion
cleaned_df.to_csv("wdi_cleaned.csv", index=False)

Power BI Dashboard & Visual Modeling
The cleaned dataset (wdi_cleaned.csv) was imported into Power BI to construct an interactive executive dashboard featuring:

KPI Cards: Displaying average global internet adoption rates and distinct country counts.

Top 10 Clustered Bar Chart: Highlighting leading nations in internet adoption percentage.

Regional Clustered Column Chart: Comparing average indicator metrics across country income groups and regions.

Trend Line Chart: Tracking global internet penetration progress over time.

Interactive Slicers: Allowing users to filter metrics dynamically by Year and Country Name.

Key Findings & Analytical Insights
Sustained Global Expansion: Internet penetration demonstrates a consistent upward trajectory globally, strongly driven by rapid mobile cellular network adoption.

Top Performing Economies: High-income economies and nations in Western Europe and the Middle East (e.g., Liechtenstein, Iceland, Qatar, Norway) lead global adoption with rates exceeding 90–95%.

Infrastructure & Economic Disparities: A direct positive correlation exists between national GDP per capita and internet user density, highlighting ongoing connectivity gaps in developing regions.

Strategic Recommendations
Targeted Infrastructure Financing: International development agencies and public-private partnerships should focus telecommunication infrastructure funding on lower-income markets.

Mobile-First Expansion Strategy: Policy planners should prioritize mobile spectrum allocation and infrastructure incentives as a cost-effective, scalable pathway to bridge remote digital divides.

Digital Literacy Integration: Deploy community digital skills programs alongside network expansion to ensure maximum adoption and economic impact.

Repository Structure & Deliverables
wdi_cleaned.csv — Preprocessed and cleaned dataset output from Python.

WDI_Technology_Analysis.pbix — Interactive Power BI Dashboard file.

Final_Capstone_Project_Report.pdf — Formal project report documentation.

README.md — Complete project summary and code workflow.
