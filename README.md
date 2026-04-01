# 🛒 Retail Sales & Customer Analysis

> End-to-end data analytics project covering Exploratory Data Analysis (EDA), an interactive Power BI dashboard, and a business presentation — built on a star-schema retail dataset.

---

## 📌 Project Overview

This project performs a full analysis of retail sales data to extract actionable insights around **sales performance**, **customer behavior**, and **operational efficiency**. It is designed to support data-driven decision-making for business growth.

**Author:** Jatindra Patel  
**Tools Used:** Python, Pandas, NumPy, Matplotlib, Plotly, Power BI, Google Colab  

---

## 🎯 Business Objectives

- 🏆 Identify top-performing products and categories
- 📈 Analyze sales trends over time
- 👥 Find high-value customers
- 💸 Evaluate discount effectiveness
- 🚚 Analyze shipping performance
- 🔄 Understand customer purchasing behavior

---

## 📁 Project Structure

```
Retail-Sales-Customer-Analysis/
│
├── data/                          # Raw datasets (star schema)
│   ├── Fact_Sales.csv             # Fact table — 2,155 sales records
│   ├── orders.csv                 # 830 orders
│   ├── order_details.csv          # Line items per order
│   ├── customers.csv              # 91 customers across multiple countries
│   ├── products.csv               # 77 products
│   ├── categories.csv             # 8 product categories
│   └── shippers.csv               # 3 shipping companies
│
├── notebooks/
│   └── EDA.ipynb                  # Exploratory Data Analysis notebook
│
├── dashboard/
│   └── Retail_Sales_Dashboard.pbix  # Power BI interactive dashboard
│
├── reports/
│   ├── Business_Requirement_Document.docx   # BRD with project scope & KPIs
│   └── Dashboard_Report.docx                # Narrative summary of findings
│
├── presentation/
│   └── Retail_Sales_Presentation.pptx  # Stakeholder presentation deck
│
├── .gitignore
└── README.md
```

---

## 🗃️ Data Schema

This dataset follows a **Star Schema** design:

```
                   ┌─────────────┐
                   │  categories │
                   └──────┬──────┘
                          │
┌──────────┐    ┌─────────▼──────────┐    ┌──────────┐
│ customers │◄───│    Fact_Sales      │───►│ shippers │
└──────────┘    │                    │    └──────────┘
                │ - OrderID          │
┌──────────┐    │ - ProductID        │    ┌──────────┐
│  orders  │◄───│ - CustomerID       │───►│ products │
└──────────┘    │ - ShipperID        │    └──────────┘
                │ - SalesAmount      │
┌──────────────┐│ - Quantity         │
│order_details │└────────────────────┘
└──────────────┘
```

| Table | Rows | Key Columns |
|---|---|---|
| `Fact_Sales` | 2,155 | OrderID, ProductID, CustomerID, SalesAmount, Quantity, Discount |
| `orders` | 830 | OrderID, CustomerID, OrderDate, ShipperID, Freight |
| `order_details` | 2,155 | OrderID, ProductID, UnitPrice, Quantity, Discount |
| `customers` | 91 | CustomerID, CompanyName, Country, City |
| `products` | 77 | ProductID, ProductName, UnitPrice, CategoryID |
| `categories` | 8 | CategoryID, CategoryName |
| `shippers` | 3 | ShipperID, CompanyName |

---

## 🔍 Analysis Highlights (EDA Notebook)

The `notebooks/EDA.ipynb` covers:

1. **Data Cleaning & Preparation** — handling nulls, data types, deduplication
2. **Sales Trend Analysis** — monthly and yearly revenue trends
3. **Top Products & Categories** — best sellers by revenue and quantity
4. **Customer Segmentation** — high-value customers, purchase frequency
5. **Discount Effectiveness** — correlation between discounts and revenue
6. **Shipping Analysis** — shipper performance and freight costs

---

## 📊 Power BI Dashboard

The `dashboard/Retail_Sales_Dashboard.pbix` file contains an interactive Power BI report with:

- KPI cards (Total Revenue, Orders, Customers, Avg Order Value)
- Sales over time (line chart)
- Top products & categories (bar charts)
- Customer map (geographic distribution)
- Shipper performance comparison

> **Requires:** Power BI Desktop ([Download here](https://powerbi.microsoft.com/desktop/))

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/Retail-Sales-Customer-Analysis.git
cd Retail-Sales-Customer-Analysis
```

### 2. Run the EDA Notebook

**Option A — Google Colab (Recommended)**
Upload `notebooks/EDA.ipynb` to [Google Colab](https://colab.research.google.com/) and upload the `data/` files when prompted.

**Option B — Local**
```bash
pip install pandas numpy matplotlib plotly jupyter
jupyter notebook notebooks/EDA.ipynb
```

### 3. Open the Power BI Dashboard
Open `dashboard/Retail_Sales_Dashboard.pbix` in **Power BI Desktop**.

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| Data Analysis | Python, Pandas, NumPy |
| Visualization | Matplotlib, Plotly |
| BI Dashboard | Microsoft Power BI |
| Notebook | Jupyter / Google Colab |
| Documentation | MS Word, PowerPoint |

---

## 📄 Reports & Documents

| File | Description |
|---|---|
| `reports/Business_Requirement_Document.docx` | Defines business goals, KPIs, and data requirements |
| `reports/Dashboard_Report.docx` | Written summary of dashboard insights and findings |
| `presentation/Retail_Sales_Presentation.pptx` | Stakeholder-ready slide deck |

---

## 📜 License

This project is for educational and portfolio purposes.  
Dataset sourced from a publicly available retail dataset (Northwind-style schema).

---

## 🙋‍♂️ Author

**Jatindra Patel**  
📧 [jatindrapatel9893@gmail.com]  
🔗 [LinkedIn](linkedin.com/in/jatindrapatel) | [GitHub](https://github.com/JatindraPatel)
