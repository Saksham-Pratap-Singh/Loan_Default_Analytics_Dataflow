# Loan Default Analytics – Dataflow & Power BI Dashboard

End‑to‑end analytics project to understand loan default behavior, segment borrowers by risk, and track portfolio performance using interactive Power BI dashboards and a reusable dataflow.

---

## 1. Project Overview

This project analyzes historical loan data to:

- Measure and monitor **loan default risk**
- Understand how **borrower demographics** and **financial profiles** influence default
- Provide **dashboard‑driven insights** for credit risk and portfolio management teams

The solution combines **dataflow‑based ETL**, **data modeling**, and **Power BI dashboards** to deliver a single source of truth for loan performance and default analytics.

---

## 2. Business Problem & Objectives

Lending institutions need to balance **growth** (loan approvals) with **risk** (defaults). Without robust analytics, they struggle to:

- Identify **high‑risk borrowers** early
- Track **year‑on‑year (YOY)** changes in loan and default amounts
- Understand how **income, employment type, education, and credit score** impact default rates

**Key objectives:**

- Quantify **default rate trends** over time
- Analyze **loan portfolio composition** by purpose, education, region, and credit score
- Profile borrowers by **age group, marital status, employment type, income bracket**
- Build an **interactive dashboard** for risk, portfolio, and customer analytics

---

## 3. Data & Features

**Data source:** Historical loan application and performance data (defaulters vs non‑defaulters).

**High‑level feature groups:**

- **Loan Details**
  - Loan amount, loan purpose (Home, Business, Education, Auto, Other)
  - Year of loan, loan status (Default / Non‑Default)
  - Upfront charges, interest rate (if available)

- **Borrower Demographics**
  - Age groups (Teens, Adults, Middle‑Age Adults, Senior Citizens)
  - Gender, marital status (Single, Married, Divorced)
  - Education level (High School, Bachelor’s, Master’s, PhD)
  - Region (if available)

- **Financial Profile**
  - Income and income brackets (Low, Medium, High)
  - Employment type (Full‑time, Part‑time, Self‑employed, Unemployed)
  - Mortgage / dependencies flags
  - Credit score & credit score bins (Very Low, Low, Medium, High)

- **Target**
  - Default flag (1 = Default, 0 = Non‑Default)

---

## 4. Solution Architecture & Dataflow

The project follows a **dataflow‑driven analytics pipeline**:

1. **Data Ingestion**
   - Import raw loan and customer data from CSV/Excel (and/or database)
   - Load into **Power BI Dataflow** (or equivalent ETL layer)

2. **Data Cleaning & Transformation**
   - Handle missing values and inconsistent categories
   - Derive **age groups, income brackets, credit score bins**
   - Create calculated fields for:
     - **Default Rate (%)**
     - **YOY Loan Amount Change**
     - **YOY Default Loan Amount Change**

3. **Data Modeling**
   - Build a **star schema** style model (Fact: Loans/Defaults, Dimensions: Customer, Date, Product, Credit)
   - Define **relationships**, **hierarchies**, and **DAX measures** for KPIs

4. **Reporting & Dashboards**
   - Design interactive **Power BI dashboards** for:
     - Financial risk metrics
     - Applicant demographics & profiles
     - Loan default trends and breakdowns

---

## 5. Dashboard Overview

The Power BI report is organized into multiple analytical views:

### 5.1 Financial Risk Metrics

- **YOY Loan Amount Change** (2013–2018)
- **YOY Default Loan Amount Change**
- Overall **loan amount vs defaulted loan amount**

**Business value:** Helps risk teams quickly see whether portfolio growth is **healthy** or driven by **rising defaults**.

---

### 5.2 Applicants Demographics & Financial Profile

Visuals include:

- **Loan Amount by Income Bracket** (Low, Medium, High)
- **Loan Amount by Employment Type** (Full‑time, Part‑time, Self‑employed)
- **Total Loan by Credit Score Bins** (Very Low, Low, Medium, High)
- **Average Loan Amount (High Credit Score) by Age Group & Marital Status**
- **Loans by Education Type** (High School, Bachelor’s, Master’s, PhD)
- **Loans by Mortgage / Dependencies flags**

**Business value:** Provides a 360° view of **who** is borrowing (and for how much) across income, education, and credit quality.

---

### 5.3 Loan Default & Risk Overview

Key visuals:

- **Default Rate (%) by Employment Type**
  - Compare Full‑time, Part‑time, Self‑employed, Unemployed
- **Yearly Default Rate %** (2013–2018)
- **Average Loan Amount by Age Group** (Teens, Adults, Middle‑Age, Senior)

**Business value:** Identifies **high‑risk segments** (e.g., certain employment types or age groups) and tracks how default behavior evolves over time.

---

### 5.4 Loan Portfolio Composition

- **Loan Amount by Purpose**
  - Home, Business, Education, Auto, Other
- **Loan distribution by Education, Credit Score, and Income**

**Business value:** Shows how the **portfolio is allocated** across products and borrower types, enabling better risk‑adjusted growth strategies.

---

## 6. Key Insights (Sample)

These are the types of insights the dashboard is designed to uncover:

- Certain **employment types** (e.g., self‑employed or unemployed) show **higher default rates** than full‑time employees.
- **YOY default loan amount** can move differently from overall loan growth, highlighting **risk build‑up years**.
- **High income** and **higher credit score bins** are associated with **larger loan amounts** but relatively **lower default rates**.
- Specific **loan purposes** (e.g., business or education) may carry **higher risk** compared to home or auto loans.
- **Age group and marital status** combinations reveal subtle differences in both **average ticket size** and **default behavior**.

> These patterns help credit teams refine **approval rules, pricing, and collection strategies**.

---

## 7. How to Use This Project

### Prerequisites

- **Power BI Desktop** (recommended)
- Raw dataset files (loan applications and customer profiles)
- Optional: Access to the configured **Power BI Dataflow** / data source

### Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/Saksham-Pratap-Singh/Loan_Default_Analytics_Dataflow.git
   cd Loan_Default_Analytics_Dataflow
