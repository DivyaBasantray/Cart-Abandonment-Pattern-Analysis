## 1. Project Objective

The objective of this project was to understand why customers abandon their shopping carts before completing a purchase.

Using e-commerce event data from February 2020, I analyzed customer and session behavior to identify the main factors associated with cart abandonment. The analysis covered product categories, brands, price ranges, number of products in the cart, session depth, customer engagement, devices, and traffic sources.

The goal was to turn these findings into clear business insights that can help an e-commerce team understand where customers are dropping off and what areas should be investigated first.

---

## 2. Key Insights

The Power BI dashboard highlighted several important patterns behind cart abandonment:

- Certain product categories had significantly higher abandonment rates than others.
- Some brands showed very high abandonment rates, suggesting that customers often added products to their carts without completing the purchase.
- Lower-priced products showed higher abandonment compared with higher-priced products in the analyzed data.
- Customers who added only one product to their cart were more likely to abandon compared with customers who added multiple products.
- Session depth had a clear relationship with conversion. Customers with more sessions were generally more likely to complete a purchase.
- Customers who purchased showed stronger engagement with the website compared with customers who abandoned their carts.
- Some device types and traffic sources showed higher abandonment rates, highlighting areas that may need further investigation.
- The largest drop-off in the purchase journey occurred between adding a product to the cart and completing the purchase.

Overall, the analysis showed that cart abandonment is not caused by one single factor. Product, price, customer engagement, session behavior, device, and traffic source all play a role in the likelihood of completing a purchase.

---

## 3. Tech Stack

### Python
Used for data cleaning, data preparation, and exploratory data analysis. Python was also used to process the large dataset in chunks.

### Pandas
Used to clean, filter, transform, and analyze the e-commerce data.

### MySQL
Used for SQL analysis and answering business questions related to cart abandonment, customer behavior, and high-abandonment segments.

### Power BI
Used to build the final interactive dashboard and present the analysis through clear visualizations and business insights.

### Excel
Used for supporting data checks and basic analysis during the project.

### Jupyter Notebook
Used to perform the Python-based data cleaning and exploratory data analysis.

### GitHub
Used to store the project files, analysis, SQL queries, and documentation.

---

## 4. Dashboard Purpose and Features

### Business Problem

E-commerce businesses can have a large number of customers who add products to their carts but leave without completing the purchase.

The main business problem addressed in this project was:

**Why are customers abandoning their carts, and which customer or product factors are most strongly associated with abandonment?**

### Dashboard Goal

The goal of the Power BI dashboard was to turn the analysis into a simple business view that helps identify the main areas of customer drop-off.

The dashboard allows users to explore:

- Total cart sessions
- Purchased and abandoned sessions
- Cart abandonment rate
- Cart-to-purchase conversion rate
- Abandonment trends over time
- Abandonment by device
- Abandonment by traffic source
- Abandonment by product category and brand
- Abandonment by price range
- Impact of product count on abandonment
- Customer engagement differences between purchasers and abandoners
- Relationship between session depth and purchase behavior
- High-traffic segments with low conversion
- Major drop-off points in the purchase journey

The dashboard is designed to help an e-commerce or product team identify the biggest drop-off areas and decide what should be investigated or improved first.

---

## 5. Dataset

The project uses the **E-commerce Behavior Data from Multi-Category Store** dataset from Kaggle.

The original dataset contains e-commerce events such as:

- `view`
- `cart`
- `purchase`

along with information about products, categories, brands, prices, users, and sessions.

For this project, the analysis focused on the **February 2020 dataset**.

The February file contained approximately **55 million events**. Because of its large size, the data was processed in chunks using Python instead of loading the entire file into memory at once.

For the cart abandonment analysis, the focus was specifically on **cart events**, resulting in approximately **2.65 million cart records** after processing and cleaning.

The final cart-level dataset included information such as:

- Event time
- Product ID
- Category
- Brand
- Price
- User ID
- User session
- Purchase status
- Date
- Hour
- Day of week

The processed data was then used across **Python, SQL, and Power BI** to complete the analysis and build the final dashboard.
