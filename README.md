# Amazon Repeat Purchase Root Cause Analysis

## Executive Summary

Amazon observed a significant decline in Repeat Purchase Rate (RPR) among Tier-1 city customers.

| Quarter | Repeat Purchase Rate |
|----------|----------|
| Q1 | 52% |
| Q2 | 44% |
| Q3 | 34% |

The objective of this project was to identify the root cause behind the decline in repeat purchases and recommend actionable business solutions.

Using SQL, cohort analysis, customer segmentation, behavioral event analysis, funnel analytics, delivery experience analysis, and cart abandonment analysis, the investigation revealed that the decline was primarily driven by changing customer delivery expectations.

The rise of Quick Commerce platforms has significantly altered customer behavior in Tier-1 cities, particularly among younger non-prime customers. Categories heavily associated with instant delivery such as Beauty & Personal Care, Grocery, Fashion, and Convenience Products experienced the largest increase in cart abandonment and decline in repeat purchases.

---

## Business Problem

Repeat Purchase Rate (RPR) is one of the most important retention metrics for any e-commerce business.

A customer who places multiple orders over time contributes significantly more revenue and customer lifetime value compared to one-time buyers.

During quarterly business reviews, Amazon identified a sudden decline in Repeat Purchase Rate among Tier-1 city customers:

- Q1 Repeat Purchase Rate: 52%
- Q2 Repeat Purchase Rate: 44%
- Q3 Repeat Purchase Rate: 34%

The business team requested a detailed Root Cause Analysis (RCA) to determine:

- Why repeat purchases are declining
- Which customer segments are most affected
- Whether the issue is operational, behavioral, competitive, or product-related
- What actions can recover customer retention

---

## Definition of Repeat Purchase

A customer is considered a repeat customer if they place more than one order on different days within the same quarter.

Same-day purchases are not considered repeat purchases.

### Formula

```text
Repeat Purchase Rate (RPR)

=
Customers with more than 1 order in a quarter
--------------------------------------------------
Total customers who placed at least 1 order
```

---

## Business Questions

### External Factors

1. Is the decline caused by economic slowdown?
2. Is there an industry-wide slowdown?
3. Have competitors launched aggressive initiatives?
4. Has Quick Commerce expanded into new categories?
5. Are there seller or vendor-related issues?
6. Have competitors improved delivery speed?

### Internal Factors

1. Has customer acquisition quality deteriorated?
2. Are customers inactive after their first purchase?
3. Has delivery SLA worsened?
4. Has product satisfaction declined?
5. Have complaints increased?
6. Have returns increased?
7. Where are users dropping in the funnel?
8. Has cart abandonment increased?
9. Which customer segments contribute most to the decline?
10. Which product categories are affected?

---

# Dataset

The analysis uses the following tables:

| Table | Description |
|---------|---------|
| customers | Customer demographics and Prime membership |
| orders | Order transactions and delivery information |
| order_items | Product-level order details |
| products | Product category information |
| product_reviews | Customer ratings and reviews |
| returns | Product return information |
| cs_support | Customer complaints and support tickets |
| user_events | Website and app behavioral event tracking |

---

# Analytical Framework

The investigation followed a hypothesis-driven approach.

## Step 1

Validate external causes

- Economy
- Industry
- Competition
- Vendor ecosystem
- Quick Commerce expansion

## Step 2

Validate customer quality

- Acquisition channel analysis
- Customer composition analysis

## Step 3

Validate post-purchase engagement

- Active customer analysis
- Return visit behavior

## Step 4

Validate customer experience

- Delivery SLA analysis
- Reviews
- Complaints
- Returns

## Step 5

Perform funnel analysis

- Browse
- Search
- Product page
- Cart

## Step 6

Perform cart abandonment analysis

- Delivery expectations
- Product categories

## Step 7

Analyze Prime membership impact

## Step 8

Analyze demographic contribution

## Step 9

Identify root cause

## Step 10

Recommend recovery strategy

---

# Hypotheses Tested

## H1: Customer acquisition quality has deteriorated

### Result

❌ Rejected

Customer acquisition quality remained stable across all quarters.

Acquisition channels showed consistent distribution:

| Channel | Q1 | Q2 | Q3 |
|----------|----------|----------|----------|
| Direct | 74.78% | 74.26% | 76.22% |
| Affiliate | 18.30% | 18.45% | 16.80% |
| Ads | 6.92% | 7.29% | 6.97% |

---

## H2: Customers become inactive after their first purchase

### Result

❌ Rejected

Customer activity remained relatively stable.

| Quarter | Active Customers |
|----------|----------|
| Q1 | 70.51% |
| Q2 | 73.67% |
| Q3 | 69.09% |

---

## H3: Delivery SLA has worsened

### Result

❌ Rejected

Delivery SLA performance remained stable and even improved slightly.

Missed SLA rates did not increase during the period.

---

## H4: Product satisfaction has deteriorated

### Result

❌ Rejected

Review sentiment remained stable.

Negative reviews showed no meaningful increase across quarters.

---

## H5: Complaints and returns increased

### Result

❌ Rejected

Complaint rates remained stable.

Return rates remained stable or improved slightly.

---

## H6: Customers abandon carts due to delivery expectations

### Result

✅ Supported

Strong evidence suggests delivery expectations influence purchasing behavior.

---

## H7: Quick Commerce has changed customer behavior

### Result

✅ Supported

Multiple independent observations support this hypothesis.

---

# Analysis & Findings

## Finding 1: Customer Quality Remained Stable

Customer acquisition channels remained consistent across quarters.

No evidence suggests lower-quality customers entered the platform.

### Conclusion

Customer quality is not responsible for the repeat purchase decline.

---

## Finding 2: User Engagement Remained Stable

Customers continued returning to the platform after their first purchase.

Activity rates remained nearly unchanged.

### Conclusion

The issue is not caused by customer inactivity.

---

## Finding 3: Product Experience Remained Stable

Analysis of:

- Reviews
- Complaints
- Returns

showed no meaningful deterioration.

### Conclusion

Product quality and customer satisfaction are not responsible.

---

## Finding 4: Users Showed Higher Purchase Intent

Among non-repeat customers:

| Quarter | Browse | Search |
|----------|----------|----------|
| Q1 | 47% | 52% |
| Q2 | 35% | 64% |
| Q3 | 25% | 74% |

Users increasingly shifted from browsing behavior to direct search behavior.

### Interpretation

Customers displayed stronger purchase intent rather than weaker intent.

---

## Finding 5: Funnel Conversion Remained Strong

Search funnel conversion remained healthy.

| Quarter | Product Page Visit | Added To Cart |
|----------|----------|----------|
| Q1 | 67% | 80% |
| Q2 | 66% | 76% |
| Q3 | 73% | 83% |

### Interpretation

Customers still discovered products and added them to cart successfully.

The problem occurs after cart interaction.

---

## Finding 6: Delivery Expectations Worsened for Non-Repeat Customers

Expected delivery times shown in cart shifted significantly.

### Non-Repeat Customers

| Quarter | Within 2 Days |
|----------|----------|
| Q1 | 61% |
| Q2 | 50% |
| Q3 | 39% |

### Interpretation

Customers increasingly encountered longer delivery promises.

---

## Finding 7: Repeat Customers Received Faster Delivery Promises

### Repeat Customers

| Quarter | Within 2 Days |
|----------|----------|
| Q1 | 70% |
| Q2 | 81% |
| Q3 | 87% |

### Interpretation

Customers who continued purchasing generally saw faster delivery promises.

---

## Finding 8: Non-Prime Customers Drove the Decline

The largest decline occurred among non-prime customers.

### Observation

Non-prime repeat customers dropped from:

- 12.54% (Q1)
- 7.27% (Q2)
- 1.03% (Q3)

### Interpretation

Prime membership acts as a protective factor against churn.

---

## Finding 9: Younger Customers Were Most Impacted

More than 80% of affected customers belonged to:

- 18–24 age group
- 25–34 age group

Prime adoption among these groups was extremely low.

### Interpretation

Younger customers appear significantly more sensitive to delivery speed.

---

## Finding 10: Cart Abandonment Increased in Specific Categories

Largest increases occurred in:

- Beauty & Personal Care
- Electronics
- Fashion
- Home Convenience Products

### Interpretation

These categories are highly aligned with Quick Commerce purchasing behavior.

---

# Additional Validation Analysis

## Delivery Time Sensitivity by Age Group

Analysis showed that customers aged 18–34 accounted for the majority of repeat purchase decline.

These customers are:

- More likely to adopt convenience services
- More sensitive to delivery speed

### Conclusion

Younger customers demonstrate lower tolerance for longer delivery promises.

---


## Grocery and Beauty Category Comparison

The largest declines occurred in categories such as:

- Grocery
- Beauty & Personal Care
- Fashion

These categories are strongly associated with same-day delivery expectations.

### Conclusion

Categories most exposed to Quick Commerce competition experienced the greatest deterioration.

---

## Quick Commerce Dominated Category Comparison

### Most Affected

- Beauty & Personal Care
- Grocery & Essentials
- Fashion
- Convenience Electronics

### Least Affected

- Books
- Education Products
- Furniture

### Conclusion

Products commonly purchased through Quick Commerce experienced significantly higher abandonment rates.

This provides additional evidence supporting the delivery expectation hypothesis.

---

# Root Cause

The decline in repeat purchases is primarily driven by changing delivery expectations among customers.

Quick Commerce platforms have fundamentally changed customer expectations in Tier-1 cities.

Customers who previously accepted 3–4 day delivery now increasingly expect:

- Same-day delivery
- Next-day delivery
- Instant fulfillment

This effect is strongest among:

- Non-prime customers
- Younger customers
- Tier-1 city customers
- Quick Commerce dominated categories

As delivery expectations rise, cart abandonment increases, resulting in lower repeat purchases.

---

# Recommendations

## Short-Term Initiatives

### Increase Prime Adoption

Actions:

- Student discounts
- Free trials
- Youth-focused promotions

Expected Benefit:

- Faster delivery eligibility
- Reduced delivery fees
- Improved retention

---

### Warehouse Optimization

Actions:

- Move high-demand inventory closer to customers
- Increase Tier-1 city inventory coverage

Expected Benefit:

- Faster fulfillment
- Lower abandonment

---

### Improve Delivery Communication

Actions:

- Highlight fast-delivery products
- Promote same-day delivery eligibility

Expected Benefit:

- Better customer confidence
- Higher cart conversion

---

### Category Prioritization

Focus on:

- Grocery
- Beauty
- Fashion
- Convenience products

Expected Benefit:

- Immediate impact on repeat purchase recovery

---

## Long-Term Initiatives

### Launch Quick Commerce Offering

Pilot Program:

- Tier-1 cities
- High-frequency categories
- Same-day fulfillment

Expected Benefit:

- Protect market share
- Improve retention
- Increase customer lifetime value

---

### Hyperlocal Fulfillment Network

Actions:

- Dark stores
- Micro-fulfillment centers
- Local warehouse expansion

Expected Benefit:

- Sustainable delivery advantage

---

# Project Highlights

### Business Analytics

- Root Cause Analysis
- Hypothesis Testing
- Customer Retention Analysis
- Customer Segmentation
- Cart Abandonment Analysis
- Customer Journey Analysis
- Delivery Experience Analysis
- Strategic Recommendation Framework

### Product Analytics

- Funnel Analysis
- Behavioral Event Analysis
- Cohort Analysis
- User Journey Analysis
- Conversion Analysis
- Retention Diagnostics

### Strategic Thinking

- Competitor Assessment
- Market Trend Evaluation
- Quick Commerce Impact Analysis
- Short-Term Recovery Planning
- Long-Term Business Strategy

---

# Technical Skills Demonstrated

## SQL

- Common Table Expressions (CTEs)
- Window Functions
- Conditional Aggregation
- CASE Statements
- Multi-table Joins
- Date Functions
- Cohort Analysis
- Funnel Analysis
- Event Stream Analysis
- Pivot Reporting
- Crosstab Analysis

## Analytics

- Root Cause Analysis
- Hypothesis Testing
- Cohort Segmentation
- Behavioral Analytics
- Funnel Analytics
- Retention Analysis
- Customer Segmentation
- KPI Development

## Business

- Customer Lifecycle Analysis
- Customer Retention Strategy
- Competitive Analysis
- Delivery Experience Optimization
- E-commerce Analytics
- Product Analytics

---

# Repository Structure

```text
amazon-repeat-purchase-root-cause-analysis/

├── README.md

├── docs/
│   ├── Executive_Summary.md
│   ├── Business_Case_Study.md
│   ├── Project_Highlights.md
│   └── Technical_Skills_Highlights.md

├── schema/
│   ├── er_diagram.png
│   └── database_schema.sql

├── sql/
│   ├── 01_repeat_purchase_rate.sql
│   ├── 02_customer_quality_analysis.sql
│   ├── 03_active_user_analysis.sql
│   ├── 04_delivery_experience_analysis.sql
│   ├── 05_customer_feedback_analysis.sql
│   ├── 06_funnel_analysis.sql
│   ├── 07_cart_analysis.sql
│   ├── 08_prime_membership_analysis.sql
│   ├── 09_demographic_analysis.sql
│   ├── 10_category_analysis.sql
│   └── 11_root_cause_analysis.sql

├── data/
│   └── sample_dataset.csv

└── images/
    ├── er_diagram.png
    ├── funnel_analysis.png
    ├── cart_abandonment.png
    └── root_cause_driver_tree.png
```

---

# Author

**Mohammed Tariq**

Data Analytics | Product Analytics | Business Analytics

Focused on solving real-world business problems using SQL, analytics, experimentation, and data-driven decision making.
