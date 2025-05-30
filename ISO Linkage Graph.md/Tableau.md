# 📊 ISO Linkage Graphers – Tableau Interactive Dashboard

This document outlines the Tableau-based visualization component of the ISO Linkage Graphers project, designed to uncover hidden corporate linkages in fentanyl trafficking networks.

---

## 🔍 Purpose

To create an **interactive dashboard** that visualizes entity linkages based on shared communication identifiers such as email addresses, phone numbers, and chat IDs.

---

## 🛠️ Tools Used

- **Tableau Desktop 2021.4+**
- **Tableau Tree Extension**
- Dataset: `Associate_Reset_VRelease.xlsx`

---

## 🧱 Data Structure

Each row in the dataset represents a connection between a **base company** and an **associated company** based on a **shared identifier**.

- Columns:
  - Base Company
  - Associated Company
  - Linkage Method (Email, Phone, Chat)
  - Linkage Value
  - Evidence Score

---

## 🌳 Tree Graph Dashboard Features

- **Tree structure** shows base company and its direct associations.
- **Color-coded edges**:
  - Blue → Email
  - Orange → Phone
  - Green → Chat
- **Interactive Filters**:
  - Company name
  - Linkage method
  - Minimum linkage score
- **Tooltip Popups**:
  - Company contact details
  - Method of connection
  - Identifier used

---

## 📦 Workbook Deliverable

- File: `DAEN_690_tableau_Final_1.twbx`
- Includes:
  - Packaged data
  - Custom Tree Extension configuration
  - Filters and calculated fields

---

## ✅ Outcome

- Enabled intuitive navigation across company networks.
- Helped identify **highly linked companies** for further investigation.
- Served as the **primary user interface** for non-technical reviewers.

---

## 👩‍💻 My Role

- Developed dashboard layout and data schema.
- Integrated Tree Extension plugin and custom filters.
- Prepared linkage mapping and assisted in evidence scoring.

---

