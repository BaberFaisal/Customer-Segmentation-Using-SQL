# Customer Segmentation Using SQL

This project analyzes transactional retail data to segment customers based on their purchasing behavior using RFM (Recency, Frequency, Monetary) metrics and SQL queries.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Purpose](#purpose)
- [Dataset Description](#dataset-description)
- [Methodology](#methodology)
- [Segmentation Criteria](#segmentation-criteria)
- [Results](#results)
- [Next Steps](#next-steps)
- [Technologies Used](#technologies-used)

---

## Project Overview

The objective is to use SQL for segmenting retail customers into behavior-based groups. This enables businesses to target customers more effectively and improve retention, loyalty, and sales.

---

## Purpose

- Identify loyal customers  
- Find high-value customers  
- Spot at-risk or dormant customers  
- Drive targeted marketing with data  

---

##  Dataset Description

The dataset consists of retail transactions from 2010–2011, including the following columns:

| Column Name  | Description                       |
|--------------|-----------------------------------|
| InvoiceNo    | Transaction ID                    |
| StockCode    | Product Code                      |
| Description  | Product Description               |
| Quantity     | Number of Items Purchased         |
| InvoiceDate  | Date of Transaction               |
| UnitPrice    | Price per Unit                    |
| CustomerID   | Unique Customer Identifier        |
| Country      | Country of Customer               |

---

## Methodology

1. **Data Preprocessing**  
   - Removed NULL CustomerIDs  
   - Filtered out negative or zero quantities  
   - Added `TotalPrice` column = Quantity × UnitPrice  

2. **RFM Metric Calculation**  
   - **Recency**: Days since last purchase  
   - **Frequency**: Number of unique invoices  
   - **Monetary**: Total revenue per customer  

3. **Scoring System**  
   Used SQL `CASE WHEN` logic to score each RFM metric from 1 to 4 based on thresholds.

4. **Segmentation**  
   Created segments based on combined RFM scores (e.g., 444, 321).

---

##  Segmentation Criteria

| Segment          | Description                                      |
|------------------|--------------------------------------------------|
| Champions        | Recent, frequent, high spenders                 |
| Loyal Customers  | Frequent buyers, less recent                    |
| At Risk          | Haven’t purchased in a long time               |
| Potential        | Moderate spenders with recent activity         |
| Others           | Not matching any of the above strictly         |

---

## Results

- **Segment Distribution**
  - Potential: 628 customers
  - Loyal Customers: 2
  - Others: 4

- **Revenue by Segment**
  - Others: \$57,587.18
  - Potential: \$29,161.73
  - Loyal Customers: \$8,809.54

- **Average Order Value**
  - Others: \$2,478.52
  - Potential: \$361.40
  - Loyal Customers: \$153.59

---

## Next Steps

- Add time-based tracking for customer lifecycle stages  
- Integrate with marketing tools for automated campaigns  
- Extend segmentation by product or category  

---

## Technologies Used

- SQL (with views, `CASE`, `GROUP BY`, `DATEDIFF`, etc.)
- Basic SQL-based data engineering
- RFM Segmentation logic


