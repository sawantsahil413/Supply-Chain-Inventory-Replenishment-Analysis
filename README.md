#  Supply Chain Inventory & Replenishment Analysis

An end-to-end inventory management and replenishment model built in Microsoft Excel. This portfolio project simulates a 90-day retail inventory cycle across 60 SKUs, featuring automated data cleaning, statistical safety stock modeling, Economic Order Quantity (EOQ) optimization, and a dynamic executive dashboard.

---

## The Business Problem
Inventory management teams constantly face a difficult balancing act:
* **Stockouts:** Fast-moving items run out of stock, resulting in lost revenue and dissatisfied customers.
* **Overstocking:** Slow-moving products sit idly on shelves, tying up valuable working capital and increasing holding costs.
* **Outdated Reorder Thresholds:** In many legacy systems, reorder levels are set arbitrarily or kept too low (in this dataset, 40 out of 60 SKUs had outdated reorder points), causing alerts to trigger too late.
* **Data Quality Issues:** Real-world data feeds often contain messy anomalies, duplicate entries, missing input fields, and physical stock-count discrepancies (shrinkage/damage).

---

## The Solution & Workflow
This workbook implements a robust, formula-driven supply chain framework to solve these challenges through a strict 6-stage pipeline:

1. **Data Intake & Validation (`Raw_Data` & `Validation`):** 
   * Audited 62 raw records, successfully removing duplicate SKUs and imputing missing values (lead times and sales) using category averages and movement equations.
   * Explicitly flagged 3 stock-movement variances where physical closing counts did not match ledger inputs, routing them for warehouse audits.
2. **Dynamic Assumptions Engine (`Assumptions`):** 
   * Built a centralized control panel where key parameters (Service Level Z-score, ordering costs, holding costs, and overstock thresholds) can be adjusted to dynamically recalculate the entire workbook.
3. **Statistical Inventory Analysis (`Analysis`):** 
   * Calculated **Average Daily Demand**, **Lead-Time Demand**, **Safety Stock** (using a 1.65 Z-score targeting a 95% service level), and **Economic Order Quantity (EOQ)**.
   * Automatically established scientific **Recommended Reorder Points**.
4. **ABC & Velocity Classification (`Analysis`):** 
   * Segmented products by value contribution (ABC analysis) and sales velocity (Fast, Medium, Slow movers) to prioritize capital allocation.
5. **Executive Dashboard (`Dashboard` & `Summary`):** 
   * Designed live KPI summary cards tracking total inventory value ($\text{₹}2.16M$), stockout counts, at-risk items, and overstock capital tie-ups.
6. **Actionable Procurement Plan (`Replenishment`):** 
   * Generated an auto-sorted priority list for the 19 SKUs requiring immediate reordering, detailing exact suggested order quantities and total purchase order values ($\text{₹}1,075,375$).

---

## Workbook Architecture (Worksheet Guide)

| Sheet Name | Description & Function |
| :--- | :--- |
| **`README`** | Project overview, scope, and structural guide. |
| **`Dashboard`** | High-level KPI visual control panel and automated key insights. |
| **`Assumptions`** | Centralized control cell inputs for global model adjustments. |
| **`Raw_Data`** | Raw sample dataset containing planted real-world anomalies. |
| **`Validation`** | Live audit log documenting data cleaning and reconciliation rules. |
| **`Analysis`** | Core calculation engine (Demand, EOQ, Safety Stock, Reorder Points, ABC class). |
| **`Summary`** | Pivot-style aggregation tables grouped by inventory status and category. |
| **`Replenishment`** | Auto-sorted, high-priority purchase order list for warehouse execution. |

---

## Key Insights & Results
* **Replenishment Need:** 19 of 60 SKUs (32%) require immediate reordering (5 stocked out, 11 below reorder level, 3 at risk).
* **Capital Efficiency:** 8 overstocked SKUs hold more than 60 days of inventory cover, tying up over 50% ($\text{₹}1.1M$) of total inventory value.
* **Risk Mitigation:** Replaced outdated triggers with statistical reorder points across all SKUs, preventing future late-stage stockouts.

---

## Skills & Tools Demonstrated
* **Supply Chain Analytics:** Safety stock modeling, service level management (Z-scores), lead-time demand calculations, EOQ optimization, and ABC/Velocity segmentation.
* **Data Quality & Hygiene:** Error detection, duplicate purging, missing value imputation, and inventory variance reconciliation.
* **Advanced Excel Modeling:** Complex nested formulas, dynamic summary tables, structured audit logging, and executive dashboard design.

---
