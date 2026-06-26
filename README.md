# 🚴 AdventureWorks Sales Analytics — Power BI Dashboard

A comprehensive **end-to-end Power BI project** built on the AdventureWorks dataset, covering data modeling, DAX measures, and interactive sales reporting across three fiscal years (2020–2022).

---

## 📊 Project Overview

This project transforms raw transactional CSV data from AdventureWorks (a fictional bicycle and accessories company) into a fully interactive Power BI report. It demonstrates a complete BI workflow — from data ingestion and star-schema modeling to KPI dashboards and drill-through analysis.

| Metric | Value |
|---|---|
| **Sales Period** | Jan 2020 – Jun 2022 |
| **Total Orders** | ~56,000+ |
| **Customers** | 18,151 |
| **Products** | 293 |
| **Sales Territories** | 10 (North America, Europe, Pacific) |
| **Product Categories** | 4 (Bikes, Components, Clothing, Accessories) |

---

## 📁 Repository Structure

```
AdventureWorks-PowerBI/
│
├── demo.pbix                                      # Main Power BI report file
│
├── data/
│   ├── AdventureWorks_Sales_Data_2020.csv         # Sales transactions — 2020
│   ├── AdventureWorks_Sales_Data_2021.csv         # Sales transactions — 2021
│   ├── AdventureWorks_Sales_Data_2022.csv         # Sales transactions — Jan–Jun 2022
│   ├── AdventureWorks_Returns_Data.csv            # Product return records
│   ├── AdventureWorks_Customer_Lookup.csv         # Customer dimension table
│   ├── AdventureWorks_Product_Lookup.csv          # Product dimension table
│   ├── AdventureWorks_Product_Categories_Lookup.csv
│   ├── AdventureWorks_Product_Subcategories_Lookup.csv
│   ├── AdventureWorks_Territory_Lookup.csv        # Sales territory dimension
│   └── AdventureWorks_Calendar_Lookup.csv         # Date dimension table
│
└── README.md
```

---

## 🗂️ Data Model

The report is built on a **star schema** with a central fact table connected to multiple dimension tables via key relationships.

### Fact Tables

| Table | Rows | Key Fields |
|---|---|---|
| Sales Data (2020–2022) | ~56,047 | OrderDate, ProductKey, CustomerKey, TerritoryKey, OrderQuantity |
| Returns Data | ~1,809 | ReturnDate, ProductKey, TerritoryKey, ReturnQuantity |

### Dimension Tables

| Table | Rows | Description |
|---|---|---|
| Customer Lookup | 18,151 | Demographics: income ($10K–$170K), occupation, education, gender |
| Product Lookup | 293 | SKU, pricing ($2.29–$3,578.27), cost, color, size |
| Product Categories | 4 | Bikes, Components, Clothing, Accessories |
| Product Subcategories | 37 | Granular product groupings |
| Territory Lookup | 10 | Regions across North America, Europe, and Pacific |
| Calendar Lookup | 912 | Full date table for time intelligence |

### Relationships

```
Calendar ──────────────► Sales (OrderDate)
Customer ──────────────► Sales (CustomerKey)
Product ───────────────► Sales (ProductKey)
Territory ─────────────► Sales (TerritoryKey)
Product Subcategories ─► Product (ProductSubcategoryKey)
Product Categories ────► Product Subcategories (ProductCategoryKey)
Product ───────────────► Returns (ProductKey)
Territory ─────────────► Returns (TerritoryKey)
```

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Report development & data modeling
- **Power Query (M)** — Data transformation and cleaning
- **DAX** — Calculated columns, measures, and KPIs
- **CSV** — Source data format


## 🤝 Contributing

Contributions, suggestions, and improvements are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-analysis`)
3. Commit your changes (`git commit -m 'Add customer segmentation page'`)
4. Push to the branch (`git push origin feature/new-analysis`)
5. Open a Pull Request


## 👤 Author

**\< sanjay kumar \>**  
📧 \<bsanjaykumar.work@gmail.com\>  
🔗 [LinkedIn](www.linkedin.com/in/sanjaykumar-data-science) · [GitHub](https://github.com/bsanjaykumar-ds)

*If you found this project helpful, please ⭐ star the repository!*
