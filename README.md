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
