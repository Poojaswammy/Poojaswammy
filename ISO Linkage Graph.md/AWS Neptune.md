#  ISO Linkage Graphers – AWS Neptune Graph Ingestion

This document describes the implementation of the AWS Neptune-based graph ingestion used in the ISO Linkage Graphers project. It focuses on the scalable modeling of corporate linkages using structured and semi-structured data in a cloud-native graph database.

---

##  Purpose

To ingest and model company linkage data into **Amazon Neptune** using **Gremlin queries**, enabling the discovery of hidden connections between organizations based on shared identifiers like emails, phone numbers, and chat IDs.

---

##  Tools Used

- Amazon Neptune
- AWS EC2 and S3
- Python (pandas, requests, openpyxl)
- Jupyter Notebook
- Gremlin Query Language
- Dataset: `Consolidated_TraCCC_KV_Master(In_Work7).xlsx`, `ISO_Main1.xlsx`, `ISO_Linkage1.xlsx`, `ISO_Company.xlsx`

---

##  Graph Schema

### Key-Value Model
![image](https://github.com/user-attachments/assets/e85e0425-ef26-42d3-8892-232075277274)


### 3NF Extended Model
![image](https://github.com/user-attachments/assets/4bf2301f-7808-43ae-8f8a-eb76d2bdd4f9)


---

## 🔁 Ingestion Workflow

1. Loaded Excel files using `pandas`
2. Preprocessed and normalized the data into Key-Value and 3NF structures
3. Built Gremlin queries to:
   - Create nodes (Company, AttributeType, AttributeValue, PaymentMethod)
   - Add dynamic edge types (e.g., `has_email`, `has_chat_wechat`)
4. Prevented duplicates using `fold().coalesce()` logic
5. Posted queries to Neptune at:
6. Visualized results using Graph Explorer and Jupyter Notebook

---

## Visualization Output

- Displayed company linkage clusters through AWS Graph Explorer
- Traced shared identifiers across multiple companies
- Observed connection density and linkage frequency
- Allowed real-time filtering and investigation using notebook queries

---

##  Outcome

- Successfully ingested structured and semi-structured data into Amazon Neptune
- Created over **10,000 unique nodes** and **50,000+ relationships**
- Reduced manual investigation time by approximately **70%**
- Enabled scalable, cloud-based graph search functionality
- Served as a foundational backend for higher-level dashboards

---

##  My Role

- Developed the ingestion pipeline in Python and Gremlin
- Modeled both Key-Value and 3NF schemas for Neptune
- Created dynamic Gremlin edge types based on attribute categories
- Filtered high-signal data using evidence scores (≥ 3000)
- Integrated Neptune results into the broader investigation workflow

