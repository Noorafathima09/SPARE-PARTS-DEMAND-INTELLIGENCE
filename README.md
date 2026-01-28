
# Spare Parts Demand Intelligence


Real-world data analysis project based on ERP invoice data from an automotive spare parts and service agency.

---

## Project Overview

This project analyzes real ERP invoice-line data from an automotive spare parts counter and workshop environment to understand spare parts demand behavior and operational workload.

Instead of focusing only on sales or revenue, the analysis emphasizes:
- Demand consistency and stability
- Long-tail behavior of spare parts
- Operational workload hidden behind invoices
- Practical challenges of working with ERP data

The project demonstrates how raw transactional data can be transformed into business-meaningful insights using Python.

---

## Business Context

In spare parts and workshop operations, performance is often evaluated using revenue-centric metrics.  
However, revenue alone does not explain:

- Why workshops feel overloaded during certain periods  
- Which items truly drive recurring service activity  
- How much effort is consumed by free or policy jobs  
- Why operational workload does not always align with sales figures  

This project approaches the data from an operations and demand behavior perspective rather than a pure sales viewpoint.

---

## Dataset Description

- **Source:** ERP export from an automotive spare parts & service agency  
- **Granularity:** Invoice-line level  

### Structure
- Each row represents one line item  
- Multiple rows together form one invoice (job)  

### Key Columns
- Branch, Technician Name  
- Item Code, Item Name, Item Group  
- Invoice, Posting Date  
- Customer details  
- Stock Quantity, Rate, Amount, Taxes, Total  

### Data Characteristics
- Parts, consumables, labor, and service charges are mixed  
- Some invoices contain summary/total rows  
- Zero-value transactions exist (free or policy jobs)  
- Certain columns are semantically overloaded  

These characteristics required careful preprocessing before analysis.

---

## Tools & Technologies

- Python  
  - Pandas  
  - NumPy  
  - Matplotlib  
- Jupyter Notebook / VS Code  

---

## Data Preparation & Normalization

Key data preparation steps included:

- Inspecting data structure, types, and missing values  
- Handling null values without distorting operational meaning  
- Identifying and removing invoice-level summary rows that inflated quantities  
- Creating a monthly time dimension from posting dates  
- Deriving a new `Item Category` field to separate:
  - Physical Parts  
  - Consumables  
  - Labour Charges  
  - Service / Other Charges  

This ensured that subsequent analysis reflected true operational activity rather than accounting artifacts.

---

## Demand Analysis Summary

Demand analysis focused on physical parts and consumables, as these represent actual material movement.

The analysis included:
- Monthly aggregation of item demand  
- Activity ratio calculation (months active / total months)  
- Classification of items into Fast, Medium, and Slow moving  
- Identification of long-tail demand structure  
- Demand stability analysis using the Coefficient of Variation (CV)  

### Key Observations
- Nearly half of the item catalog consists of slow-moving items  
- A smaller subset of items appears consistently month after month  
- Fast-moving items are not necessarily stable  
- Operational dependency is concentrated on a limited group of items  

---

## Operational Interpretation of Demand

Rather than treating fast-moving items as universally low-risk, the analysis shows that:

- Demand consistency matters as much as volume  
- Some frequently used items exhibit high demand variability  
- Long-tail items dominate the catalog but not day-to-day operations  

This shifts the focus from *what sells* to *what operations depend on*.

---

## Job / Invoice-Level Perspective (Exploratory)

The dataset also supports analysis at the job (invoice) level, where each invoice represents a service visit.

The current exploration includes:
- Treating invoices as units of work rather than sales events  
- Identifying zero-value invoices that still consume effort  
- Observing job complexity through the number of line items per invoice  

This provides initial insight into operational workload beyond revenue figures.

---

## Key Insights

- Spare parts demand follows a clear long-tail pattern  
- Operational relevance is concentrated on a small subset of items  
- Revenue alone does not represent actual workshop workload  
- Zero-value jobs contribute to hidden operational effort  
- ERP data requires semantic understanding before meaningful analysis  

---

## Why This Project Stands Out

- Uses real ERP business data, not public datasets  
- Handles real-world data quality and semantic issues  
- Focuses on operations rather than vanity sales metrics  
- Avoids unnecessary machine learning  
- Emphasizes explainable, business-driven insights  

---

## Disclaimer

This project uses real business data strictly for educational and portfolio purposes.  
Sensitive information has been anonymized where required.

---

## Author

**Hafsa shafeek**  
Data Analyst | Python | SQL | Power BI  
Interested in real-world business and operations analytics




