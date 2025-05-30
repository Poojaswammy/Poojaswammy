#  Augment Linkage: Evidence and Exploration  
**Graph-Based Intelligence Analysis for Fentanyl Trafficking Networks**

##  Project Overview
This capstone project investigates hidden networks in fentanyl trafficking by modeling corporate relationships using graph databases and visualizing entity linkages across platforms. Using communication identifiers like emails, phone numbers, and chat handles, we uncovered connections between shell companies and high-risk actors through real-time visual exploration and cloud-based graph analytics.

---

##  Problem Statement
Conventional relational data structures are insufficient for identifying complex linkages in criminal networks. Investigators often lack scalable tools to map multi-entity interactions, leading to delays in identifying high-risk entities. This project builds an end-to-end solution to reveal shared identifiers between companies and explore how they are linked through evidence-backed relationships.

---

##  Technologies & Tools
- **Graph Databases**: Neo4j, AWS Neptune  
- **Visualization Tools**: Tableau (Tree Extension), Neo4j Bloom, Gephi  
- **Languages & Queries**: Python, Cypher, Gremlin  
- **Data Modeling**: Key-Value format, 3NF normalization  
- **Cloud Platform**: AWS EC2, Neptune, S3  

---

##  Solution Architecture

We designed and implemented a 3-part architecture:

### 🔹 Tableau Interactive Dashboard
- Built tree graph dashboards using Tableau and Tree Extension
- Color-coded connections by linkage method (email, phone, chat)
- Interactive filters for company selection and linkage frequency
- Enabled visual, intuitive navigation across networks

### 🔹 Neo4j Native Graph Modeling
- Modeled entities using multi-hop schema:
(BaseCompany)-[:HAS_METHOD]->(LinkageMethod)
(LinkageMethod)-[:HAS_LINKAGE]->(LinkageValue)
(LinkageValue)-[:LINKS]->(AssociatedCompany)- Queried top linkages using Cypher
- Weighted relationships by frequency to prioritize suspicious activity

### 🔹 AWS Neptune Graph Analytics
- Deployed scalable graph queries using Gremlin on Neptune
- Modeled datasets in both KV and 3NF forms
- Inferred company-to-company relationships through shared attributes
- Used Jupyter notebooks to automate ingestion and exploration

---

##  My Contributions
- Modeled entity relationships in Neo4j using Cypher queries
- Developed graph-based ingestion pipelines on AWS Neptune using Gremlin
- Created Tableau Tree Graph dashboards with layered filters and tooltips
- Cleaned and transformed real-world entity datasets into 3NF and KV forms
- Collaborated on architecture design and cross-platform visual storytelling

---

## Outcomes
- Reduced graph exploration time by **~70%** compared to manual analysis
- Identified **20+ high-risk company clusters** across multiple data sources
- Built a cloud-based graph system enabling **real-time linkage analysis**
- Demonstrated effectiveness of graph modeling in public safety intelligence

---

##  Skills Highlighted
- Graph-based data modeling (Cypher, Gremlin)  
- Cloud deployment using AWS Neptune and EC2  
- Visual analytics using Tableau and Gephi  
- Multi-format data engineering (structured + semi-structured)  
- Team collaboration in research, design, and development

---

##  About Me
I am a data analyst with a strong interest in solving real-world problems using data architecture, graph analytics, and visualization. This project reflects my capability to bridge technical modeling and investigative insights using scalable, cloud-based tools.
