# CleanSight ✨  
**AI Data Cleaning Assistant for Analysts (Local-First, No Code)**

 **Problem solved:** Analysts spend too much time cleaning messy data and too little time analyzing it.  
> **Solution:** CleanSight automates data profiling, detects quality issues, and applies safe, explainable cleaning — without code or external APIs.

CleanSight is a local-first, AI-assisted web app that helps analysts transform messy CSV/TSV/TXT datasets into **analysis-ready data** in minutes. It automates profiling, issue detection, cleaning recommendations, and exports — while prioritizing **transparency, data correctness, and reproducibility**.

---

## 🚀 What CleanSight Does

**Upload > Diagnose > Fix > Export**

### 🔍 Diagnose (Automatic)
CleanSight profiles your dataset and detects:
- Missing values (counts and percentages)
- Duplicate rows
- Data types and cardinality
- Formatting anomalies (dates, currency, percentages)
- Outliers using IQR-based statistical rules

### 🛠 Fix (User-Controlled)
Apply cleaning actions with previews and toggles:
- Trim whitespace
- Normalize currency and percent fields
- Safe numeric and date parsing
- Missing value imputation (configurable)
- Duplicate removal
- Outlier handling (cap / remove / ignore)

### ⬇️ Export
- Cleaned dataset (CSV)
- Cleaning report (HTML / TXT)
- Before vs After metrics with Data Quality Score

---

## 🧠 Core Principles

1. **Local-First Processing**  
   Your file stays in-session. No external APIs by default.

2. **Transparency Over Black-Box Automation**  
   Every issue is visible. Every fix is optional. Changes are previewed.

3. **Data Correctness Is Non-Negotiable**  
   Cleaning should never silently make data worse.

4. **Reproducibility**  
   Exports include a documented summary of all cleaning actions.

---

## 📊 Data Quality Score (0–100)

CleanSight includes a Quality Score to reflect **net data quality improvement**.

### Key Engineering Insight
During development, we identified that naïve type conversion (currency/date parsing) can unintentionally introduce new missing values (NaNs), causing quality scores to drop after cleaning.

### ✅ Safeguards Implemented
- Track missing cells **before and after cleaning**
- Compute **net new missing values introduced**
- Penalize score based on **net new issues only**
- Display warnings and a **Conversion Failure Report** when parsing fails

This makes score changes explainable, defensible, and trustworthy.

---

## 🧪 Demo Dataset
A built-in messy demo dataset is included so users can test the app instantly without uploading files (recruiter-friendly).

---

## 🏗 Tech Stack
- **Frontend:** Streamlit  
- **Data Processing:** pandas, NumPy  
- **Statistics:** IQR outlier detection, profiling summaries  
- **Deployment:** Replit (development), compatible with Streamlit Community Cloud / Hugging Face Spaces

---

## ▶️ Run Locally

### 1) Create environment
```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS / Linux:
source venv/bin/activate
