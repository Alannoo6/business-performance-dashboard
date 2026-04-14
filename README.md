\# Business Performance Dashboard (Power BI) – Financial \& Inventory Analysis | Espacio Bazar



\## Overview

This project presents an interactive Power BI dashboard for comprehensive business performance analysis of the Espacio Bazar unit at Brandteam, covering billing, collections, customer debt, inventory, projected stock, and valued stock — based on real operational data.



The dashboard enables unified monitoring of financial and inventory KPIs across multiple dimensions, supporting data-driven decision-making for commercial, financial, and operations teams.



It includes customer debt aging analysis, collections tracking, billing performance, stock level monitoring, projected inventory and valued stock views, with dynamic filters to identify risks and optimization opportunities.



> \*\*Disclaimer:\*\* All datasets, table names, business identifiers, and sensitive information have been fully anonymized to preserve confidentiality and comply with corporate data protection policies. This repository is for demonstration purposes only.



\---



\## Business Problem

Finance and operations teams require consolidated, reliable visibility over business performance across multiple areas to:

\- Monitor billing and collections in a unified view

\- Track customer debt aging and outstanding balances

\- Control current stock levels and projected inventory

\- Evaluate valued stock for financial reporting

\- Support operational and strategic decision-making



This dashboard centralizes transactional data from multiple business areas into a single analytical model to deliver a unified, interactive reporting solution.



\---



\## Project Objective

Develop a management dashboard to monitor financial and inventory performance, enabling analysis of billing, collections, customer debt, and stock indicators across multiple dimensions.



The goal is to provide a flexible analytical tool that allows business users to explore performance indicators, detect risks, and make data-driven decisions.



\---



\## Data Architecture \& Flow

The analytical workflow follows a standard BI pipeline:



```

SQL Server → Power Query (ETL) → Power BI Semantic Model → Dashboard

```



\- Extraction of transactional data from SQL Server (billing, collections, debt, inventory)

\- Data transformation and cleansing using Power Query (M language)

\- Semantic model built with relationships and calculated measures in DAX

\- KPI and performance indicator visualization in Power BI



This approach ensures data consistency between transactional systems and analytical reporting, maintaining scalable and reusable data models.



\---



\## Data Model

The semantic model is built on a star schema structure connecting fact and dimension tables across the main business areas.



> 📎 Data model diagram — coming soon



\### Main Model Tables



| Table | Type | Description |

|-------|------|-------------|

| Fact\_Sales | Fact | Sales transactions by date, customer, and product |

| Fact\_Collections | Fact | Payments received and collector tracking |

| Fact\_Invoices | Fact | Invoice status, due dates, and financial aging |

| Fact\_StockMovements | Fact | Inbound and outbound stock movements |

| Fact\_Stock | Fact | Current stock levels by product and warehouse |

| Fact\_StockValuation | Fact | Stock valued at cost and sale price |

| Fact\_Purchases | Fact | Purchase orders and delivery tracking |

| Fact\_Deliveries | Fact | Units delivered and conversion factors |

| Dim\_Calendar | Dimension | Date table for time intelligence |

| Dim\_Product | Dimension | Item master with family and category |

| Dim\_BusinessUnit | Dimension | Business unit and item type classification |

| Dim\_Province | Dimension | Geographic dimension with country and province |

| Dim\_Region | Dimension | Regional grouping by province |



\---



\## Dashboard Preview

Selected screenshots from the interactive Power BI dashboard. All data has been anonymized for confidentiality and demonstration purposes.



\### Cover

!\[Cover](dashboard/screenshots/01\_cover.png)



\### Commercial Performance

!\[Commercial Performance](dashboard/screenshots/02\_commercial\_performance.png)



\### Accounts Receivable

!\[Accounts Receivable](dashboard/screenshots/03\_accounts\_receivable.png)



\### Overdue Balance

!\[Overdue Balance](dashboard/screenshots/04\_overdue\_balance.png)



\### Collections

!\[Collections](dashboard/screenshots/05\_collections.png)



\### Inventory Control

!\[Inventory Control](dashboard/screenshots/06\_inventory\_control.png)



\### Inventory Valuation

!\[Inventory Valuation](dashboard/screenshots/07\_inventory\_valuation.png)



\---



\## Business Impact

This dashboard contributes to:

\- Improving visibility over financial performance in billing and collections

\- Identifying overdue customer debt and risk concentration by aging

\- Monitoring stock availability and preventing inventory stockouts

\- Supporting valued stock for financial reporting

\- Reducing manual reporting effort by centralizing analysis in a single platform

\- Improving data quality and consistency for management reporting



\---



\## Key Features

\- Interactive dashboards with dynamic filters and slicers

\- Billing and collections performance monitoring

\- Customer debt aging analysis with segmentation by due date

\- Current stock and projected inventory views

\- Valued stock reporting

\- Time intelligence calculations for trend analysis

\- KPI monitoring across financial and operational dimensions



\---



\## Technologies Used



| Technology | Usage |

|------------|-------|

| SQL Server | Data extraction and base dataset construction |

| Power Query (M) | Data transformation and ETL layer |

| Power BI | Data visualization and interactive dashboards |

| DAX | Measures and business logic for advanced analytics |

| GitHub | Version control and project documentation |



\---



\## Dataset Preparation

Data was extracted from transactional databases hosted in SQL Server, covering billing, collections, debt, and inventory tables.



SQL scripts were developed to build the base datasets used as data sources in Power BI. Power Query was then used to apply transformations, cleanse data, and shape tables for the analytical model.



SQL scripts used in this stage are located in:

```

sql/

```



Power Query transformations are documented in:

```

powerquery/

```



\---



\## DAX Measures \& Business Logic

DAX measures were implemented to calculate key performance indicators across financial and inventory areas, including:

\- Billing totals and period-over-period variances

\- Collection rate and outstanding balance tracking

\- Customer debt aging and overdue concentration

\- Stock coverage and projected inventory calculations

\- Stock valuation at cost and sale price

\- Time intelligence calculations (MTD, YTD, rolling periods)



Implemented measures are located in:

```

dax/

```



\---



\## Repository Structure



```

business-performance-dashboard/

│

├── sql/                    # SQL scripts for data extraction

├── powerquery/             # Power Query transformation scripts (M)

├── dax/                    # DAX measures and business logic

├── data\_model/             # Data model diagram and documentation

├── dashboard/              # Dashboard screenshots (anonymized)

│   └── screenshots/

│       ├── 01\_cover.png

│       ├── 02\_commercial\_performance.png

│       ├── 03\_accounts\_receivable.png

│       ├── 04\_overdue\_balance.png

│       ├── 05\_collections.png

│       ├── 06\_inventory\_control.png

│       └── 07\_inventory\_valuation.png

├── docs/                   # Additional documentation

│   └── data\_dictionary.md  # Table and field descriptions

└── README.md

```



\---



\## Roadmap (Optional Improvements)

\- Add incremental refresh for large historical datasets

\- Implement Row-Level Security (RLS) for role-based access

\- Extend the model with profitability and margin analysis

\- Integrate automated refresh flows and monitoring

\- Add what-if parameters for stock projection scenarios



