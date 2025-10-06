📊 Power BI Superstore Sales and Profitability Dashboard
Project Overview
This dashboard is a comprehensive Business Intelligence (BI) solution designed to analyze the sales and profitability performance of a global Superstore chain. It moves beyond simple visualization to demonstrate proficiency in advanced data modeling, complex DAX calculations, and user-centric report design.

The report allows stakeholders to quickly identify top-performing product categories, track regional sales trends, and analyze key metrics across various customer segments and shipping modes.

🖼️ Report Preview
A snapshot of the final interactive sales and profitability dashboard:
<img width="1322" height="740" alt="image" src="https://github.com/user-attachments/assets/d2ae4599-5690-4912-882c-9ed4be16f69a" />


🚀 Key Features and Technical Skills Demonstrated
This project showcases several advanced techniques crucial for enterprise-level BI development:

1. Dynamic DAX and Advanced Filtering
Custom Dynamic Drill-Through Title Measure: Implemented a single, complex DAX measure to consolidate the filter context (e.g., specific City, Month, or Product Category) passed via a drill-through action. This ensures the target page's title clearly communicates the context of the data being viewed. 

Formula File: The custom DAX code for the dynamic title is provided in the DAX/ folder.

2. User Experience (UX) Enhancements
Interactive Reset Functionality: Implemented the Power BI Bookmark feature to create a "Reset to Home" button, clearing all slicers and resetting visual drill-down states (Data and Display options checked) for seamless navigation.

Custom Report Page Tooltips: Created specialized Report Page Tooltips that display granular metrics (e.g., top products) upon hovering over data points, reducing visual clutter and providing immediate context on the main page.

3. Data Visualization and Storytelling
Hierarchical Analysis: Utilized drill-down capabilities in visuals to enable seamless transition from Region > State > City, giving users granular control over geographical analysis.

Executive Overview: Incorporated a concise, one-line narrative summary at the top to provide immediate context, defining the report's purpose for executive consumption.

🏗️ Development Process
This project followed a structured development lifecycle to ensure efficiency, scalability, and maintainability.

Step 1: Data Modeling (Star Schema)
Data Cleaning: Used Power Query to cleanse and transform the raw Superstore_Data_Source.csv data.

Dimensional Modeling: Implemented a Star Schema by separating transactional data into a central Fact Table (FactSales) and creating several lookup Dimension Tables (DimCustomer, DimProduct, DimDate, DimGeography).

Relationship Management: Established one-to-many relationships (1:M) between Dimension and Fact tables, ensuring correct filter propagation and data integrity throughout the model.

Step 2: DAX Logic and Business Measures
Standard Measures: Created core measures for key business metrics such as Total Sales, Total Profit, and Profit Ratio.

Advanced Dynamic Title: Developed the complex DAX measure (Dynamic Report Title) to enhance the user experience by reflecting all filter selections simultaneously.

Step 3: Interactive Report Development
Layout and Design: Designed a clean, professional, and responsive layout for optimal viewing on desktop and tablet devices.

Visual Selection: Used appropriate visuals (e.g., Bar Charts for hierarchy analysis, Cards for KPIs) to tell the sales performance story effectively.

UX Implementation: Integrated bookmarks and customized drill-through features to guide users through the analysis and provide easy navigation.

🛠️ Technology Stack
Component

Tool / Language

Purpose

BI Tool

Power BI Desktop

Data modeling, visualization, report creation.

Language

DAX (Data Analysis Expressions)

Custom measures, calculated columns, and complex business logic.

Data Source

CSV

Standard flat-file data source (included for reference).

📁 Repository Contents
Report/Superstore_Sales_Analysis.pbix: The final, interactive report file.

Data/Superstore_Data_Source.csv: The clean input data set.

Presentation/Superstore_Analysis_Description.pdf: The Analysis Presentation/Description file

🔑 Key DAX Measure Snippet
To demonstrate the technical complexity:

The core logic for handling the dynamic title measure:

Drill-Through Title = 
VAR CategoryName = VALUES('Dim_Product'[Category])
VAR SubCategoryName = VALUES('Dim_Product'[Sub-Category])
VAR ProductName = VALUES('Dim_Product'[Product Name])

RETURN
    IF(
        HASONEVALUE('Dim_Product'[Product Name]),
        "Drill-Through for " & ProductName,
        IF(
            HASONEVALUE('Dim_Product'[Sub-Category]),
            "Drill-Through for " & SubCategoryName,
            IF(
            HASONEVALUE('Dim_Product'[Category]),
            "Drill-Through for " & CategoryName,
            "Drill-Through Page"
        )
    ))








Open the Report: Open the Superstore_Sales_Analysis.pbix file using Power BI Desktop.

Explore Interactivity: Test the dynamic title by making multiple selections in the date, region, and product slicers.

Created by

