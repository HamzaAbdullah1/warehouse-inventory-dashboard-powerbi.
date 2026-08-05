# 📦 Warehouse Inventory Dashboard

An interactive Power BI dashboard for tracking daily material inventory levels across a warehouse operation, built to monitor consumption trends, identify low-stock items, and support replenishment decisions.

## 🎯 Overview

This dashboard transforms raw daily inventory snapshots (originally a wide-format spreadsheet with one column per date) into a clean, interactive reporting tool that tracks stock levels for 20+ material types over time.

## 🛠️ Tools & Skills Used

- **Power BI Desktop** — data modeling and visualization
- **Power Query (M language)** — data cleaning and transformation:
  - Unpivoted wide-format date columns into a normalized long-format table (`Materials`, `Date`, `Quantity`)
  - Handled duplicate column name conflicts and locale-specific date parsing (`DD-MMM` format)
  - Cleaned malformed values and type mismatches using `Replace Values` and error handling
- **DAX** — custom measures for business logic:
  - `SUMX` with `IFERROR` to safely aggregate text-stored numeric values
  - Dynamic "latest value" measures using `MAX(Date)` + `CALCULATE` to always reflect the most recent stock snapshot, regardless of report refresh date
- **Data Visualization**:
  - Line chart for consumption trends across materials over time
  - Bar chart for current stock ranking with dynamic date-based filtering
  - Conditional-formatted matrix (heatmap-style) for daily stock levels per material
  - KPI card and slicers for interactive filtering

## 📊 Key Features

- **Trend analysis** — visualize how each material's stock level changes day-to-day
- **Low-stock detection** — quickly identify materials running low based on the latest recorded values
- **Daily heatmap** — color-coded matrix view showing stock health across the full date range
- **Interactive filtering** — slice by material to focus on specific items

## 🖼️ Screenshots

*(Screenshot 2026-08-05 050848.png)*

## 📝 Data Note

The dataset used reflects a real warehouse operation's packaging material inventory (paper bags, tape, bubble wrap, etc.). No pricing, personnel, or customer information is included — the dashboard exclusively tracks material quantities.

## 📌 What I Learned

Working on this project deepened my hands-on experience with:
- Reshaping messy, real-world spreadsheet exports into analysis-ready data models
- Writing resilient DAX measures that handle data type inconsistencies gracefully
- Designing dashboards that answer specific operational questions (not just displaying data)
