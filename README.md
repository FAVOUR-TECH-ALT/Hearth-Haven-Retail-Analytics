Hearth & Haven UK: Retail Analytics Dashboard

An interactive Excel dashboard for a fictional UK home-goods retailer, built with Power Query, the Excel Data Model, DAX measures, PivotTables and slicers. It covers sales, margin, discounts, returns, delivery and customers from 2021 to 2025.

Data note: all data is synthetic and was created for portfolio use. It does not describe real transactions or customers.

Dashboard page 1: Executive Overview

What I found
Revenue is flat, and the shape of the year is the story. Net revenue grew 1.7% in four years (£2.97M to £3.02M). October to December brings 32% of revenue, and December is about twice January in every category and channel.
Deeper discounts cost margin without larger baskets. Estimated gross margin falls from 53.0% at full price to 35.8% in the deepest discount band, while units per line stay at 1.40 to 1.41.
Margin gaps come from cost, not discounting. Decor has the lowest category margin and the highest product cost ratio, and stays lowest at full price.
Returns total £1.27M (8.49% of net revenue) and are spread widely. The ten products with the most returned value hold 6.2% of it. Paid Search is the one channel clearly above average.
Delivery looks the same everywhere. Lead time is about 5.7 days for every shipping method, region and month, although Express costs about £4.76 more per order.

The full analysis, limitations and recommendations are in the findings report. A shorter write-up is in the case study.

Dashboard pages
Page	Focus	For
1. Overview	KPIs, monthly trend, order status, category, region and channel	Head of E-commerce
2. Products & Margin	Category margin, cost ratios, discount effect	Merchandising and Finance
3. Returns & Delivery	Return reasons and rates, lead times, shipping	Customer Experience and Operations
4. Customers & Channels	Segments, repeat rate, regions, channels	Marketing and Customer teams

Products & Margin Returns & Delivery Customers & Channels

How the project was built
Audit and clean in Power Query, with the raw file left untouched. The issue log holds 27 entries.
Model the four tables (order lines, orders, customers, products) in the Excel Data Model with a Calendar table.
Define 12 KPIs before building charts. On-time delivery is deliberately not calculated, because the data has no promised delivery date.
Analyse trends, seasonality, discounts, categories, suppliers, returns, delivery and customers.
Build four dashboard pages with connected slicers.

Data model

Problems I solved
A date-format trap: 35 dates were written day first and an automatic month-first conversion blanked 18 sales orders (£2,916) from the yearly totals. I fixed it by parsing UK dates first.
A sales flag built in the wrong order: five cancelled or processing orders (£682) were counted as sales until the logic moved into the measures.
Repeated product names: 420 products share 223 names, so rankings use the product ID.
Business rules
Sales exclude Cancelled and Processing orders. Returned and Partially Returned orders count as sales, and returns are reported separately.
Margin is estimated gross margin (net revenue less estimated product cost), not profit.
The period is 1 January 2021 to 31 December 2025.
KPI definitions are in the KPI_Definitions sheet of the workbook.
Using the workbook
Download HearthHaven_Dashboard.xlsx and open it in Excel for Windows. The Data Model may not work in Excel for the web or some Mac versions.
Start at Dashboard 1 and use the sidebar buttons to move between pages.
Use the slicers (Year, Channel, Region, Category) to filter. Click the funnel icon on a slicer to clear it.
The Year slicer does not change the monthly trend line, and the Category slicer does not apply to the order-status chart or delivery times.

The workbook keeps its own copy of the data, so the dashboard works without the raw file. Refreshing the data needs the original source and the query connections.

Repository contents
Path	What it is
HearthHaven_Dashboard.xlsx	The final workbook: dashboards, calculations and documentation sheets
docs/Findings_Report.pdf	Findings, limitations and recommendations
docs/Case_Study.pdf	Short portfolio write-up
docs/HearthHaven_Documentation.xlsx	Issue log, data dictionary, KPI definitions, assumptions, hypotheses
images/	Dashboard and data model screenshots
Limitations

Estimated cost means margin is not profit. The data has no advertising spend, web traffic, stock levels or promised delivery dates, so marketing return, conversion, stockouts and on-time delivery cannot be measured. Discount and channel patterns show association, not cause.

Tools

Excel, Power Query, Excel Data Model, DAX, PivotTables, slicers.

Author

Favour Daniel
LinkedIn
