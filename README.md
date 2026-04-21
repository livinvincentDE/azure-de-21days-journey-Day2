# 📦 Final GitHub README.md

````markdown
# 🚀 Day 2: Scalable Data Ingestion Pipeline (Microsoft Fabric)

![Microsoft Fabric](https://img.shields.io/badge/Microsoft-Fabric-blue)
![Data Engineering](https://img.shields.io/badge/Data-Engineering-orange)
![Pipeline](https://img.shields.io/badge/Pipeline-Scalable-green)
![Status](https://img.shields.io/badge/Project-Active-success)

---

## 📌 Overview

This project demonstrates how to build a **scalable, metadata-driven data ingestion pipeline** using **Microsoft Fabric**.

The pipeline is designed to efficiently process **large volumes of data (GB → TB → PB)** by leveraging:

- ⚡ Parallel execution  
- 🔄 Dynamic ingestion  
- 📦 Metadata-driven architecture  
- 🧠 Centralized logging  

---

## 🧭 Table of Contents

- [🎯 Objective](#-objective)
- [🧠 Problem Statement](#-problem-statement)
- [🏗️ Architecture](#️-architecture)
- [🔧 Components](#-components)
- [🧭 Pipeline Design](#-pipeline-design)
- [⚡ Performance Strategy](#-performance-strategy)
- [📊 Output](#-output)
- [🔥 Key Learnings](#-key-learnings)
- [🌍 Use Cases](#-use-cases)
- [🚀 Future Enhancements](#-future-enhancements)

---

## 🎯 Objective

Build a **scalable ingestion pipeline** to load data into a **Lakehouse (Bronze Layer)** using Microsoft Fabric.

---

## 🧠 Problem Statement

Traditional ingestion methods fail at scale:

- ❌ Manual file handling  
- ❌ Sequential processing  
- ❌ Not scalable  

### ✅ Solution Approach

- Parallel processing using **ForEach**
- Metadata-driven pipeline design
- Automated logging & monitoring

---

## 🏗️ Architecture

```plaintext
Source Files 
     ↓
Pipeline (Lookup → ForEach → Copy)
     ↓
Bronze Layer (Lakehouse)
     ↓
Logging Layer (Delta Table)
````

---

## 🔧 Components

| Component     | Description                   |
| ------------- | ----------------------------- |
| Lakehouse     | Stores ingested data (Bronze) |
| Pipeline      | Orchestrates workflow         |
| Lookup        | Reads metadata                |
| ForEach       | Enables parallel processing   |
| Copy Activity | Loads data                    |
| Notebook      | Handles logging               |

---

## 🧭 Pipeline Design

### 🔹 Step 1: Metadata Driven

Metadata table contains:

```json
{
  "file_name": "file1.csv",
  "source_path": "/input/",
  "target_path": "/bronze/",
  "archive_path": "/archive/"
}
```

---

### 🔹 Step 2: Parallel Execution

```plaintext
Lookup → ForEach → Copy Activity
```

✔ Multiple files processed simultaneously
✔ Improves throughput

---

### 🔹 Step 3: Dynamic Parameters

Pipeline dynamically assigns:

* file_name
* source_path
* target_path
* archive_path

---

### 🔹 Step 4: Data Ingestion

* Source → Files
* Destination → Lakehouse

✔ Optimized for large-scale ingestion

---

### 🔹 Step 5: Archiving

```plaintext
Move processed files → Archive folder
```

✔ Prevents reprocessing
✔ Maintains audit trail

---

### 🔹 Step 6: Error Handling

* Success → log_success
* Failure → log_failure

---

### 🔹 Step 7: Logging Payload

```json
{
  "file_name": "file1.csv",
  "status": "SUCCESS",
  "time": "2026-04-21",
  "run_id": "12345",
  "pipeline_name": "ingestion_pipeline",
  "row_count": "10000"
}
```

---

### 🔹 Step 8: Notebook Logging

Logs stored in:

```
pipeline_logs (Delta Table)
```

✔ Enables monitoring & observability

---

## ⚡ Performance Strategy

### 🔸 Parallel Processing

* Uses **ForEach activity**
* Handles multiple files concurrently

---

### 🔸 Partitioning

* Data stored efficiently in Lakehouse
* Faster downstream queries

---

### 🔸 Incremental Load

* Processes only new files
* Avoids duplication

---

## 📊 Output

### 🟤 Bronze Layer

* Raw ingested data

### 📋 Logging Table

| file_name | status | run_id | pipeline_name | row_count |
| --------- | ------ | ------ | ------------- | --------- |

---

## 🔥 Key Learnings

* Metadata-driven architecture
* Scalable pipeline design
* Parallel ingestion techniques
* Logging & monitoring strategies
* Handling large datasets

---

## 🌍 Use Cases

* 🏥 Healthcare Data Pipelines
* 🏦 Banking & Financial Systems
* 🛒 E-commerce Analytics
* 🌐 IoT Data Processing

---

## 🚀 Future Enhancements

* Bronze → Silver transformation
* Data cleansing & joins
* Change Data Capture (CDC)
* Delta optimization techniques

---

## 👨‍💻 Author

**Livin Vincent**
Senior Data Engineer 🚀

📌 *21 Days of Azure Data Engineering*

---

Just say the word 😄
```
