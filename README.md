# NL Banking | Customer Behaviour, Transaction Performance & Risk Analysis

**Business Analytics | Microsoft Excel | Tableau**

An end-to-end banking analytics case study focused on understanding customer transaction behaviour, transaction performance, merchant activity and fraud exposure. The project combines multi-table data analysis, KPI development, hypothesis validation and interactive Tableau dashboards to identify meaningful business patterns and translate them into actionable recommendations.

---

## 1. Project Overview

The project examines a banking transaction dataset comprising 100,000 transactions linked with customers, cards and merchants.

The primary objective is to identify which customer, transaction and merchant dimensions create meaningful differences in engagement, transaction value and observed fraud exposure.

Rather than treating every variable as equally important, the analysis evaluates five business hypotheses, validates them against descriptive evidence and prioritises the findings that provide the clearest decision-making signals.

### Dataset at a Glance

| Dataset Component | Records |
|---|---:|
| Customers | 25,000 |
| Transactions | 100,000 |
| Cards | 32,457 |
| Merchants | 500 |

### Executive KPI Summary

| KPI | Observed Value |
|---|---:|
| Total Transaction Value | ₹164.25 Cr |
| Average Transaction Value | ₹16,424.67 |
| Transaction Success Rate | 91.15% |
| Fraud Rate | 5.38% |

## 2. Business Objective & Key Questions

The analysis addresses five core business questions:

1. Which customer behaviours are associated with stronger transaction engagement?
2. Which customer and merchant dimensions create meaningful differences in transaction value?
3. Which transaction channels and payment methods account for the largest operational volumes?
4. Where is observed fraud exposure concentrated, particularly across international transactions?
5. Which analytical findings provide sufficiently strong evidence to justify management attention?

The intended outcome is an evidence-led understanding of customer engagement, transaction economics, operational performance and risk prioritisation.

## 3. Data Model & Preparation

The project uses four interconnected datasets, organised around transaction-level analysis.

| Source Table | Analytical Role |
|---|---|
| Transaction Data | Transaction ID, amount, channel, status, fraud indicator and international activity |
| Customer Data | Customer demographics, income, segment and geography |
| Cards Data | Card ownership and card-level characteristics |
| Merchant Table | Merchant category, risk classification and geography |

**Key relationships**

- Transaction Data → Customer Data using `Customer_ID`
- Transaction Data → Cards Data using `Card_ID`
- Transaction Data → Merchant Table using `Merchant_ID`

The Excel workbook maintains separate raw-data and analytical layers, including dedicated EDA, hypothesis-validation and recommendation worksheets. Tableau uses the same underlying analytical structure to maintain consistency between analysis and stakeholder reporting.

### Data Validation

- 100,000 transaction records and 25,000 customer records were included in the completed analysis.
- No exact duplicate records were identified in the documented audit.
- Required analytical keys were available for the defined KPI calculations.
- Core calculated measures were applied consistently across the analytical outputs.

## 4. KPI & Measurement Framework

Five primary measures were established to evaluate performance from different business perspectives.

| KPI | Definition | Business Purpose |
|---|---|---|
| Transaction Volume | Count of transactions | Measure operational scale |
| Average Transaction Value | Average transaction amount | Evaluate transaction value |
| Transactions per Customer | Transaction count relative to customer count | Measure engagement frequency |
| Success Rate | Successful transactions / Total transactions | Monitor transaction reliability |
| Fraud Rate | Fraud transactions / Total transactions | Monitor observed risk exposure |

The framework deliberately distinguishes volume, value, reliability and risk. High transaction volume is not automatically interpreted as high transaction value or higher risk.

## 5. Hypothesis Framework & Validation

Five hypotheses were developed around the key business questions and evaluated using descriptive evidence.

| ID | Hypothesis | Evidence | Result |
|---|---|---|---|
| H1 | Customers owning more cards have higher transaction engagement. | Average transactions per customer increase from 3.07 to 6.22 to 9.09 across one, two and three cards. | Supported |
| H2 | Higher-income customers have higher transaction values. | Average transaction value increases from ₹13,988.68 in Q1 to ₹17,350.39 in Q4. | Supported |
| H3 | International transactions have materially different value and risk characteristics. | Average transaction value: ₹37,022.80 vs ₹15,333.03 domestically; fraud rate: 19.15% vs 4.65%. | Strongly Supported |
| H4 | Higher merchant risk classifications are associated with higher observed fraud rates. | Fraud rates remain almost identical: High 5.40%, Low 5.38%, Medium 5.36%. | Not Supported |
| H5 | Customer segments materially differ in transaction engagement. | Average transactions per customer remain between 3.92 and 4.04 across segments. | Not Supported |

The validation labels represent the strength of observed descriptive patterns. They do not imply statistical significance or establish causality.

**Key interpretation:** Card ownership and international activity provide the strongest decision signals. Merchant risk classifications and customer segment labels show limited differentiation in the available data.

## 6. Key Business Findings

### A. Customer Engagement & Value

**Card ownership is the clearest engagement signal.**

Average transactions per customer increase substantially with card ownership:

- One card: 3.07
- Two cards: 6.22
- Three cards: 9.09

In contrast, customer segments show limited separation, with averages between 3.92 and 4.04 transactions per customer. Age groups also remain closely grouped, approximately 3.93–4.08.

Income demonstrates a clearer association with transaction value than with transaction frequency, supporting its use as a secondary value-targeting dimension.

### B. Transaction Channel Performance

POS is the dominant transaction channel, accounting for 48,341 transactions, followed by Mobile App with 25,772.

| Channel | Transactions | Success Rate |
|---|---:|---:|
| POS | 48,341 | 91.24% |
| Mobile App | 25,772 | 91.17% |
| ATM | 15,937 | 91.12% |
| Online Web | 9,950 | 90.73% |

Despite differences in volume, channel success rates remain closely grouped between 90.73% and 91.24%.

Debit Card is the leading payment method, representing 51.2% of transactions, followed by Credit Card at 35.4%, UPI at 11.0% and Net Banking at 2.4%.

### C. Merchant Category & Transaction Value

Transaction values vary considerably across merchant categories.

| Merchant Category | Average Transaction Value |
|---|---:|
| Electronics | ₹37,333.23 |
| Hospital | ₹35,468.87 |
| Education | ₹34,989.99 |
| Airline | ₹33,424.42 |
| Hotel | ₹19,632.24 |
| Food Delivery | ₹2,986.03 |

These differences indicate that merchant category can support differentiated value analysis, category-level monitoring and targeted propositions.

### D. International Transaction Risk

International transactions account for approximately 5.0% of total transaction volume (5,033 of 100,000), but show materially higher average transaction value and fraud exposure.

| Measure | Domestic | International |
|---|---:|---:|
| Average Transaction Value | ₹15,333.03 | ₹37,022.80 |
| Fraud Rate | 4.65% | 19.15% |

International fraud is more than four times the domestic rate, making this the clearest risk-prioritisation signal in the analysis.

### E. Merchant Risk Classification

Observed fraud rates across merchant risk classifications are:

- High: 5.40%
- Low: 5.38%
- Medium: 5.36%

The minimal variation indicates that the existing merchant risk labels do not materially differentiate observed fraud exposure on their own.

### F. Merchant Geography

Average transaction value varies across states.

West Bengal records the highest average transaction value among the listed states at ₹20,125.77, followed by Tamil Nadu at ₹19,037.82 and Uttar Pradesh at ₹19,037.70.

Geographic performance provides additional context for transaction-value analysis and market-level monitoring.

## 7. Tableau Dashboard & Stakeholder Reporting

The Tableau reporting layer is structured around three stakeholder-focused analytical views.

**Executive Overview**

Provides the overall transaction baseline and operating-health perspective through KPI cards, transaction volume by channel and channel success rates.

**Customer & Value**

Examines card ownership, customer engagement, merchant category value and income-related transaction-value differences.

**Risk & Transactions**

Highlights domestic versus international transaction value, fraud exposure and merchant-risk classification performance.

The dashboard uses focused filters for transaction type, customer segment, income quartile and merchant risk level to support targeted exploration.

### Interactive Tableau Dashboard

[**View the NL Banking Executive Dashboard on Tableau Public**](https://public.tableau.com/app/profile/nipun.singh7731/viz/NL_Banking_17890288455950/NLBankingExecutiveDashboard?publish=yes)

![NL Banking Tableau Dashboard Preview](Dashboard%20Preview/NL_Banking_Tableau_Dashboard.png)

## 8. Business Recommendations

The analysis translates the strongest observed patterns into six practical recommendations.

| Recommendation | Proposed Action | Priority |
|---|---|---|
| Deepen Multi-card Engagement | Target customers with two or three cards through cross-selling, bundled benefits and relationship-led engagement. | High |
| Strengthen International Controls | Apply differentiated monitoring to international and high-value cross-border transactions. | High |
| Improve Fraud Detection | Supplement merchant-risk labels with transaction amount, channel, device, payment method, international status and behavioural signals. | High |
| Protect High-volume Channels | Prioritise POS and other major transaction touchpoints for reliability monitoring. | High |
| Use Merchant Category for Value Targeting | Develop category-level targeting and monitoring for higher-value spending contexts. | Medium |
| Use Income Selectively | Treat income as a supporting signal for premium and value propositions, rather than a primary engagement predictor. | Medium |

### Suggested Success Measures

- Average transactions per customer for multi-card engagement.
- International fraud rate, alongside false-positive monitoring.
- Fraud-rate differentiation across risk classifications.
- Transaction success rate by channel.
- Average transaction value in priority merchant categories.

## 9. Limitations & Next Steps

### Analytical Limitations

- The analysis is descriptive and does not establish causal relationships.
- Additional time periods would improve trend stability and enable stronger comparisons.
- External market benchmarks were outside the available scope.
- Operating costs and profitability measures were not available.

### Recommended Next Steps

1. Monitor core KPIs monthly or quarterly and refresh the hypotheses as new data becomes available.
2. Pilot multi-card engagement initiatives and evaluate changes in transaction frequency.
3. Implement targeted international monitoring and measure changes in fraud exposure.
4. Enrich fraud analysis with behavioural, device, channel and transaction-level signals.
5. Use Tableau for stakeholder monitoring and Excel as the traceable analytical workbook.

## 10. Project Deliverables

| Deliverable | File |
|---|---|
| Detailed Business Analytics Report | `NL_Banking BRD.pdf` |
| Excel Analysis Workbook | `NL_Banking_Analysis_.xlsx` |
| Interactive Tableau Dashboard | Tableau Public link above |
| Tableau Dashboard Preview | `Dashboard Preview/` |

---

**Project:** NL Banking — Customer Behaviour, Transaction Performance & Risk Analysis  
**Tools:** Microsoft Excel, Tableau  
**Project Type:** Business Analytics & Data Analysis Case Study  
**Prepared by:** Nipun Singh
