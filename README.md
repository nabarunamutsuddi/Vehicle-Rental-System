# Vehicle-Rental-System
End-to-end Data Engineering project for a Vehicle Rental System using SQLite, Apache Spark, Kafka, and Airflow with ETL pipelines, OLAP warehouse, and real-time analytics.
# 🚗 Vehicle Rental System – Data Engineering Capstone Project

## 📌 Overview

This project implements a complete **end-to-end data engineering pipeline** for a vehicle rental system. It integrates OLTP database design, ETL processing, data warehousing, big data analytics, and workflow orchestration.

The system manages:

* Customer records
* Vehicle inventory
* Booking transactions
* Revenue analytics

---

## 🎯 Objectives

* Design a **3NF relational database**
* Implement SQL features: DDL, DML, Views, Indexes, Triggers
* Build an **ETL pipeline (CSV → Database → Warehouse)**
* Perform analytics using **Apache Spark**
* Enable orchestration using **Apache Airflow**
* Implement **data quality checks**

---

## 🏗️ System Architecture

```
CSV Data → Python ETL → SQLite (OLTP)
                      ↓
                Star Schema (OLAP)
                      ↓
                 Apache Spark
                      ↓
               Analytics Dashboard
                      ↓
               Apache Airflow DAG
```

---

## 🧱 Database Design

### Core Tables

* **vehicles** – vehicle details and availability
* **customers** – customer information
* **bookings** – transaction records

### Relationships

* Customer → Booking (1:M)
* Vehicle → Booking (1:M)

### Features

* Primary & Foreign Keys
* CHECK constraints
* Fully normalized (3NF)

---

## ⚙️ SQL Components

### ✔ DDL

Table creation for vehicles, customers, bookings

### ✔ DML

Insert, update, delete operations

### ✔ Views

* Active rentals
* Revenue summary
* Customer rankings

### ✔ Indexes

Optimized queries on:

* vehicle_id
* customer_id
* booking status
* dates

### ✔ Triggers

* Auto-update vehicle status on booking
* Restore availability after completion

---

## 🔄 Data Pipeline

### ETL Process

* CSV ingestion using Python
* Data cleaning & validation
* Deduplication
* Load into SQLite

### Data Quality Checks (22 rules)

* Null checks
* Duplicate detection
* Referential integrity
* Z-score anomaly detection

---

## 📊 Data Warehouse (OLAP)

* Star Schema:

  * `fact_bookings`
  * `dim_vehicle`
  * `dim_customer`
  * `dim_date`
  * `dim_location`

---

## ⚡ Big Data Processing

* Apache Spark DataFrames
* Spark SQL queries
* Broadcast joins optimization
* Parquet partitioning

---

## 📡 Streaming

* Apache Kafka
* 3-partition topic (by vehicle category)
* Producer–consumer architecture
* Offset replay for recovery

---

## ⏰ Workflow Orchestration

* Apache Airflow DAG (5 tasks)
* Scheduled daily at **02:00 AM**
* Retry logic & SLA monitoring
* Audit logging

---

## 📊 Dashboard Features

* Fleet utilization
* Revenue by category
* Top vehicles
* Active rentals
* Customer rankings

---

## 🛠️ Tech Stack

| Layer         | Technology     |
| ------------- | -------------- |
| Database      | SQLite         |
| Language      | Python         |
| Processing    | Apache Spark   |
| Streaming     | Apache Kafka   |
| Orchestration | Apache Airflow |
| Storage       | HDFS           |
| Format        | Parquet        |

---

## 🌟 Unique Features

* Full **end-to-end pipeline**
* Dual DB architecture (OLTP + OLAP)
* Real-time streaming with Kafka
* Automated Airflow DAG
* Data quality validation system
* Trigger-based automation

---

## 🚀 Future Improvements

* Cloud deployment (AWS/GCP)
* Streamlit dashboard
* GPS tracking via Kafka
* ML-based dynamic pricing
* Delta Lake integration

---

## 👨‍💻 Author
**Nabaruna Mutsuddi**
## 📌 Notes

* Logs and temporary runtime files are excluded from submission.
* Use provided scripts to regenerate pipelines if needed.
