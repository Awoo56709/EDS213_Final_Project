# EDS213_Final_Project - Does Price Predict Quality in French Wine?

## Purpose

This project explores whether wine price is a reliable predictor of 
quality using reviews from Wine Magazine. Using a 
relational database of three tables and over 200,000 observations, 
I queried and visualized the relationship between price and rating 
for French wines specifically — and identified the best-value 
bottles under $20.

This was completed as part of EDS 213: Databases and Data Management 
at the Bren School of Environmental Science & Management, UCSB.

## Repoaitory Structure

```
EDS213_FINAL_PROJECT/
├── README.md
├── requirements.txt
├── .gitignore
├── EDS213_Final_Project.Rproj
├── data/
│   ├── raw/
│   │   ├── GRAPE_QUALITY.csv
│   │   ├── vivino_wines_2026.csv
│   │   ├── winemag-data_first150k.csv
│   │   └── winemag-data-130k-v2.csv
│   └── clean/
│       ├── grape_quality_clean.csv
│       ├── vivino_clean.csv
│       └── winemag_clean.csv
├── database/
│   └── wine_database.duckdb
├── scripts/
│   ├── 01_cleaning_ingestion.qmd    # renamed from exploratory.qmd
│   ├── 02_queries.sql               # renamed from database_queries
│   └── 03_analysis_visualization.ipynb  # renamed from final_project_query
└── outputs/
    └── figures/
        └── schema_diagram.pdf
        
```

# Data Access

- **Wine Magazine Reviews** — two CSV files totaling about 280k rows 
  of wine reviews including variety, price, points, region, and winery. Source: 
  [Kaggle - Wine Reviews](https://www.kaggle.com/datasets/zynicide/wine-reviews)

- **Vivino Wines 2026** — consumer ratings and wine metadata 
  including wine type, region, and natural wine (binary). Source: 
  [Kaggle - Vivino Wines](https://www.kaggle.com/datasets/mrbridge/vivino-wine-ratings-2026)

- **Grape Quality** — environmental metrics per grape variety and 
  region including brix, pH, soil moisture, and rainfall. 
  *Note*: this dataset was found to be synthetic during analysis 
  and was excluded from the final analytical question. [Kaggle - Grape Quality](https://www.kaggle.com/datasets/meheralimeer/wine-quality-dataset
  )

Raw data files are included in the `data/` folder. Cleaned versions are in `clean/`. The DuckDB database file is in `database/`.

1. Clone the repository
2. Install dependencies (see `requirements.txt`)
3. Run `exploratory.qmd` in RStudio to clean data and build the database
4. Open `final_project_query.ipynb` in Jupyter or VS Code to run queries and generate visualizations

> Note: If `wine_database.duckdb` is already present, skip step 3. 
> Only one process can access the DuckDB file at a time — do not 
> open it in RStudio and VS Code simultaneously.

## References & Acknowledgements

- Course: EDS 213 — Databases and Data Management, UCSB Bren School. 
  [Course website](https://ucsb-library-research-data-services.github.io/bren-eds213/)

