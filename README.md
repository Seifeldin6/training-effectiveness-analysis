# 📈 Training Effectiveness Analysis Pipeline (ROI Calculator)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## 📌 Executive Summary
This project implements an automated end-to-end analytical pipeline designed to measure the **Return on Investment (ROI)** of corporate training programs. 

Unlike traditional LMS reports that only track completion rates, this solution quantifies the actual impact of training on employee performance (KPIs) using **Difference-in-Differences (DiD)** approximation. Furthermore, it introduces a novel **"Quality of Learning"** metric by correlating exam scores with performance lift, allowing organizations to distinguish between effective content and misleading assessments (e.g., the "Exam Mismatch" phenomenon).

---

## 🚀 Key Features
*  **Raw Event Processing:** Ingests granular learner event logs (not pre-aggregated data) to extract precise completion timestamps and best-attempt scores.
*  **Optimized Performance:** Utilizes vectorized operations and $O(N)$ complexity logic to process large datasets in seconds (approx. 10-20s runtime).
* **Statistical Rigor:** Validates results using **Welch’s T-test** ($p < 0.05$) to ensure performance changes are statistically significant.
* **Score Impact Analysis:** Calculates Pearson Correlation between *Exam Scores* and *Performance Lift* to validate the assessment's predictive power.
* **Automated Strategy:** Generates a `recommendation.csv` file with actionable business decisions (e.g., "Scale Course", "Fix Exam", "Monitor").

---

## 📂 Repository Structure

```text
Training-Effectiveness-Analysis/
│
├── data/                         # Raw Input Data
│   ├── learner_events.csv        # Log of starts, submits, and completions
│   └── kpis.csv                  # Monthly performance records
│
├── output/                       # Generated Reports
│   ├── recommendation.csv        # FINAL strategic report (The Main Deliverable)
│   └── metrics_report.csv        # Detailed statistical breakdown
│
├── docs/                         # Documentation
│   └── Technical_Report.pdf      # Deep dive into math & architecture
│
├── ROI_Analysis_Pipeline.ipynb  # Main Execution Notebook (The Code)
├── requirements.txt              # Dependencies
└── README.md                     # Project Documentation