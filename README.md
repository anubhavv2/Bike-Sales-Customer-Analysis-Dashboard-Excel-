# Bike-Sales-Customer-Analysis-Dashboard-Excel-
A complete Excel-based data analysis project that cleans raw customer data, engineers new features, answers key business questions using formulas, and visualizes insights through an interactive dashboard with pivot charts and slicers.

# Dataset
The dataset contains 1,000+ customer records with fields including Marital Status, Gender, Income, Children, Education, Occupation, Home Owner, Cars, Commute Distance, Region, Age, and Purchased Bike (Yes/No).

## Project Workflow

### 1. Data Cleaning
- Removed duplicate records using **Data → Remove Duplicates**
- Standardized coded values using **Find & Replace**:
  - Marital Status: `M` → Married, `S` → Single
  - Gender: `M` → Male, `F` → Female

### 2. Feature Engineering
- **Age Brackets**: Created using a nested `IF` formula to segment customers into Young Adults, Early Middle Age, Middle Age, Mature Adults, and Seniors
=IF(N2<34,"Young Adults",IF(N2<44,"Early Middle Age",IF(N2<54,"Middle Age",IF(N2<64,"Mature Adults","Seniors"))))

- **Risk Category & Loyalty Points**: Created a lookup table and used `VLOOKUP` to enrich records based on Occupation
=VLOOKUP(Table1[@Occupation],Table2[#All],2,FALSE)

### 3. Business Questions Answered (using COUNTIFS / AVERAGEIFS)
| # | Question | Function Used |
|---|---|---|
| Q1 | How many male customers with income above 60,000 purchased a bike? | COUNTIFS |
| Q2 | How many customers in each Region are homeowners and purchased a bike? | COUNTIFS |
| Q3 | What is the average income of married vs. single customers, split by bike purchase? | AVERAGEIFS |
| Q4 | What is the average number of cars owned by bike buyers vs. non-buyers, by region? | AVERAGEIFS |

### 4. Pivot Tables & Charts
- Average income of customers (gender-wise) who purchased a bike or not
- Average commute distance of bike buyers vs. non-buyers
- Line chart showing bike purchase trends across age brackets

### 5. Interactive Dashboard
Built a dynamic Bike Sales Dashboard combining all pivot charts with slicers, enabling real-time filtering across Gender, Region, Age Bracket, and other dimensions.

## Skills & Excel Functions Used
Remove Duplicates · Find & Replace · Nested IF · VLOOKUP · COUNTIFS · AVERAGEIFS · Pivot Tables · Pivot Charts · Slicers · Dashboard Design

## Repository Structure
├── README.md                 # Project documentation
└── Excel_Project.xlsx        # Full workbook with all sheets (raw data, working sheet, lookup table, pivot tables, business questions, dashboard)

## Key Insights
- 188 male customers with an income above 60,000 purchased a bike
- North America leads in homeowner bike buyers (158), followed by Europe (99) and Pacific (68)
- Married customers who purchased a bike have a higher average income (60,346) than those who didn't (57,492); the same trend holds for single customers (55,760 vs. 51,085)
- Non-bike buyers consistently own more cars on average than bike buyers across all regions — Pacific shows the widest gap (2.316 vs. 1.549 cars), suggesting customers with fewer cars are more likely to rely on a bike

## How to Use
1. Download Excel_Project.xlsx
2. Open in Excel (2016 or later recommended for full Pivot Table/Slicer support)
3. Navigate to the Dashboard sheet to interact with slicers and explore insights in real time
