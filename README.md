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

8. How to Use

1. Open `ecom_express.pbix` in Power BI Desktop.
2. If prompted, point the data source connections to the local CSV files (`Orders.csv`, `Products.csv`, `Customers.csv`).
3. Use the Category and Date slicers on the Overview page to filter the dashboard.
4. Refresh the data model if the CSVs are updated.

9. Requirements

- Power BI Desktop (recent version, saved with Power BI's July 2026 base theme resources)
