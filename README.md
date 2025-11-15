# Global-Electric-Vehicle-Analysis-Dashboard
This Power BI project analyzes the Global EV Market using IEA 2024 data, highlighting adoption trends, regional performance, and powertrain growth. Through advanced modeling, Power Query, and DAX, it delivers actionable insights for policymakers, manufacturers, and researchers to guide sustainable mobility and strategic decision-making worldwide.
# 🔌 Global EV Sales Analysis — Power BI Dashboard

An interactive Power BI dashboard that analyzes global electric vehicle (EV) adoption using the **IEA Global EV Data 2024**.  
This project transforms raw data into a decision-ready dashboard to explore EV sales, stock, energy demand, powertrain mix, and vehicle-type trends across regions and over time.

> Slide deck and project notes referenced from the project presentation. :contentReference[oaicite:1]{index=1}

---

## 🚩 Project Overview
As EV adoption accelerates worldwide, stakeholders need clear, data-driven views of where and how EVs are growing. This dashboard answers questions such as:
- How do EV **sales** and **stock** compare across regions and years?
- Which **powertrains** (BEV / PHEV / FCEV) dominate in different markets?
- What is the **energy demand** impact across regions?
- How do **vehicle types** (cars, buses, vans, trucks) contribute to EV stock and sales?

---

## 🗂 Dataset
- **Source:** IEA Global EV Data 2024 (used as the primary data for sales, stock, energy demand, powertrain & category breakdowns).  
- Data was ingested as CSV and modeled in Power BI to create the visualizations and time-series analyses.

---

## 📊 Key Visuals & Insights
The dashboard includes the following major visuals and takeaways:

- **Regional Energy Demand Trends**  
  Visualizes GWh / energy demand by region and year — useful for grid and policy planning.

- **EV Sales vs. EV Stock (Time-series)**  
  Compares annual sales and cumulative stock to highlight adoption momentum.

- **Powertrain Mix (BEV / PHEV / FCEV)**  
  Shows how different drivetrains contribute to sales and stock by region.

- **Vehicle Type Breakdown**  
  Tracks shares of cars, buses, trucks, and vans — reveals which vehicle categories are electrifying fastest.

- **Interactive Filters**  
  Region, year, and vehicle-category slicers for on-the-fly exploration and scenario comparisons.

These visualizations help policymakers, automakers, energy planners, and investors understand adoption trends and anticipate future demand.

---

## 🛠 How to reproduce / run locally
1. **Prerequisites**
   - Power BI Desktop (latest stable release)
   - The dataset CSV(s) (IEA Global EV Data 2024 CSVs used in this project)

2. **Load data**
   - Open Power BI Desktop → `Get data` → `CSV` → select the IEA data file(s).

3. **Modeling**
   - Load relevant tables (sales, stock, energy demand, powertrain, vehicle categories).
   - Create relationships based on `year` and `region` columns.

4. **Recommended Measures (examples in DAX)**
   ```dax
   Total_Sales = SUM(Sales[units])
   Total_Stock = SUM(Stock[units])
   Sales_YoY = DIVIDE([Total_Sales] - CALCULATE([Total_Sales], PREVIOUSYEAR(Date[Year])), CALCULATE([Total_Sales], PREVIOUSYEAR(Date[Year])))
   EnergyDemand_GWh = SUM(Energy[GWh])
