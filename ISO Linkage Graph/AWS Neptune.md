Project Report
ISO Linkage Graphers – Amazon Neptune Graph Ingestion
Capstone Project | DAEN 690 – George Mason University
Author: Pooja Manjunatha Swamy

Purpose
The purpose of this module was to build a scalable and searchable graph representation of complex entity relationships (e.g., companies connected via email, phone, chat) using Amazon Neptune, allowing for hidden network exploration and investigative insights in the context of fentanyl trafficking investigations.

Objective
To ingest and model structured and semi-structured data using Gremlin queries into Amazon Neptune, enabling:

Relationship exploration across organizations

Identification of shared identifiers (phone, email, chat)

Visualization of high-risk clusters in supply chain or communication networks

Overview of Graph Model
We designed a dual-ingestion pipeline for Key-Value and 3NF (Third Normal Form) data modeling using structured Excel data.

Key-Value Graph Schema

(Company) 
  ├── HAS_VALUE ──> (AttributeValue) 
(AttributeValue) 
  └── HAS_TYPE ──> (AttributeType)
Inferred Linkages
Companies sharing the same AttributeValue (e.g., the same email) are linked:

(Company) ── LINKED_COMPANY { via: value } ──> (Company)
This enabled automatic detection of hidden relationships.

Datasets Used
Consolidated_TraCCC_KV_Master(In_Work7).xlsx

ISO_Main1.xlsx (Key-Value Model)

ISO_Linkage1.xlsx (3NF)

ISO_Company.xlsx (Company payment metadata)

3NF-Based Extended Schema
We extended the schema to cover more granular and typed relationships:

(Company) 
  ├── has_email / has_phone / has_chat_wechat ──> (LinkageValue)
  ├── uses_payment_method ──> (PaymentMethod)

(LinkageValue) ── used_by ──> (Company)
(LinkageMethod) ── has_type ──> (LinkageValueType)
(LinkageMethod) ── has_value ──> (LinkageValue)
 Ingestion Workflow
Read Excel Files with pandas

Preprocess data to avoid nulls, whitespace issues

Construct Gremlin queries dynamically for each node and edge

Use fold().coalesce() to avoid duplicate creation

Submit queries to Neptune via POST requests to:

https://<your-neptune-endpoint>:8182/gremlin
Confirm successful ingestions via Graph Explorer or query logs

Functional Highlights
Unique node creation for each company, attribute type, value, and payment method

Dynamic edge generation (has_email, has_chat_wechat, etc.)

Linkage scoring enabled prioritization of suspicious clusters

Evidence score threshold filtering (e.g., only scores ≥ 3000 ingested)

Outcomes
Created over 10,000 unique nodes and 50,000+ relationship edges

Reduced manual investigation effort by ~70%

Enabled real-time searchability of companies based on communication identifiers

Integrated findings into a Neo4j + Tableau-based visual system

Limitations
Graph ingestion is batch-processed — not real-time streaming

Excel format requires strict field standardization before ingestion

Attribute ambiguity (e.g., reused phone numbers) requires further validation

Skills Demonstrated
Graph-based data modeling

Gremlin query construction

AWS Neptune configuration & ingestion

Complex relationship inference logic

Scalable architecture design

📎 Notes
This module serves as a key piece in the broader "Augment Linkage" system, contributing the scalable, cloud-based backend graph layer for intelligence gathering and pattern recognition.
