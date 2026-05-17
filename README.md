


# FDA MAUDE Quality Analytics: Complaint Trend & Risk Analysis

Built an end-to-end analytics pipeline on FDA MAUDE (Manufacturer and User Facility Device Experience) data to identify recurring product failures, complaint concentration risks, traceability gaps, and potential CAPA opportunities across medical devices.
This project simulates how a Quality Engineer / Continuous Improvement / Operations Analyst would investigate post-market complaint data to support ISO 13485 quality systems, CAPA prioritization, and risk mitigation.

---

## Business Problem

Medical device manufacturers receive massive volumes of post-market complaints, but raw FDA MAUDE datasets are fragmented across multiple files:

* MDR Event Reports
* Device Information
* Patient Information
* Narrative Text Files

The challenge was:

* Large dataset size (millions of rows)
* Multiple disconnected tables
* Missing traceability between complaint reports and device records
* Unstructured complaint narratives
* Difficulty identifying recurring failure trends quickly

The goal was to convert raw complaint data into actionable quality insights.

---

## Dataset

FDA MAUDE public dataset (2020–2025)

Tables used:

### 1. MDR Reports Table

Core complaint event data

Fields:

* MDR_REPORT_KEY
* DATE_RECEIVED
* EVENT_TYPE
* REPORT_SOURCE
* REPORTER_COUNTRY_CODE

**Records analyzed:** **13.8M+**

---

### 2. Device Table

Device-level information

Fields:

* Manufacturer
* Brand
* Product Code
* Device Type

**Records analyzed:** **2.19M+**

---

### 3. Patient Table

Patient impact/severity details

Fields:

* Injury
* Death
* Malfunction severity

---

### 4. Complaint Narrative Text

Unstructured complaint descriptions used for NLP analysis.

---

## Tech Stack

Instead of loading millions of rows into memory with pandas:

* **DuckDB** → fast SQL joins/querying on large flat files
* **Python**
* **Pandas**
* **Matplotlib**
* **NLP (CountVectorizer - Scikit Learn)**

---

## Key Analysis Performed

### Complaint Trend Analysis

Tracked monthly complaint volume across 2025.

**Finding:**
Monthly complaints ranged from **347K → 441K**, showing persistent complaint inflows with recurring spikes.

---

## Manufacturer Risk Concentration

Top manufacturers by complaint volume:

* Dexcom → **834K**
* Medtronic Puerto Rico → **410K**
* Tandem Diabetes Care → **298K**

This highlighted complaint concentration among major diabetes device manufacturers.

---

## Pareto Analysis (Critical Few)

Built Pareto charts to identify the "vital few" device brands driving majority of complaints.

### Largest contributor:

**Dexcom G7 → 605K complaints**

Top few device brands accounted for majority of complaint volume.

This mirrors real-world CAPA prioritization logic.

---

## Severity Analysis

Analyzed patient severity scores.

Findings:

* Severity 0 → **2.67M**
* Severity 3 → **620K**
* Severity 4–5 → significantly lower but higher risk

Helps prioritize high-severity investigations.

---

## Geographic Complaint Analysis

Top reporting country:

**United States → 2.7M+ complaints**

Followed by:

* Switzerland
* Japan
* Germany
* Canada

---

## NLP Failure Pattern Mining

Applied NLP on complaint narratives to identify recurring failure keywords.

Most frequent issues:

* Injury
* Failure
* Malfunction
* Battery
* Infection
* Broken
* Leak
* Fracture
* Overheat

This helps uncover hidden failure modes from unstructured complaint text.

---

## Traceability Gap Analysis

Joined MDR reports with device records.

Found:

* **2.72M** complaint reports in 2025
* **541K** missing linked device records
* **~19.8% traceability gap**

This can create investigation delays during audits and CAPA reviews.

---

# Why This Matters

This project reflects real responsibilities in:

* Quality Engineering
* CAPA
* Continuous Improvement
* Operations Analytics
* Medical Device Quality
* ISO 13485 environments
* FDA post-market surveillance

---

## What I Demonstrated

* Large-scale data cleaning
* SQL joins
* Root cause trend analysis
* Pareto prioritization
* Complaint risk analysis
* NLP on quality narratives
* Traceability gap identification
* Data storytelling for operational decisions

---

## Potential Business Actions

* Prioritize CAPA for high complaint products
* Improve supplier/process controls
* Reduce recurring failures
* Improve complaint traceability
* Strengthen post-market surveillance workflows

---

## Repository Contents

* Jupyter Notebook
* SQL queries
* Visualizations
* Analysis outputs

---

---

This project helped me bridge **quality engineering + manufacturing + analytics** by applying data-driven problem solving to medical device quality systems.

