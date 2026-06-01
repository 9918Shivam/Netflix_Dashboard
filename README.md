# 🎬 Netflix Analytics Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![CSV](https://img.shields.io/badge/Data-CSV-brightgreen?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-512BD4?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-Media%20Analytics-red?style=for-the-badge)

---

## 📌 Project Overview

This project is an **interactive Netflix Content Analytics Dashboard** built in Microsoft Power BI, analyzing Netflix's global content library of **7,787 titles** across movies, TV shows, genres, countries, release years, ratings, and durations.

The central business question this dashboard answers:

> **"How has Netflix built its content library — which countries, genres, and content types dominate, and how has the catalog evolved over time?"**

Just as a web developer deploys a live website anyone can open and interact with, this dashboard is a **published, filterable report** that media analysts, content strategists, or recruiters can explore in real time.


> 📸 **Dashboard Preview:**

![Netflix Dashboard](./screenshorts/dashboard_preview.png)

---

## 🗂️ Repository Structure

```
netflix-analytics-dashboard-powerbi/
│
├── 📁 data/
│   └── NetFlix.csv                    # Raw dataset — 7,787 Netflix titles
│
├── 📁 report/
│   └── Net1.pbix                      # Power BI Desktop report file
│
├── 📁 screenshots/
│   └── dashboard_preview.png          # Full dashboard screenshot
│
└── README.md                          # You are here
```
---

## 📊 Dataset Description

**Source:** Netflix Titles Dataset (publicly available)
**File:** `NetFlix.csv`
**Total Records:** 7,787 titles
**Format:** CSV (flat file, single table)

### Columns

| Column | Description |
|---|---|
| `show_id` | Unique identifier for each title |
| `type` | Content type — Movie or TV Show |
| `title` | Name of the title |
| `director` | Director name(s) |
| `cast` | Main cast members |
| `country` | Country where content was produced |
| `date_added` | Date the title was added to Netflix |
| `release_year` | Original year of release |
| `rating` | Content rating (TV-MA, TV-14, R, PG-13, etc.) |
| `duration` | Length in minutes (Movies) or seasons (TV Shows) |
| `genres` | Genre tags (comma-separated, multi-genre) |
| `description` | Short plot summary |

---

## 📈 Dashboard Features & Visuals

| Visual | Type | What It Shows |
|---|---|---|
| **Total Titles** | KPI Card | 7,789 total content pieces on Netflix |
| **Movies Count** | KPI Card | 5,377 movies in the library |
| **TV Shows Count** | KPI Card | 2,410 TV shows in the library |
| **Country Count** | KPI Card | Content spanning 681 unique countries |
| **Movies Count by Type** | Donut Chart | Content split — Movie vs TV Show vs Director breakdown |
| **Count of Title by Release Year** | Line Chart | How content volume has grown across decades |
| **Count of Country by Title** | Horizontal Bar | Which titles are available in multiple countries |
| **Movies Count by Genres** | Bar Chart | Genre popularity — from Children & Family to Action |
| **Sum of Release Year by Duration** | Area/Line Chart | Duration distribution across release periods |
| **Country Slicer** | Dropdown | Filter entire dashboard by production country |
| **Year Added Slicer** | Dropdown | Filter by the year a title was added to Netflix |
| **Date Added / Year Added Slicer** | Dropdown | Granular date-based filtering |

---

## 🔍 Problem Solved & Data Story

### ❓ The Business Problem

Netflix's raw content catalog is a flat CSV with 7,787 rows and 12 columns. In that form, it answers nothing. A content strategist asking *"Which genres should we invest in?"* or *"How has our library grown year over year?"* would need to manually filter, pivot, and chart the data in Excel — a slow, error-prone process.

This dashboard turns that raw file into an **interactive, always-on analytics tool** where every dropdown filter updates every visual simultaneously.

### ✅ What Was Built

A single-page Power BI dashboard with 8 visuals and 3 slicers covering content type, genre, country, release year, duration, and catalog growth — giving content and business teams a complete view of Netflix's library in one screen.

### 📢 Key Findings from the Real Data

| # | Finding | Stat |
|---|---|---|
| 1 | **Movies dominate the library** | 5,377 Movies (69%) vs 2,410 TV Shows (31%) |
| 2 | **USA produces the most content by far** | 2,555 titles — nearly 3× more than #2 (India at 923) |
| 3 | **India is Netflix's #2 content country** | 923 titles — ahead of UK (397), Japan (226), South Korea (183) |
| 4 | **2018 was the biggest release year** | 1,121 titles released — followed by 2017 (1,012) and 2019 (996) |
| 5 | **Netflix added the most content in 2019** | 2,136 titles added in 2019 alone — peak catalog expansion year |
| 6 | **International Movies is the #1 genre** | 2,437 titles — ahead of Dramas (2,106) and Comedies (1,471) |
| 7 | **TV-MA is the dominant rating** | 2,863 titles rated TV-MA — Netflix leans heavily toward mature content |
| 8 | **Average movie runtime is 99 minutes** | Range: 3 mins (shortest) to 312 mins (longest) |
| 9 | **Content additions surged post-2016** | 432 titles in 2016 → 1,661 in 2018 → 2,136 in 2019 — a 5× jump in 3 years |
| 10 | **South Korea's rise is clear in the data** | 183 titles — strong signal of the K-Drama wave Netflix capitalized on |

### 💼 Business Insights & Recommendations

1. **International content is Netflix's biggest bet** — with 2,437 International Movies as the top genre, the strategy of funding local-language content globally is deeply embedded in the catalog.
2. **The 2019 content peak tells a story** — 2,136 titles added that year represents Netflix's heaviest investment period, likely before the subscriber growth slowdown of 2021–22.
3. **Mature content (TV-MA) is the core audience** — 2,863 TV-MA titles vs 280 TV-Y titles shows Netflix prioritizes adult subscribers over family audiences in volume.
4. **India is a priority market** — 923 titles makes India the largest non-English content market, validating Netflix's aggressive India originals strategy.
5. **K-Drama momentum is real** — South Korea at 183 titles is disproportionately large for its population size — reflecting deliberate investment in a high-engagement content category.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Power BI Desktop** | Dashboard design, data modelling, all visuals |
| **Power Query (M Language)** | Data type corrections, date column parsing, genre splitting |
| **DAX (Data Analysis Expressions)** | Custom KPI measures and calculated columns |
| **CSV (Flat File)** | Single-table source data |

---

## 📐 DAX Measures Used

```dax
-- Total Titles
Total Titles = COUNT('NetFlix'[show_id])

-- Movies Count
Movies Count = CALCULATE(COUNT('NetFlix'[show_id]),
                'NetFlix'[type] = "Movie")

-- TV Shows Count
TV Shows Count = CALCULATE(COUNT('NetFlix'[show_id]),
                  'NetFlix'[type] = "TV Show")

-- Country Count
Country Count = DISTINCTCOUNT('NetFlix'[country])

-- Average Movie Duration
Avg Movie Duration =
CALCULATE(
    AVERAGE('NetFlix'[duration]),
    'NetFlix'[type] = "Movie"
)
```
## ❓ Common Interview Questions About This Project

**Q: What problem does this dashboard solve?**
A: It transforms a flat 7,787-row CSV into an interactive catalog analytics tool — letting content strategists answer questions about genre distribution, country production, content ratings, and catalog growth trends in seconds instead of hours.

**Q: What was your most interesting finding?**
A: That International Movies is the single largest genre on Netflix — bigger than Dramas and Comedies combined. It shows that Netflix's global-first content strategy isn't just marketing language — it's built directly into the catalog at scale.

**Q: Why Power BI over a simple Excel chart?**
A: All 8 visuals are connected through one data model. A single country dropdown filter updates every chart at once. You can't replicate that kind of cross-filtering cleanly in Excel.

**Q: What would you add with more data?**
A: Subscriber engagement data (watch hours, completion rate) to correlate content investment with actual viewership — moving from descriptive analytics (what's in the catalog) to prescriptive analytics (what should be added next).

---
## 📄 License

The Netflix dataset used in this project is publicly available for educational and portfolio purposes.

---

> ⭐ If this project helped you or gave you ideas, consider giving it a star on GitHub!
