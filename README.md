# 🛒 E-Commerce Cart Abandonment Analysis

## 📌 Project Overview

Cart abandonment is one of the biggest challenges in e-commerce. A customer may add a product to their cart but leave without completing the purchase.

This project analyzes **February 2020 e-commerce customer behavior data** to understand:

- How often customers abandon their carts
- Where customers drop off in the purchase journey
- Which categories, brands and price ranges have higher abandonment
- How customer and session behavior differs between purchasers and abandoners
- Which traffic sources and device types show higher abandonment
- Whether session depth and engagement affect conversion
- Which segments have high traffic but low conversion
- What patterns are most strongly associated with cart abandonment
- Where the checkout funnel has the biggest drop-off and what the product team should prioritize

The analysis was completed using **Python, SQL and Power BI**, with each tool used for a different part of the analysis.

---

## 🎯 Business Questions

The project answers the following business questions:

1. What is the overall cart abandonment and conversion rate?
2. Which device types have the highest cart abandonment?
3. Which traffic sources have the highest abandonment?
4. How does user engagement differ between purchasers and abandoners?
5. Does session depth affect the likelihood of purchase?
6. Which customer or session segments show the highest abandonment?
7. Which segments have high traffic but low conversion?
8. What are the strongest patterns associated with cart abandonment?
9. Where in the checkout flow are customers dropping off most, and what should the product team fix first?

---

## 📊 Dataset

**Source:** Kaggle  
**Dataset:** E-Commerce Behavior Data from Multi-Category Store

The original dataset contains e-commerce events such as:

- `view`
- `cart`
- `purchase`

For this project, the analysis was focused on the **February 2020 data**.

The February dataset contains approximately **55 million events**.

Because the full event dataset was too large to work with comfortably in memory, the data was processed using **chunking with Pandas**.

The analysis eventually focused on the **cart-event dataset**, containing approximately **2.65 million cart events**.

---

## 🛠️ Tools & Technologies

### Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

### SQL
- MySQL

### Visualization
- Microsoft Power BI

### Other
- GitHub
- Excel/CSV

---

# 🔍 Project Workflow

The project was completed in three major stages:

```text
Raw E-Commerce Data
        ↓
Python Data Processing & EDA
        ↓
Cart-Level Dataset
        ↓
SQL Business Analysis
        ↓
Power BI Dashboard
        ↓
Business Insights & Recommendations
```

---

# 1️⃣ Data Processing & Exploratory Data Analysis

Python was used to process the large February dataset and perform exploratory analysis.

Because the dataset contained tens of millions of rows, the file was processed in **chunks instead of loading the entire dataset into memory at once**.

### Key processing steps

- Loaded the February dataset in chunks
- Filtered cart events
- Created a cart-level analysis dataset
- Removed duplicate records
- Converted and extracted date/time information
- Added:
  - Date
  - Hour
  - Day of week
  - Day name
- Identified whether each cart event eventually resulted in a purchase
- Created customer and session-level metrics
- Analyzed abandonment across different dimensions

### Final cart dataset

The processed cart dataset contained approximately:

**2.65 million cart events**

with the following main fields:

```text
event_time
event_type
product_id
category_id
category_code
brand
price
user_session
purchased
date
hour
day_of_week
day_name
```

---

# 2️⃣ Exploratory Data Analysis

The EDA focused on identifying patterns behind cart abandonment.

### Overall cart behavior

| Outcome | Cart Events |
|---|---:|
| Abandoned | 1,363,052 |
| Purchased | 1,293,476 |
| Total | 2,656,528 |

This shows that cart abandonment is a significant part of the customer journey.

---

## 🔄 Funnel Analysis

The broader February event data was also used to understand the overall customer funnel.

| Funnel Stage | Events |
|---|---:|
| Views | 51,232,669 |
| Cart | 2,885,608 |
| Purchase | 1,200,288 |

Key event-level conversion rates:

- **View → Cart:** 5.63%
- **Cart → Purchase:** 41.60%
- **View → Purchase:** 2.34%

Session-level analysis produced:

- **View → Cart:** 10.47%
- **Cart → Purchase:** 42.17%
- **View → Purchase:** 5.31%

This helped separate the problem of **getting customers to add products to their cart** from the problem of **converting carts into purchases**.

---

# 📈 Key EDA Findings

## Category

Abandonment varied significantly across product categories.

Examples:

- Construction tools/light: **47.64%**
- Sport/bicycle: **61.29%**
- Apparel/shoes: **63.49%**
- Unknown category: **68.91%**

This indicates that product category can have a meaningful relationship with abandonment.

---

## 🏷️ Brand

Some brands showed extremely high abandonment rates.

Examples from the analysis included:

- Silverlit: **97.76%**
- Nokian: **88.26%**

These brands may require further investigation into factors such as pricing, availability, product information or customer intent.

---

## 💰 Price

The cart price distribution showed:

- Mean price: **291.55**
- Median price: **172.44**
- Maximum price: **2,574.07**

Abandonment by price band:

| Price Band | Abandonment |
|---|---:|
| $0–50 | 65.64% |
| $50–100 | 60.03% |
| $100–200 | 50.69% |

Lower-priced carts showed higher abandonment in this dataset.

---

## 🛍️ Number of Products

Customers with fewer products in their cart were more likely to abandon.

| Products in Cart | Abandonment |
|---|---:|
| 1 product | 60.16% |
| 2 products | 39.82% |

This suggests that customers with larger or more deliberate shopping baskets may have stronger purchase intent.

---

## 👤 Session Depth

Session behavior also showed a relationship with abandonment.

| Session Count | Abandonment |
|---|---:|
| 1 session | 65.42% |
| 6+ sessions | 45.94% |

Customers with deeper engagement showed lower abandonment.

This suggests that **engagement and purchase intent are closely connected**.

---

# 3️⃣ SQL Analysis

SQL was used to answer the project's business questions using structured queries.

The SQL analysis focused on:

- Overall abandonment
- Conversion rates
- Device-level performance
- Traffic-source performance
- Purchaser vs abandoner behavior
- Session depth
- Customer/session segmentation
- High-traffic low-conversion segments
- Strongest abandonment patterns

SQL helped transform the processed data into business-focused metrics rather than only descriptive statistics.

---

# 4️⃣ Power BI Dashboard

Power BI was used to turn the analysis into an interactive business dashboard.

### Dashboard Structure

### Page 1: Executive Overview

Contains:

- Total cart sessions
- Purchased sessions
- Abandoned sessions
- Cart abandonment rate
- Cart → Purchase rate
- Overall conversion
- February trend

The page provides a quick overview of the overall business performance.

---

### Page 2: Abandonment Drivers

Analyzes abandonment across:

- Device
- Traffic source
- Category
- Brand
- Price band
- Product count

This page helps identify the major areas associated with customer drop-off.

---

### Page 3: Customer & Session Behavior

Analyzes:

- Session depth
- Customer engagement
- Purchaser vs abandoner behavior
- Customer/session characteristics
- Behavioral differences between converters and abandoners

---

### Page 4: Checkout Drop-off

Focuses on the customer journey and identifies where the largest drop-offs occur.

The purpose of this page is to answer:

> **Where are customers dropping off most, and what should the product team fix first?**

The dashboard uses the analysis to highlight the most important areas for product improvement rather than simply showing descriptive charts.

---

# 💡 Key Business Insights

The analysis showed several important patterns:

### 1. Cart abandonment is a major conversion problem

A large proportion of customers who add products to their cart do not complete the purchase.

This makes the cart-to-purchase stage an important area for optimization.

### 2. Customer engagement matters

Customers with deeper session activity showed lower abandonment than customers with very limited engagement.

This suggests that encouraging meaningful engagement may improve purchase intent.

### 3. Product characteristics matter

Abandonment varies across:

- Categories
- Brands
- Price ranges
- Number of products in the cart

Therefore, cart abandonment is not caused by one single factor.

### 4. Some segments require deeper investigation

Certain brands and categories showed unusually high abandonment.

These segments could be investigated further for:

- Pricing issues
- Product availability
- Product information
- Customer intent
- Delivery/shipping concerns
- Checkout friction

### 5. High traffic does not always mean high conversion

Some segments can attract significant customer traffic while still producing relatively weak conversion.

These segments represent potential opportunities because improving conversion there could have a larger business impact.

---

# 🚀 Product Recommendations

Based on the analysis, the product team should prioritize:

### 1. Reduce friction at the largest checkout drop-off

Identify the exact stage where customers are leaving and simplify that step.

Possible areas to investigate:

- Checkout form complexity
- Payment friction
- Shipping information
- Unexpected costs
- Login/account requirements
- Page performance

### 2. Investigate high-abandonment categories and brands

Focus on categories and brands with unusually high abandonment rates.

Check whether the issue is related to:

- Price
- Product availability
- Product information
- Customer expectations
- Delivery options

### 3. Improve engagement before checkout

Customers with deeper engagement showed stronger purchase behavior.

Potential actions include:

- Better product recommendations
- Related products
- Product comparisons
- Reviews and ratings
- Clear product information

### 4. Prioritize high-traffic, low-conversion segments

Improving a low-conversion segment with substantial traffic can potentially create a larger impact than optimizing a small segment with very high abandonment.

### 5. Monitor abandonment continuously

Cart abandonment should be tracked by:

- Device
- Category
- Brand
- Traffic source
- Price
- Customer behavior
- Session depth

This allows the business to identify new problems as customer behavior changes.

---

# 📁 Repository Structure

```text
Ecommerce-Cart-Abandonment-Analysis/
│
├── Python/
│   └── Ecommerce_Cart_Abandonment_EDA.ipynb
│
├── SQL/
│   └── Ecommerce_Cart_Abandonment_Analysis.sql
│
├── Power BI/
│   └── Ecommerce_Cart_Abandonment_Dashboard.pbix
│
├── Documentation/
│   └── EDA_Summary.pdf
│
└── README.md
```

---

# 📊 Project Outcome

This project demonstrates an end-to-end data analytics workflow:

```text
Large Raw Dataset
        ↓
Data Processing
        ↓
Exploratory Data Analysis
        ↓
Business Questions
        ↓
SQL Analysis
        ↓
Interactive Power BI Dashboard
        ↓
Business Insights
        ↓
Product Recommendations
```

The main goal was not simply to calculate an abandonment rate, but to understand **why customers abandon their carts, which segments are most affected, where the customer journey loses users, and what the business should investigate or improve first.**

---

# 🧠 Skills Demonstrated

- Data Cleaning
- Data Processing
- Exploratory Data Analysis
- Large Dataset Handling
- Pandas
- NumPy
- SQL
- MySQL
- Business Analysis
- Funnel Analysis
- Customer Segmentation
- Behavioral Analysis
- Conversion Analysis
- Power BI
- Data Visualization
- Dashboard Design
- Business Question Framing
- Insight Generation
- Product Recommendations

---

## 👩‍💻 Author

**Divya Basantray**

Data Analytics | SQL | Python | Power BI

[LinkedIn](#) • [GitHub](#)

---

## ⭐ If you found this project useful

Feel free to explore the notebooks, SQL analysis and Power BI dashboard to understand the complete analysis process.
