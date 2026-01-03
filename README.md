# Superstore Data Warehouse & BI Dashboards

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](#)
[![Pentaho PDI](https://img.shields.io/badge/Pentaho%20PDI-0A4A9E?style=for-the-badge&logo=pentaho&logoColor=white)](#)
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)

An end-to-end BI solution built on a star-schema warehouse with ETL pipelines and interactive dashboards for the Superstore dataset

The primary goal is to provide a structured environment for analyzing "Superstore" data to uncover trends and improve operational decision-making.

## Highlights

* **Data Warehouse**: Star schema centered on `fact_sale` with well-defined dimensions.
* **ETL Workflows**: Pentaho jobs for dimension and fact processing.
* **Dashboards**: Visual narratives for Customer, Product, Sales, and Shipping.


## Tech Stack

* **Database**: PostgreSQL (Data Warehousing)
* **ETL Tool**: Pentaho Data Integration (PDI)
* **Visualization**: Power BI


## Data Model

The project utilizes a **Star Schema** design to optimize analytical queries, consisting of a central fact table and multiple dimension tables.

### Schema Components

* **Fact Table (`fact_sale`)**: Quantitative measures (sales, order/ship dates) and derived `days_diff` for delivery time.
* **Dimension Tables**:

  * **`dim_product`**: Category, sub-category, and product details.
  * **`dim_customer`**: Customer demographics and segments (Consumer, Corporate, Home Office), plus geography.
  * **`dim_ship`**: Shipping modes (e.g., Second Class, Standard Class) and related attributes.


## ETL Workflows

Pentaho transformations orchestrate consistent, repeatable processing.

1. **Dimension Processing**: Rename/clean columns, encode labels, remove duplicates, normalize data types for Customer, Product, and Shipping.
2. **Fact Processing**: Map surrogate keys from dimensions to the sales fact table and compute `days_diff` for delivery metrics.

Open the workflows:

* Dimension load: [etl-superstore/load_dim_customer.ktr](etl-superstore/load_dim_customer.ktr)
* Fact load: [etl-superstore/load_fact_sales.ktr](etl-superstore/load_fact_sales.ktr)


## Visualizations & Insights

Interactive dashboards highlight business performance:

* **Customer Analysis**: Breakdown of customers by segment and geographical heatmaps showing top cities and states.
* **Product Performance**: Analysis of sales distribution across categories and sub-categories.
* **Sales Trends**: Evaluation of sales volume over years and quarters, and delivery time efficiency.


## Dashboards

Below are snapshot views of the interactive dashboards used in the project. For the best experience, open these images to view at full resolution.

* **Overview**
  ![Dashboard 1 - Overview](assets/v1.jpg)

* **Product Performance** — category/sub-category trends and revenue contribution
  ![Dashboard 2 - Product Performance](assets/v3.jpg)

* **Sales Trends** — year/quarter dynamics and seasonality patterns
  ![Dashboard 3 - Sales Trends](assets/v4.jpg)

* **Sales by City** — top cities driving revenue
  ![Dashboard 4 - Sales by City](assets/v5.jpg)


## Team

This project was presented our team at the **Institute of Technology of Cambodia**, Department of Applied Mathematics and Statistics.

* **Lecturer**: Mr. Ngin Kimlong
* **Team Members**: Pheth Soriyuon, Phoeun Rajame, Phoeurn Kimhor, Pich Daraphal

