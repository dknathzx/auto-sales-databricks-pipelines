# Auto Sales Analytics Pipeline

## 🎯 Project Overview
Production-ready data pipeline built on Databricks with CI/CD automation using GitHub Actions.

### Pipeline Architecture
```
CSV Data → Bronze Layer → Silver Layer → Gold Layer → Analytics Tables
```

**Medallion Architecture:**
- **Bronze Layer**: Raw data ingestion (2,747 sales records)
- **Silver Layer**: Data cleaning and transformation
- **Gold Layer**: Business analytics (5 tables)

## 📊 Analytics Tables Created
1. `gold_sales_by_product_line` - Product performance metrics
2. `gold_sales_by_country` - Geographic sales analysis
3. `gold_monthly_sales_trends` - Time-series analysis
4. `gold_deal_size_analysis` - Deal segmentation
5. `gold_executive_dashboard` - Executive KPIs

## 🚀 Features
- ✅ Automated CI/CD pipeline with GitHub Actions
- ✅ Multi-environment deployment (DEV/STAGING/PROD)
- ✅ Data quality monitoring
- ✅ Complete data lineage tracking
- ✅ Delta Lake for ACID transactions
- ✅ Unity Catalog integration

## 🏗️ Repository Structure
```
auto-sales-databricks-pipeline/
├── .github/
│   └── workflows/
│       └── databricks-cicd.yml    # GitHub Actions workflow
├── notebooks/
│   ├── 01_bronze_ingestion.py     # Bronze layer notebook
│   ├── 02_silver_cleaning.py      # Silver layer notebook
│   └── 03_gold_analytics.py       # Gold layer notebook
├── config/
│   ├── dev.json                   # Development environment config
│   ├── staging.json               # Staging environment config
│   └── prod.json                  # Production environment config
├── tests/
│   └── test_data_quality.py       # Automated tests
├── .gitignore                      # Git ignore rules
└── README.md                       # This file
```

## 🔧 Setup Instructions

### 1. GitHub Secrets Configuration
Add these secrets in GitHub Settings → Secrets → Actions:
- `DATABRICKS_HOST`: Your Databricks workspace URL
- `DATABRICKS_TOKEN`: Personal access token from Databricks

### 2. Databricks Setup
1. Create three catalogs/schemas: `dev`, `staging`, `prod`
2. Upload source data to Unity Catalog volume
3. Configure cluster policies

### 3. Running the Pipeline

**Manually in Databricks:**
```python
# Run notebooks in sequence:
1. 01_bronze_ingestion.py
2. 02_silver_cleaning.py
3. 03_gold_analytics.py
```

**Via Databricks Job:**
- Job Name: "Auto Sales Analytics Pipeline"
- Runs all 3 notebooks in sequence
- Duration: ~1-2 minutes

**Via CI/CD (Automated):**
- Push to `develop` branch → Deploys to DEV
- Push to `main` branch → Deploys to PROD

## 📈 Key Metrics
- **Total Records Processed**: 2,747
- **Pipeline Run Time**: 1m 14s
- **Data Quality Score**: 99%+
- **Number of Analytics Tables**: 5

## 🔄 CI/CD Pipeline Flow
```
Code Commit → GitHub Actions Triggered → Run Tests → Deploy to Environment → Verify Deployment
```

## 👥 Team
- **Developer**: [Your Name]
- **Project**: Databricks Data Engineering Demo

## 📝 License
Internal Use Only
