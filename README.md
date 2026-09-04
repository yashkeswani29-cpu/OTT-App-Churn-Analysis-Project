**# OTT Subscriber Churn Analytics & Risk Scoring Pipeline**

## Overview

Engineered an end-to-end churn analytics pipeline for an OTT subscription platform by integrating multi-table subscriber data across acquisition type, contract structure, and plan tier (20+ KPIs). The project identifies critical drivers of subscriber loss, quantifies MRR leakage and Customer Lifetime Value (CLTV) erosion, and provides a data-backed retention framework to reduce involuntary churn.

---

## Key Metrics & Analytics Formulas

| Metric | Business Definition / SQL Logic |
| --- | --- |
| **Churn Rate** | `Churned Customers / Total Customers` |
| **Churn by Plan Type** | `Churn Rate GROUP BY plan_type (Basic / Standard / Premium)` |
| **Churn by Location** | `Churn Rate GROUP BY country, state` |
| **Retention Rate** | `1 - Churn Rate` |
| **ARPU** | `SUM(monthly_charges) / COUNT(active customerid)` |
| **Average Customer Tenure** | `AVG(DATEDIFF(cancellation_date OR NOW(), subscription_start_date))` |
| **Revenue at Risk** | `SUM(monthly_charges) WHERE churn_score > 70` |
| **Escalation Rate** | `(SUM(escalations) / COUNT(complaints)) * 100` |
| **Avg Complaints per Customer** | `COUNT(complaints) / COUNT(DISTINCT customerid)` |
| **Support Correlation** | `Churn Rate WHERE escalations >= 1 vs 0` |

---

## Key Insights

* **Churn & Contract Disparity:** The platform has an overall churn rate of **28.6%** (Retention Rate: 71.4%). Monthly contract subscribers churn at **55.6%**, which is **6.7x** higher than annual contract subscribers (**8.3%**).
* **Revenue & CLTV Impact:** Churn resulted in a total revenue loss of **18%**. Specifically, 6 high-risk churned customers directly accounted for **$73.94/mo in MRR leakage** and **$2,047 in CLTV erosion**.
* **Plan Tier Concentration:** Most churn occurs within the **Basic subscription plan**.
* **Temporal & Geographic Spikes:** A peak in churn occurred in **September 2024**, with **Karnataka** identified as the most impacted state.
* **Customer Tenure & ARPU:** Average customer tenure is **1,451 days**, with an Average Revenue Per User (ARPU) of **Rs 18.8**.
* **Support Escalations:** Cross-functional support data shows escalated interactions are disproportionately concentrated among churned cohorts. Primary cancellation drivers include competitor switching, pricing sensitivity, and content dissatisfaction.

---

## Strategic Action Plan

* **Investigate September Spike in Karnataka:** Conduct root-cause analysis on potential regional price increases, system outages, or technical issues during September 2024.
* **Contract & Pricing Adjustments:** Review Basic plan price adjustments and test incentives to migrate monthly subscribers to annual plans to reduce the 55.6% churn rate.
* **Competitor Benchmarking:** Analyze market positioning and competitor offerings to counter user migration.
* **Targeted Proactive Retention:** Segment customers by high/medium churn risk and CLTV to prioritize outreach via multi-channel campaigns (Email, SMS, Calls) and resolve open support escalations.
