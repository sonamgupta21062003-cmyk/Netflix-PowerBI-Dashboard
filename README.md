
 *Netflix Content Analytics Dashboard — Power BI*



Power BI

Power Query / M

DAX

KPI measures,
Data Cleaning


Data Modeling


KPI Development

Building headline metrics for fast business understanding

Interactive Reporting

Slicers and cross-filtering across visuals

Data Visualization

Donut, area, column and filled-map visual design

Geospatial Analysis

Country-level content distribution

Business Storytelling

Converting a raw content dataset into an easy-to-read analytical story

Dashboard UI/UX

Dark theme, visual hierarchy, KPI-first layout and consistent formatting

Analytical Thinking

Translating dataset fields into business questions and insights

 *Project Objective*

The goal of this project is to turn a raw Netflix titles dataset into an interactive analytical dashboard that helps users quickly understand the structure and evolution of the Netflix catalog.

The dashboard answers questions such as:

What is the balance between Movies and TV Shows?

How does Netflix content vary across release years?

Which ratings occur most frequently?

How is content distributed across countries?

How much director information is available across content types?

How do the metrics change when the user filters by Show Type, Release Year, or Country?

This project focuses on both technical Power BI skills and business-oriented data storytelling.

📌 Dashboard Snapshot

The current dashboard view displays:

KPI

Dashboard value

🎞️ Total Shows

8,086
<img width="941" height="446" alt="{BF2CCFA8-3756-4C46-8B4B-87D4ACD32A78}" src="https://github.com/user-attachments/assets/399354f5-21a6-41f8-a4e3-927135f4dd5e" />
<img width="941" height="446" alt="{BF2CCFA8-3756-4C46-8B4B-87D4ACD32A78}" src="https://github.com/user-attachments/assets/ce83ba67-6d7d-4310-a188-0d8fde56aa20" />


🎬 Movies

5,486

📺 TV Shows

2,600

🎥 Director-linked records

4,198

Note: These KPI values represent the current dashboard/model view in the PBIX file. The director metric is based on the dashboard's director field logic, not a verified count of unique people.

Content Mix

Movies: 67.85%

TV Shows: 32.15%

The dashboard therefore shows a clearly movie-heavy catalog in its current view.

🔄 End-to-End Analytics Workflow

Netflix Titles Dataset
        │
        ▼
   Data Import
        │
        ▼
 Power Query / M
        │
        ├── Cleaning
        ├── Data-type preparation
        ├── Blank / categorical handling
        ├── Country preparation
        └── Director preparation
        │
        ▼
  Cleaned Dataset
        │
        ▼
    DAX Measures
        │
        ├── Total Shows
        ├── Movies
        ├── TV Shows
        └── Director metric
        │
        ▼
 Interactive Visual Layer
        │
        ├── KPI Cards
        ├── Donut Charts
        ├── Area Chart
        ├── Rating Column Chart
        ├── Filled Map
        └── Slicers
        │
        ▼
 Business Insights

📂 Dataset Understanding

The repository contains the Netflix titles dataset with fields including:

Field

Purpose

show_id

Unique title identifier

type

Movie or TV Show

title

Content title

director

Director information

cast

Cast information

country

Country/countries associated with the title

date_added

Date the title was added

release_year

Original release year

rating

Content rating

duration

Movie runtime or number of TV seasons

listed_in

Genre/category information

description

Title description

The PBIX model also uses prepared fields such as Country_new and Director_new for reporting.

🧹 Data Preparation & Power Query / M Understanding

Power Query acts as the data-preparation layer between the raw CSV and the analytical report.

Why Power Query?

Raw data is rarely ready for direct reporting. Before visualization, the data needs to be made consistent, usable and analysis-friendly.

Main preparation responsibilities in this project

Validate and prepare column data types

Handle blank or incomplete categorical values

Prepare country information for geographic analysis

Prepare director information for analysis

Create cleaned fields used by report visuals

Keep the final reporting layer easier to analyze

Important fields created/used by the report

Country
   ↓
Country_new
   ↓
Filled Map

Director
   ↓
Director_new
   ↓
Director Analysis

Power Query mental model

Raw Data
   ↓
Transform
   ↓
Clean
   ↓
Shape
   ↓
Load

Power Query is therefore responsible for preparing the data, while Power BI's visual and DAX layers are responsible for analysis and presentation.

🧮 DAX & Measurement Layer

DAX provides the calculation layer used to turn the dataset into report-level KPIs and analytical metrics.

Measures visible in the PBIX report

Total Shows

Movies

TV Shows

Total director

Several chart visuals also use a non-blank count of show_id as the title-count aggregation.

DAX concepts demonstrated

Measure
   ↓
Filter Context
   ↓
Aggregation / Conditional Logic
   ↓
KPI or Visual

Why measures instead of hard-coded numbers?

Because measures respond to the current filter context.

For example:

Select "Movie"
      ↓
Movies KPI updates
      ↓
Donut updates
      ↓
Release trend updates
      ↓
Ratings update
      ↓
Country analysis updates

This is what makes the report dynamic rather than static.

📊 Dashboard Visualizations

1. 🎯 KPI Cards — Executive Overview

The top section provides immediate headline metrics:

Total Shows

Movies

TV Shows

Director-linked records

Why this visual?

KPI cards answer the first question a stakeholder usually has:

"What is the current size and composition of the catalog?"

They create a strong executive-summary layer before the user explores detailed charts.

2. 🍿 Movie vs TV Show — Donut Chart

Category: type
Metric: title count

What it shows

The visualization compares:

Movies

TV Shows

Current dashboard understanding

Movies     █████████████████  67.85%
TV Shows   ████████           32.15%

This immediately communicates that Movies form the larger share of the displayed catalog.

Analytical purpose

Useful for understanding:

Content mix

Format preference

How the catalog composition changes under filters

3. 📈 Release-Year Trend — Area Chart

X-axis: release_year
Y-axis: title count

What it shows

The area chart tracks how many titles belong to each release year.

Key visual pattern

The dashboard shows a relatively low level in older years followed by a strong increase through the 2010s, with the highest concentration appearing in the late-2010s portion of the chart.

Business question

"How has the composition of the Netflix catalog changed over time?"

Why an area chart?

Because the objective is to communicate trend + volume over time rather than compare isolated categories.

4. ⭐ Rating Distribution — Column Chart

X-axis: rating
Y-axis: title count

What it shows

The column chart compares title volume across content-rating categories.

Current dashboard understanding

The chart visually indicates that TV-MA is the largest rating category, followed by TV-14, with other ratings contributing smaller volumes.

Business questions

Which ratings dominate the catalog?

How does the rating distribution change by content type?

How does the mix change for a selected country or year?

5. 🌍 Country Distribution — Filled Map

Geographic field: Country_new

What it shows

The filled map provides a geographic view of where Netflix titles are represented across countries.

Why a map?

A geographic visual makes spatial patterns much easier to understand than a long country list.

Business questions

Which markets have the strongest content representation?

How does country distribution change when filtering the report?

6. 🎥 Director Analysis — Donut / Metric Layer

The PBIX includes a director-focused visual using the cleaned Director_new field.

This layer helps compare the availability of director information across content types.

Important interpretation

The displayed metric is a count of non-blank director-linked records, so it should not automatically be described as the number of unique directors.

That distinction is important in an interview because:

Count of director records ≠ Count of unique directors

7. 🎛️ Interactive Slicers

The dashboard contains three primary slicers:

Show Type

All
Movie
TV Show

Release Year

Allows the user to focus the dashboard on a selected year.

Country

Allows the user to focus the report on a selected country.

Why slicers matter

They turn the dashboard into an exploration tool.

Instead of creating a separate report for every business question, the same visuals can be reused dynamically.

🔍 Understanding the Interactivity

The strongest analytical feature of this report is the interaction between the filters and visuals.

Example: Country Analysis

User selects a country
        ↓
Filter context changes
        ↓
KPI values recalculate
        ↓
Movie / TV mix changes
        ↓
Release-year trend changes
        ↓
Rating distribution changes
        ↓
Other visuals reflect the filtered context

Example: Movie Analysis

Select "Movie"
      ↓
Only movie records remain in context
      ↓
KPI values update
      ↓
Release trend updates
      ↓
Ratings update
      ↓
Country distribution updates

This is the difference between a dashboard and a collection of independent charts.

🧠 Why Each Visualization Was Chosen

Visualization

Analytical purpose

KPI Card

Fast executive summary

Donut Chart

Show composition / share

Area Chart

Time-based trend and volume

Column Chart

Category comparison

Filled Map

Geographic distribution

Slicer

User-driven filtering

The visual choices are based on the question being answered, not simply on visual variety.

💡 Key Insights From the Current Dashboard

1. Movies dominate the catalog

The current dashboard shows 5,486 Movies vs 2,600 TV Shows, giving Movies a 67.85% share.

2. Content volume is concentrated in newer release years

The release-year visualization shows a major increase during the 2010s compared with older release years.

3. TV-MA is the leading rating category

The rating chart makes TV-MA the most prominent rating in the displayed report.

4. Netflix content is geographically broad

The map demonstrates that the catalog is not concentrated in a single market; titles are represented across multiple regions.

5. Interactivity changes the story

A global summary can look very different after selecting a country, year, or content type. This makes filter-context analysis a major part of the dashboard.

These observations describe the current dashboard view and should not be interpreted as causal business conclusions about Netflix's real-world strategy.

🎨 Dashboard Design & UX

The report uses a dark entertainment-style theme with:

Strong red visual accents

Bright yellow analytical labels

High-contrast cards

Rounded visual containers

KPI-first hierarchy

Compact filter controls

Clear separation between summary and detailed analysis

Design philosophy

Top
│
├── Filters
├── KPIs
│
├── Main Trend / Composition Analysis
│
└── Rating + Geography
Bottom

The result is a dashboard designed for fast scanning first, deeper exploration second.

📐 Power BI Report Structure

The current PBIX is a single-page 1280 × 720 report containing the main dashboard experience.

The report definition includes:

KPI cards

Movie/TV donut analysis

Director-focused analysis

Release-year area chart

Rating column chart

Country filled map

Show Type slicer

Release Year slicer

Country slicer

Netflix branding image

📁 Repository Structure

Netflix-PowerBI-Dashboard/
│
├── README.md
├── dashboard of netflix.pbix
├── netflix.jpg
└── netflix_titles.csv

File purpose

File

Purpose

dashboard of netflix.pbix

Power BI report

netflix_titles.csv

Source dataset

netflix.jpg

Dashboard preview

README.md

Project documentation

▶️ How to Run the Project

1. Clone the repository

git clone https://github.com/sonamgupta21062003-cmyk/Netflix-PowerBI-Dashboard.git

2. Open Power BI Desktop

Open:

dashboard of netflix.pbix

3. Check the data source

The repository contains:

netflix_titles.csv

If Power BI asks for a different file location, update the source path in Power Query.

4. Refresh

Use:

Home → Refresh

5. Explore the dashboard

Try combinations of:

Show Type + Release Year + Country

and observe how the KPIs and visuals change.

🗣️ Interview-Ready Project Explanation

30-second answer

"I built an interactive Netflix Content Analytics dashboard using Power BI. I started by preparing the Netflix titles dataset in Power Query, including cleaning and creating analysis-ready country and director fields. Then I used DAX-based measures for KPIs such as total shows, movies, TV shows and director-linked records. I designed a one-page interactive dashboard with KPI cards, donut charts, a release-year area chart, a rating column chart, a filled country map and slicers for show type, release year and country. The main objective was to turn raw catalog data into an interactive analytical story rather than just presenting static charts."

🧑‍💼 Common Interview Questions

Why did you use Power Query?

Answer:
"Power Query is the data-preparation layer. I used it to clean and structure the raw dataset and create fields that were more suitable for reporting and visualization."

Why did you use DAX?

Answer:
"DAX allowed me to create reusable measures that respond to filter context, so KPIs and visual totals update automatically when users interact with the dashboard."

Why use a donut chart for Movie vs TV Show?

Answer:
"Because the question is about composition. A donut chart makes the relative share of Movies and TV Shows easy to understand at a glance."

Why use an area chart for release year?

Answer:
"The variable is temporal, so an area chart communicates the overall trend and volume across years more naturally than a categorical chart."

Why use a filled map?

Answer:
"Country is a geographic field, so a map is an intuitive way to identify spatial patterns in content distribution."

What is the difference between a report and a dashboard?

Answer:
"A Power BI report is a richer analytical experience that can contain multiple pages and extensive interaction. A dashboard is a single-page monitoring view and can bring tiles from different reports."

What happens when I select a slicer?

Answer:
"The selection changes the filter context. Connected visuals recalculate their measures and update to reflect the selected subset."

What is the difference between a count of directors and unique directors?

Answer:
"A count of non-blank director records counts populated records. A distinct count counts unique director names. They can produce different results, especially when one person appears on multiple titles."

📌 Resume-Ready Project Description

Netflix Content Analytics Dashboard | Power BI

Built an interactive Power BI dashboard to analyze 8,086 titles, including 5,486 Movies and 2,600 TV Shows in the dashboard's current model view.

Used Power Query / M for data preparation and analysis-ready fields, including country and director transformations.

Developed DAX-based KPIs and filter-aware reporting for content mix and catalog analysis.

Designed interactive donut, area, column and filled-map visualizations with slicers for Show Type, Release Year and Country.

Applied data storytelling and dashboard UX principles to convert raw catalog data into an executive-friendly analytical view.

🚀 Future Enhancements

The current dashboard can be extended with:

Genre-level analysis using listed_in

Top countries by title count

Top directors using DISTINCTCOUNT

Movie duration analysis

TV-show season analysis

Titles added over time using date_added

KPI percentage measures

Drill-through pages

Report tooltips

Bookmarks and navigation

Dedicated executive summary page

Advanced time-intelligence measures

Power BI Service publishing

⚠️ Analytical Limitations

This project is a catalog analytics project, not a complete Netflix business-performance model.

The available dataset does not directly provide:

Streaming hours

Revenue

Subscriber-level behavior

Watch time

Retention

Customer satisfaction

Content ROI

Therefore, the dashboard should be used to understand catalog structure and descriptive patterns, rather than to make unsupported claims about profitability or customer behavior.

⭐ What This Project Shows

RAW DATA
   ↓
POWER QUERY / M
   ↓
CLEAN & SHAPE
   ↓
DAX MEASURES
   ↓
DATA MODEL
   ↓
INTERACTIVE VISUALS
   ↓
FILTER CONTEXT
   ↓
BUSINESS INSIGHTS

This project demonstrates an end-to-end Power BI analytics workflow rather than only chart creation.

🔗 Repository

GitHub:
https://github.com/sonamgupta21062003-cmyk/Netflix-PowerBI-Dashboard

LinkedIn:
https://www.linkedin.com/in/sonam-gupta-a5a9b640/

👩‍💻 Author

Sonam Gupta

B.Sc. Computer Science
Aspiring Data Analyst | Power BI | SQL | Python | Machine Learning

<p align="center">
  <b>📊 Transforming raw data into clear, interactive business insights.</b>
</p>
