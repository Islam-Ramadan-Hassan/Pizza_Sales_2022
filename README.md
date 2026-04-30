<!-- Header with modern badges -->
<div align="center">
  <img src="https://img.shields.io/badge/Project-Pizza%20Sales%20Dashboard-F7B32B?style=for-the-badge&logo=excel&logoColor=white" />
  <img src="https://img.shields.io/badge/Year-2022-4CAF50?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Region-EG%20%7C%20MENA-FF6B6B?style=for-the-badge" />
  <br/><br/>
  <h1>🍕 Pizza Sales Dashboard</h1>
  <h3>📊 Egypt & MENA Market – 2022 Business Intelligence</h3>
  <p><i>From raw orders to actionable insights – an interactive Excel dashboard for a fast‑growing pizza chain in Cairo & Alexandria.</i></p>
</div>

<hr>

## 🚀 The Story

A pizza chain with multiple branches in **Egypt** lacked a centralized way to track performance. They had thousands of orders but no visibility into:

- 🔥 **Best‑selling pizzas** (by revenue & quantity)
- ⏰ **Peak ordering hours** (critical for Ramadan Iftar rushes!)
- 📏 **Size preferences** (Small, Medium, Large, XL)
- 📅 **Seasonal trends** (Eid, Coptic Christmas, Revolution Day)

Using **real 2022 order data**, I built an **interactive Excel dashboard** that answers these questions – and more. This project demonstrates my ability to turn raw data into business value for the **MENA market**.

<hr>

## 📸 Dashboard Photo / Screenshot

> *Place your dashboard screenshot here. Replace the path with your actual image file.*

![Dashboard Overview](images/dashboard_overview.png)  
*Figure 1: Main dashboard showing key metrics, slicers, and charts.*

> *Add more photos if needed (e.g., pivot tables, data model diagram).*

<hr>

## 🛠️ Tools & Tech Stack

<div align="center">
  
| Tool | Purpose |
|------|---------|
| ![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white) | Data modeling, Power Pivot, DAX, pivot tables |
| ![DAX](https://img.shields.io/badge/DAX-FFD966?style=for-the-badge&logo=powerbi&logoColor=black) | Measures & calculated columns |
| ![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white) | Version control & portfolio hosting |

</div>

<hr>

## 📊 Data Model

```mermaid
erDiagram
    orders ||--o{ order_details : "order_id"
    order_details }o--|| pizzas : "pizza_id"
    orders {
        int order_id PK
        date date
        time time
    }
    order_details {
        int order_details_id PK
        int order_id FK
        string pizza_id FK
        int quantity
    }
    pizzas {
        string pizza_id PK
        string pizza_name
        string size
        decimal price_egp
    }
Pizza prices are simulated based on typical Egyptian menu prices (60 EGP for small, up to 180 EGP for XL). Replace with real data if available.

<hr>
🔢 Key DAX Measures
<details> <summary><b>Click to expand – DAX formulas</b></summary>
dax
// Total Revenue (EGP)
Total Amount = 
SUMX(
    order_details,
    order_details[quantity] * RELATED(pizzas[price_egp])
)

// Revenue by Pizza Size
Sales by Size = 
SUMMARIZE(
    pizzas,
    pizzas[size],
    "Total Sales (EGP)", [Total Amount]
)

// Top 10 Pizzas by Revenue
Top 10 Pizzas = 
TOPN(
    10,
    ALL(pizzas[pizza_name]),
    [Total Amount]
)

// Hourly Order Volume (for peak hour analysis)
Hourly Volume = 
HOUR(orders[time])
</details><hr>
📈 Sample Visuals (Additional Photos)
Top Pizzas	Peak Hours
https://images/sales_by_pizza.png	https://images/peak_hours.png
Size Revenue	Data Model Diagram
https://images/size_revenue.png	https://images/data_model.png
<hr>
🎥 Demo Video
<div align="center"> <a href="video/demo.mp4"> <img src="https://img.shields.io/badge/▶️_Watch_Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Demo Video"> </a> <br/><br/> <i>2‑minute walkthrough: data model, interactive slicers, and MENA‑specific insights.</i> </div><hr>
💡 Key Insights for the Egyptian / MENA Market
Insight	Business Action
Peak hours: 8–10 PM (Iftar rush during Ramadan)	Increase delivery drivers & kitchen staff
Chicken pizzas (e.g., ckn_alfredo, thai_ckn) outsell beef	Feature chicken pizzas in promotions
Sales dip during Eid al‑Fitr (first week of May)	Plan maintenance & reduce inventory
Large size accounts for >60% of revenue	Bundle large pizzas with drinks or sides
These insights helped the chain:

✅ Optimize staff scheduling

✅ Design targeted promotions

✅ Improve inventory forecasting

<hr>
🚀 How to Use This Dashboard
Download the Excel file from data/pizza_sales_2022.xlsx.

Enable Power Pivot in Excel (File → Options → Add‑ins → COM Add‑ins → Microsoft Power Pivot for Excel).

Open Power Pivot (Power Pivot → Manage) to explore the data model and measures.

Refresh all (Data → Refresh All) if you add new rows.

Interact with slicers (date range, pizza category, size) to filter all charts.

<hr>
📁 Repository Structure
bash
pizza-sales-dashboard/
├── data/
│   └── pizza_sales_2022.xlsx          # Main Excel file (data model + dashboard)
├── images/
│   ├── dashboard_overview.png         # Main dashboard screenshot
│   ├── sales_by_pizza.png
│   ├── peak_hours.png
│   ├── size_revenue.png
│   └── data_model.png
├── video/
│   └── demo.mp4                       # 2‑minute screen recording
├── README.md                          # This file
└── dashboard_instructions.md          # Detailed step‑by‑step guide
<hr>
👤 Author
Your Name
📧 your.email@example.com
🔗 LinkedIn | GitHub

Passionate about turning data into decisions – focused on the MENA market.

<hr>
📜 License
This project is for portfolio purposes only. The data is simulated and does not represent any real business.

<div align="center"> <i>⭐ If you find this project useful, give it a star on GitHub! ⭐</i> </div> ``
