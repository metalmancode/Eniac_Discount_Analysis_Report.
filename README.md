# Eniac_Discount_Analysis_Report.
Eniac Sales &amp; Discount Analysis Report


## 📌 Project Overview
This project analyzes product, order, and sales data to answer key business questions:
- How should products be classified into categories for simpler reporting and analysis?
- What is the distribution of product prices across categories?
- How many products are discounted, and how large are these discounts?
- How do seasonality and special dates (Black Friday, Christmas) affect sales?
- Should the company continue using discounts, and if so, how?

The analysis was performed in **Python (Pandas, Seaborn, Matplotlib)** with data cleaning, transformation, and visualization.

---

## 📂 Data Sources
- **products.csv** → Product catalog (sku, name, description, price, promo_price, type).
- **orders.csv** → Customer orders (order_id, created_date, total_paid, state).
- **orderlines.csv** → Order details (id_order, product_id, product_quantity, sku, unit_price, date).
- **brands.csv** → Brand lookup table.

---

## ⚙️ Data Preparation
1. Converted `price`, `promo_price`, and `unit_price` columns to numeric.  
2. Removed duplicate rows by `sku`.  
3. Filtered `orders` to **Completed** only.  
4. Merged orders and orderlines for sales analysis.  
5. Created **categories** from product descriptions using keyword search (mouse, adapter, RAM, monitor, refurbished, etc.).  

---

## 📊 Key Findings

### 1. Product Categorization
- Categories created from description fields are more useful than raw product types.
- Categories allow easier reporting and comparison (e.g., *adapters, RAM, refurbished, speakers*).

### 2. Price Distribution
- Strong variation across categories.
- Commodities like **RAM/adapters** have lower stable prices.
- **Monitors/servers** show high variability.

### 3. Discounts
- ~**899 products** have active discounts.  
- **Average discount**: ~34%.  
- **Category insights:**
  - *Refurbished, Monitors, Other* → highest discounts (often 50–100%).  
  - *RAM, adapters, straps* → smaller, stable discounts (10–30%).  

### 4. Seasonality & Special Dates
- **Black Friday & Christmas** = major sales spikes.  
- **Non-discounted products** dominate holiday sales (4–5× increase vs regular days).  
- **Discounted products** also sell more, but volumes remain much lower.

### 5. Combined Insights
- **Seasonality is the main driver**, not discounts.  
- Discounts are concentrated in categories that don’t drive much revenue.  
- Deep discounting is inconsistent and not always strategic.

---

## ✅ Recommendations
- **Targeted discounts** only for clearance, refurbished, or low-demand items.  
- **Reduce discounts** on high-demand categories (they sell without markdowns).  
- **Standardize discount strategy**:  
  - Accessories → 10–20%  
  - Refurbished → up to 50%  
  - Avoid 90–100% markdowns unless liquidating stock.  
- **Leverage seasonal campaigns** (ads, bundles, limited offers) instead of blanket discounts.  
- **Improve data collection**: track revenue by category and ROI of discounting.  

---

## 📈 Example Visualizations
- **Holiday vs Non-Holiday Sales (Discounted vs Non-Discounted)**  
  ![holiday-sales](figures/holiday_sales.png)

- **Discount % by Category**  
  ![discounts-by-category](figures/discounts_by_category.png)

---

## 💡 Final Answer
- **Should we continue discounts?**  
  - **No**: Discounts should not be the main lever for holiday sales (customers buy even at full price).  
  - **Yes (selectively)**: Discounts are still useful for clearance and low-demand categories.  
  - **Best strategy**: Seasonal marketing + targeted discounts = higher revenue with better margins.

---

## 🛠️ Tech Stack
- Python 3.x  
- Pandas, Numpy  
- Seaborn, Matplotlib  
- Jupyter Notebook  

---

## 🚀 How to Run
1. Clone the repository.  
2. Place the CSV files (`products.csv`, `orders.csv`, `orderlines.csv`, `brands.csv`) into the `data/` directory.  
3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook analysis.ipynb
