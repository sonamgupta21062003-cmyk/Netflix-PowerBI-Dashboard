🎬 Netflix Content Analytics Dashboard

Interactive Power BI dashboard for exploring Netflix's movies and
TV-show catalog, content mix, release trends, ratings, directors, and
geographic distribution.






📌 Project Overview

This project transforms Netflix catalog data into an interactive
business intelligence dashboard using Microsoft Power BI.

The dashboard is designed to answer practical analytical questions such
as:

How large is the Netflix catalog?

What is the split between Movies and TV Shows?

How has Netflix content changed across release years?

Which ratings are most common?

How is content distributed across countries?

How does the catalog change when users filter by content type,
year, or country?

What patterns can be identified from the available director and
content information?

The goal is not just to display charts, but to create a dashboard that
allows a user to explore the catalog interactively and quickly
identify meaningful patterns.

🎯 Business Objective

The dashboard provides a compact analytical view of Netflix's content
library for stakeholders who want to understand:

Content Mix → Growth/Release Trends → Audience Ratings → Geographic
Distribution → Catalog Exploration

It can be used as a portfolio project to demonstrate practical skills
in:

Data cleaning

Data transformation

Data modeling

DAX

KPI design

Data visualization

Interactive dashboard development

Business-oriented storytelling

🛠️ Tech Stack

Tool                      Purpose

Microsoft Power BI    Dashboard development and visualization
Power Query / M       Data cleaning and transformation
DAX                   Measures and KPI calculations
Data Modeling         Organizing analytical fields and measures
Interactive Slicers   Dynamic filtering
Map Visualization     Geographic content analysis

🔄 Data Analytics Workflow

Raw Netflix Dataset
        ↓
Data Import
        ↓
Power Query / M
        ↓
Data Cleaning & Transformation
        ↓
Data Type & Missing-Value Handling
        ↓
Calculated / Cleaned Fields
        ↓
DAX Measures
        ↓
Interactive Visualizations
        ↓
Dashboard
        ↓
Business Insights

1. Data Preparation

The dataset was prepared in Power Query before visualization.

Typical preparation activities included:

Correcting data types

Handling missing values

Cleaning categorical fields

Preparing country information

Preparing director-related fields

Standardizing fields used by slicers

Creating analysis-ready columns

This ensures that the dashboard is based on a cleaner and more
consistent analytical layer.

📊 Dashboard Components

🔢 KPI Cards

The dashboard includes high-level KPI indicators for:

Total Shows

Movies

TV Shows

Total Directors

These KPIs provide an immediate snapshot of the catalog.

🍿 Content Type Analysis

A donut chart compares:

Movies

TV Shows

This helps identify the overall composition of the Netflix catalog.

📈 Release-Year Trend

An area chart tracks the number of titles by release year.

This makes it easier to identify:

Periods of higher content production

Changes in catalog composition over time

Long-term release patterns

⭐ Rating Analysis

A column chart analyzes the distribution of titles across content
ratings.

This helps explore the audience positioning of the catalog and identify
the most frequently represented rating categories.

🌍 Geographic Analysis

A filled map visualizes Netflix content by country.

This enables geographic exploration of the catalog and helps identify
countries/regions with stronger representation.

🎬 Director Analysis

The dashboard includes director-related analysis to provide an
additional perspective on the catalog's creative contributors.

🎛️ Interactive Filters

Users can dynamically filter the dashboard using:

Show Type

Release Year

Country

The visuals respond to these selections, allowing users to move from a
high-level overview to a more focused analysis.

💡 Key Analytical Questions

The dashboard is built around questions rather than simply displaying
visuals:

Content

Is the catalog more heavily represented by Movies or TV Shows?

How does the content mix change under different filters?

Time

Which release periods contain the highest concentration of titles?

How does the catalog evolve across years?

Ratings

Which ratings dominate the catalog?

Does the rating mix change by content type or country?

Geography

Which countries contribute the most titles?

How does geographic representation change when filtering the
dashboard?

Exploration

What changes when a specific year, country, or content type is
selected?

🔍 Interactive Analysis

One of the main strengths of the dashboard is cross-filtering.

For example:

Select Country
      ↓
KPIs update
      ↓
Movie/TV split updates
      ↓
Release trend updates
      ↓
Rating distribution updates
      ↓
Other visuals reflect the selection

This turns the report from a static collection of charts into an
interactive analytical tool.

📐 DAX & KPI Layer

The project uses Power BI measures for KPI calculations and aggregation.

Example conceptual measures:

Total Shows =
COUNTROWS(cleaned_netflix_data)

Movies =
CALCULATE(
    [Total Shows],
    cleaned_netflix_data[type] = "Movie"
)

TV Shows =
CALCULATE(
    [Total Shows],
    cleaned_netflix_data[type] = "TV Show"
)

Measure names and formulas can be adapted to the final model depending
on the version of the PBIX file.

🎨 Dashboard Design

The dashboard follows a dark, entertainment-style visual theme inspired
by Netflix branding.

Design principles used

Dark background for visual contrast

Strong accent colors

KPI-first layout

Consistent visual hierarchy

Interactive slicers

Rounded visual containers

Geographic visualization

Minimal unnecessary decoration

The objective is to make the dashboard visually attractive while
keeping the analysis readable.

📷 Dashboard Preview

Add your final dashboard screenshot here:

![Netflix Power BI Dashboard](images/netflix-dashboard.png)

Recommended GitHub structure

Netflix-PowerBI-Dashboard/
│
├── README.md
├── Netflix_Dashboard.pbix
│
├── dataset/
│   └── netflix_titles.csv
│
├── images/
│   └── netflix-dashboard.png
│
└── documentation/
    └── project-notes.md

If the original dataset has redistribution restrictions, include a
link/instructions for obtaining it rather than committing the raw
dataset.

📈 Portfolio Value

This project demonstrates more than basic chart creation.

Skills demonstrated

Power BI - Dashboard development - Interactive reporting - Visual
design - Slicers - Cross-filtering - KPI cards - Maps - Trend analysis

Power Query - Data transformation - Data cleaning - Column
preparation - Handling analytical fields

DAX - Measures - Conditional calculations - KPI logic -
Filter-context-based analysis

Analytics - Trend analysis - Categorical analysis - Geographic
analysis - Business storytelling - Interactive exploration

🚀 How to Use the Project

1. Download the repository

git clone https://github.com/YOUR_USERNAME/Netflix-PowerBI-Dashboard.git

2. Open the PBIX file

Open:

Netflix_Dashboard.pbix

using Microsoft Power BI Desktop.

3. Explore the dashboard

Try different combinations of:

Show Type

Release Year

Country

and observe how the KPIs and visuals change.

🧠 Interview Explanation

30-second project explanation

"I built an interactive Netflix Content Analytics dashboard in Power
BI. I first prepared and transformed the Netflix catalog using Power
Query, created DAX measures for key KPIs such as total shows, movies,
and TV shows, and then built interactive visuals for content type,
release-year trends, ratings, directors, and country-level
distribution. I also added slicers for show type, release year, and
country so users can dynamically explore the catalog. The main focus
was not just visualization, but converting the dataset into an
interactive analytical story."

If the interviewer asks: "Why Power BI?"

"Power BI allows me to combine data transformation, DAX-based
calculations, interactive filtering, and visualization in a single
analytical workflow. It also makes it easy for business users to
explore the data without writing queries themselves."

If asked: "What did you do in Power Query?"

"I used Power Query as the data-preparation layer to clean and
structure the dataset before analysis. This included handling data
types, cleaning categorical fields, preparing country and director
fields, and creating analysis-ready columns."

If asked: "What makes your dashboard interactive?"

"The dashboard uses slicers for show type, release year, and
country. Selecting a value changes the connected KPIs and visuals
through Power BI's filtering and cross-filtering behavior."

🔮 Future Improvements

Possible next versions could include:

📌 Genre-level analysis

📌 Average content duration

📌 Year-over-year growth

📌 Top countries by content volume

📌 Top directors by number of titles

📌 Movie vs TV Show trend comparison

📌 Drill-through pages

📌 Tooltip pages

📌 Bookmark-based navigation

📌 Executive summary page

📌 Advanced DAX time-intelligence measures

📌 Power BI Service deployment

⭐ Project Highlights

✓ Power Query data transformation
✓ DAX-based KPI layer
✓ Interactive slicers
✓ Cross-filtering
✓ Time-series analysis
✓ Rating analysis
✓ Geographic analysis
✓ Content-type analysis
✓ Professional dashboard design
✓ Business-focused storytelling

👩‍💻 Author

Sonam Gupta

Student of Computer Science | Data Analytics | Power BI | Python | SQL |
Machine Learning

Connect with me

LinkedIn: https://www.linkedin.com/in/sonam-gupta-a5a9b640/

GitHub: https://github.com/sonamgupta21062003-cmyk

📜 License

This project is intended for educational and portfolio purposes.

Dataset ownership and licensing remain with the original data
provider/source.
