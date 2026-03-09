# Sales and Customer Analytics Dashboard

## Objective
Create an interactive executive level dashboard which dynamically displays key performance indicators & quantity analytics.

## Data & Methodology
- Data contained information such as: Order Quantity, Date, and location; COGS, Revenue, and Profit per Order; Customer Name.
- Created new measures and calculated columns to develop data.

## Skill Demonstrated
- DAX Measures
- Advanced Visualization Analytics
- Business Intelligence Dashboard Design
- Interactive Filters & Slicers

## DAX Formula Examples
Customer Lifetime Value = (SUM(SalesData[Revenue USD]) / SUM(SalesData[Quantity])) * (DISTINCTCOUNT(SalesData[Sales Order Number])) * (MAX(SalesData[Year]) - MIN(SalesData[Year]))

Order Size Descriptor = 
VAR Q75 = PERCENTILEX.INC(ALL(SalesData), SalesData[Quantity], 0.75)
VAR Q50 = PERCENTILEX.INC(ALL(SalesData), SalesData[Quantity], 0.50)
VAR Q25 = PERCENTILEX.INC(ALL(SalesData), SalesData[Quantity], 0.25)
RETURN SWITCH(TRUE(), SalesData[Quantity] >= Q75, "Large Orders (Top 25%)", SalesData[Quantity] >= Q50, "Above Median Orders", SalesData[Quantity] >= Q25, "Mid-Size Orders", "Small Orders (Bottom 25%)")

Top 5 Revenue = CALCULATE([Total Revenue], TOPN(5, VALUES(SalesData[Customer Name]), [Total Revenue]))

## Key Performanc Indicators & Viusalizations
KPIs
- Total Revenue
- Gross Profit
- Total Orders
- % Revenue from Top 5 Customers

Visualizations
- Gross Profit Margin over Year and Month
- Customer Lifetime Value by Customer
- Number of Orders and Average Revenue per Order categorized by Order Size

## Quantity Analytics Visualizations
- Sum of Quanityt by Sales Area and City
- USA Revenue & Profit Margin by Sales Area
- Germany Revenue & Profit Margin by Sales Area
