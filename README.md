````markdown
# NHS Research Systems – Process Analysis & BI Platform

**One-stop demo** of how an HRA / NHS Business Analyst can:

- Map “As-Is” research approval & income workflows (IRAS/HARP → BI platform)  
- Cleanse SUS / HES data in SQL  
- Apply NTPS 2025/26 tariffs (HRG + CQUIN baked-in)  
- Surface live KPIs & variance in Power BI  
- Support UAT with user stories & acceptance criteria  

---

## 🔧 Quick-Start (Local)

1. **Clone & enter repo**  
   ```bash
   git clone https://github.com/<your-user>/NHS-Research-BI-Platform.git
   cd NHS-Research-BI-Platform
````

2. **Deploy schema & ETL**

   * PostgreSQL:

     ```bash
     psql -f sql/00_create_schema.sql
     psql -f sql/01_load_data.sql
     psql -f sql/02_clean_transform.sql
     psql -f sql/03_income_view.sql
     ```
   * SQL Server (T-SQL):

     ```sql
     :r .\sql\00_create_schema.sql
     :r .\sql\01_load_data.sql
     :r .\sql\02_clean_transform.sql
     :r .\sql\03_income_view.sql
     ```
3. **Open & refresh**

   * Launch **Power BI Desktop**
   * Open `pbix/NHS_Dashboard.pbix` → Refresh All
4. **Explore**

   * Navigate pages: Income Monitoring | Activity Trends | Tariff Issues | Forecasting | Data Quality

---

## 📂 Folder Guide

| Folder    | Contents                                         |
| --------- | ------------------------------------------------ |
| **data/** | Mock SUS & HES CSV samples + `tariffs_25_26.csv` |
| **sql/**  | DDL & ETL scripts:                               |

* `00_create_schema.sql`
* `01_load_data.sql`
* `02_clean_transform.sql`
* `03_income_view.sql` |
  \| **pbix/**  | Power BI file template: `NHS_Dashboard.pbix`                      |
  \| **docs/**  | Business-Analysis artefacts:
* As-Is & To-Be process maps (`.png`)
* User Stories & UAT log (`.xlsx`)
* Sample PDF report (`.pdf`) |
  \| **img/**   | Dashboard screenshots for README (`.png`)                         |
  \| **README.md** | This document                                               |
  \| **.gitignore** | OS/IDE/Power BI cruft exclusions                         |
  \| **LICENSE**   | MIT license                                                   |

---

## 📊 Sample Screenshots

![Income Monitoring view](img/income_view.png)
*Income vs Target, Variance flags by Commissioner*

![Data Quality Alerts](img/data_quality.png)
*Missing HRG codes & data-quality KPI*

---

## 📋 Business-Analysis Artefacts

1. **Process Maps**

   * `docs/ProcessMap_AsIs.png`
   * `docs/ProcessMap_ToBe.png`

2. **User Stories & UAT**

   * `docs/UserStories_UAT.xlsx`

3. **Monthly Report Sample**

   * `docs/Monthly_Report_Sample.pdf`

---

## 🚀 Next Steps & Ideas

* Swap mock CSVs with real NHS HES extracts for larger-scale testing
* Add **role-based security** in Power BI (one view per Commissioner)
* Implement **Python ARIMA** forecasting in a Power BI Python visual
* Deploy to Power BI Service and set up **email subscriptions**

---

## 📝 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

*Built by @<your-handle>, 2025*

```
::contentReference[oaicite:0]{index=0}
```
