# Ecom Express — Sales & Delivery Analytics

A Power BI project analyzing orders, products, and customers for an e-commerce business, with a single dashboard page covering revenue, order volume, and cancellations.

1. Files

| File | Description |
|---|---|
| `ecom_express.pbix` | Power BI report file. Contains the data model, relationships, DAX measures, and the "Overview" dashboard page. |
| `Orders.csv` | 15,690 order records — order, customer, and product IDs, quantity, purchase timestamp, delivery time, and delivery status. |
| `Products.csv` | 80 products — name, category, price, rating, and number of ratings. |
| `Customers.csv` | 462 customers — name, phone, city, state, phone brand, and operating system. |

2. Data Model

Three tables joined on ID fields:

- **Orders** → **Products** via `ProductID`
- **Orders** → **Customers** via `CustomerID`

3. Orders.csv columns
- `OrderID` — unique order identifier
- `CustomerID` — links to Customers
- `ProductID` — links to Products
- `Quantity` — units purchased
- `Date and time of purchase` — order timestamp
- `Delivery time` — delivery timestamp
- `Delivery Status` — e.g. Delivered, Cancelled

4. Products.csv columns
- `ProductID`, `Product Name`, `Category`, `Price`, `Rating`, `Number of people rated the product`

5. Customers.csv columns
- `CustomerID`, `First Name`, `Last Name`, `Phone`, `City`, `State`, `Phone Brand`, `Operating System`

6. DAX Measures (in the model)

- **Revenue** — total sales value
- **avg_order** — average order value
- **cancellation_rate** — % of orders cancelled
- **cancellation_rev** — revenue lost to cancellations
- Total order count (via `OrderID` count)

7. Dashboard — "Overview" Page

- **KPI cards:** Revenue, Avg. Order Value, Cancellation Rate, Cancellation Revenue, Total Orders
- **Bar chart:** Revenue by Product Name / Category
- **Bar chart:** Revenue by Category
- **Bar chart:** Revenue by State (customer location)
- **Line chart:** Revenue trend by month (based on delivery date)
- **Slicers:** filter by Product Category and Purchase Date

8. Dataset at a Glance

| Metric | Value |
|---|---|
| Total orders | 15,690 |
| Delivered orders | 11,027 (70.3%) |
| Cancelled orders | 4,663 (29.7%) |
| Order date range | Jan 1, 2024 – Nov 6, 2024 |
| Products | 80, across 9 categories |
| Price range | ₹515 – ₹89,975 |
| Customers | 462 |
| Top customer states | Maharashtra (91), Gujarat (90), Rajasthan (60), West Bengal (55), Tamil Nadu (45) |
| Phone brands (customers) | Xiaomi (88), Realme (81), OnePlus (80), Vivo (76), Samsung (70), Apple (67) |
| Operating system split | iOS 236 / Android 226 |

9. Product categories
Laptop (20), Cable (15), Mobile (9), Accessory (7), Headphones (7), Tablet (7), Mouse (6), Charger (5), Speaker (4).

10. Key Insights

- **Cancellation is material, not marginal:** nearly 3 in 10 orders (29.7%) are cancelled, which is why the dashboard surfaces `cancellation_rate` and `cancellation_rev` as headline KPIs alongside revenue rather than as a footnote metric.
- **Laptops and Cables dominate the catalog** by product count, but the bar chart lets you check whether that matches their share of revenue — high SKU count doesn't necessarily mean high revenue contribution.
- **Customer base skews toward western/northern India** — Maharashtra and Gujarat together account for roughly 39% of customers, useful context when reading the "Revenue by State" chart.
- **Mobile OS split is nearly even** (iOS 236 vs Android 226), so device/OS isn't currently used as a dashboard filter but could be added as a segmentation dimension.


11. How to Use

1. Open `ecom_express.pbix` in Power BI Desktop.
2. If prompted, point the data source connections to the local CSV files (`Orders.csv`, `Products.csv`, `Customers.csv`).
3. Use the Category and Date slicers on the Overview page to filter the dashboard.
4. Refresh the data model if the CSVs are updated.

12. Requirements

- Power BI Desktop (recent version, saved with Power BI's July 2026 base theme resources)
