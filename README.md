# COVID-19 Data Analysis — Experiments 19 & 20

---

## Project Overview

This project performs an Exploratory Data Analysis (EDA) on the COVID-19 global dataset. The analysis covers confirmed cases, deaths, recoveries, and active cases across countries and Indian states — based on data up to **May 29, 2021**.

---

## Dataset

| Property | Details |
|---|---|
| **File** | `covid_19_data.csv` |
| **Source** | Johns Hopkins University / Kaggle COVID-19 Dataset |
| **Records** | 306,429 rows |
| **Latest Date** | May 29, 2021 |
| **Countries Covered** | 195 unique countries/regions |

### Columns Used

| Column | Description |
|---|---|
| `ObservationDate` | Date of the observation |
| `Province/State` | Province or state |
| `Country/Region` | Country or region name |
| `Confirmed` | Cumulative confirmed cases |
| `Deaths` | Cumulative death count |
| `Recovered` | Cumulative recovered cases |
| `Active` | Derived: Confirmed − Recovered − Deaths |

> **Note:** `SNo` and `Last Update` columns were dropped as they are not needed for analysis.

---

## Tech Stack

- **Platform:** Google Colab
- **Language:** Python 3
- **Libraries:**
  - `pandas` — Data loading, cleaning, and manipulation
  - `numpy` — Numerical operations
  - `plotly.express` — Interactive world map visualization

---

## Analysis Performed

### 1. Data Loading & Preprocessing
- Loaded the dataset using `pandas`
- Dropped irrelevant columns (`SNo`, `Last Update`)
- Converted `ObservationDate` to `datetime64`, and `Confirmed`, `Deaths`, `Recovered` to `int64`

### 2. Active Cases Feature Engineering
- Created a new derived column: `Active = Confirmed - Recovered - Deaths`

### 3. Latest Date Extraction
- Identified the most recent date in the dataset: **May 29, 2021**
- Filtered data to only the latest date for country-level analysis

### 4. Country-wise Analysis
- Counted unique countries/regions in the latest data
- Grouped by `Country/Region` to get total Confirmed, Deaths, Recovered, and Active cases
- Looked up specific countries: **India**, **Mainland China**, **US**
- Found the **Top 5 countries** by confirmed cases

### 5. World Map Visualization
- Plotted a choropleth world map using `plotly.express` with confirmed cases per country
- Color scale: `pinkyl`, range: 0 to 10,000,000

### 6. India-specific Analysis
- Filtered dataset for India only
- Handled missing `Province/State` values by filling with `"Unknown"`
- Extracted India's latest date data
- Grouped by state to find top states by confirmed cases
- Found the **state with the maximum confirmed cases**

---

## Key Findings

### Country-wise Cases (as of May 29, 2021)

| Country | Confirmed | Deaths | Recovered | Active |
|---|---|---|---|---|
| India | 27,894,800 | 325,972 | 25,454,320 | 2,114,508 |
| Mainland China | 91,072 | 4,636 | 86,117 | 319 |
| US | 33,251,939 | 594,306 | 0 | 32,657,633 |

### Top 5 Countries by Confirmed Cases

| Rank | Country | Confirmed | Recovered |
|---|---|---|---|
| 1 | US | 33,251,939 | 0 |
| 2 | India | 27,894,800 | 25,454,320 |
| 3 | Brazil | 16,471,600 | 14,496,224 |
| 4 | France | 5,719,877 | 390,878 |
| 5 | Turkey | 5,235,978 | 5,094,279 |

### 🇮🇳 Top 5 Indian States by Confirmed Cases

| Rank | State | Confirmed | Recovered |
|---|---|---|---|
| 1 | **Maharashtra** | 5,713,215 | 5,339,838 |
| 2 | Karnataka | 2,567,449 | 2,189,064 |
| 3 | Kerala | 2,494,385 | 2,252,505 |
| 4 | Tamil Nadu | 2,039,716 | 1,706,298 |
| 5 | Uttar Pradesh | 1,688,152 | 1,621,743 |

> **Maharashtra** had the highest number of confirmed cases among all Indian states with **5,713,215** cases.

---

## 📁 Project Structure

```
covid19-eda/
│
├── covid_19_data.csv            # Raw dataset
├── experiments19_20.ipynb       # Main Colab Notebook
└── README.md                    # Project documentation (this file)
```

---

## Conclusion

This analysis of the COVID-19 dataset reveals the scale and geographic spread of the pandemic up to May 29, 2021. By preprocessing the data and engineering an Active Cases column, we were able to get a clearer picture of the real-time burden on each country beyond just raw confirmed counts.

The **United States** led globally with over **33.2 million confirmed cases**, followed by **India** at **27.9 million** and **Brazil** at **16.4 million**, highlighting that the pandemic was heavily concentrated in a handful of large nations. The choropleth world map visualization made this disparity immediately visible across all 195 countries.

Within India, the state-level analysis showed that **Maharashtra** was the worst-affected state with over **5.7 million confirmed cases** — significantly higher than any other state — pointing to the need for localized response strategies rather than a one-size-fits-all national approach.

Overall, this project demonstrates how basic data wrangling and visualization techniques can surface meaningful public health insights from large real-world datasets.

---
