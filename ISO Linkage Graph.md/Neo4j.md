#  ISO Linkage Graphers – Neo4j Graph Implementation

This document outlines the Neo4j-based modeling and visualization of corporate linkage data used in the ISO Linkage Graphers project, which focused on uncovering fentanyl trafficking linkages through shared communication identifiers.

---

##  Purpose

To build an interactive graph model that uncovers relationships between companies using shared identifiers like email, phone, and chat platforms. Neo4j was used to model these relationships and visualize high-risk linkages.

---

##  Tools Used

- Neo4j Desktop & Browser
- Cypher Query Language
- Neo4j Bloom
- Dataset: `Company_Linkage_data.csv`

---

##  Graph Schema

Each company is connected to other entities through a layered relationship graph:
![image](https://github.com/user-attachments/assets/71e1c115-594c-4847-bf1a-fa895401e834)

### Nodes:
- **BaseCompany**: The entity under investigation
- **LinkageMethod**: Type of communication (Email, Phone, Chat)
- **LinkageValue**: Shared contact detail (e.g., a phone number)
- **AssociatedCompany**: A second company sharing the linkage

---

##  Query Features

- Identified the top 2 most frequent linkage values per base company
- Applied frequency scoring to highlight suspicious patterns
- Enabled filtering by linkage method and company

---

## Visualization Output
Explored relationship graphs using Neo4j Browser

Used Neo4j Bloom for visual, interactive exploration

Visualized top companies such as Amadis Chemical, Shanghai Hao Zhun, etc.

Highlighted frequently used identifiers across companies

Allowed cluster exploration based on shared communication links

## Outcome
Created an explorable relationship graph across all high-risk entities

Revealed communication patterns not visible in flat tables

Improved investigative flow for tracing companies using the same emails or phone numbers

Supported dashboard integration by providing cleaned, prelinked data

## My Role
Built and tested Cypher queries to extract and link data

Designed the graph schema tailored to communication-based linkages

Filtered high-impact linkages using frequency analysis

Delivered the final Neo4j model for use in visual investigations
