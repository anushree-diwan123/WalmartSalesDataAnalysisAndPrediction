# Retail Sales Analysis & Forecasting (Walmart Dataset)

**Author:** **Anushree Diwan**  
**Topic:** Walmart Sales Data Analysis — Insights, Statistical Analysis & Sales Forecasting  
**Portfolio Project for GitHub**

---

## Project Objective

This project performs **end-to-end retail sales analysis** and short-term forecasting using Walmart’s weekly store-department dataset. The analysis helps businesses:

- Understand **demand and seasonal patterns**
- Identify **key sales and revenue drivers**
- Forecast store demand for the **upcoming weeks and quarter**
- Recommend **optimized promotion & inventory distribution strategies**

---

## Dataset Used

Three key CSV files were merged and cleaned for analysis:

| File | Description |
|------|-------------|
| `stores.csv` | Store type and store size information |
| `features.csv` | Holidays, markdown discounts, and economic indicators |
| `train.csv` | Weekly sales by Store and Department |

**Note:** The dataset did not include direct fields such as **Units Sold, Unit Price, or Revenue**, so these were **derived during analysis**.

---

## Data Preparation & Feature Engineering

### Key Steps
- Converted `Date` into `datetime` format
- Filled all **Markdown discount missing values with 0**
- Removed **duplicates** for data consistency
- Encoded categorical fields (`Store Type`, `Size Bucket`)
- Generated new business-meaningful metrics:
  - **Revenue = Weekly Sales**
  - **Total Discount = Sum of all Markdown fields**
  - **Units Sold = Estimated using CPI price-proxy normalization**
  - **Month & Quarter = Extracted from Date for seasonal trends**
- Exported clean dataset for analysis as:  
  `CleanedData.csv`

---

## Exploratory Data Analysis (EDA)

The analysis included:

- **Revenue and Units movement trends**
- **Top-performing stores and seasonal demand peaks**
- **Discount and holiday impact on sales uplift**
- **Correlation heatmap analysis** between:
  - `Total Discount`
  - `Units Sold (Proxy)`
  - `Revenue`
  - `Holiday flag`

### Key Insight from EDA
> Sales behavior is **highly seasonal and promotion-responsive**, rather than being explained by economic indicators alone.

All EDA charts and visuals were exported into `dashboard_outputs/` to be reused in slides and documentation.

---

## Statistical Analysis & Hypothesis Testing

### Hypotheses Formulated

| Hypothesis | Test Used | Result |
|------------|-----------|--------|
| H₀: Discounts have no impact on sales | t-test / correlation | **Rejected** |
| H₀: Mean revenue is equal across regions/store segmentation | ANOVA | **Rejected** |

### Findings Summary
- Discounts **do impact revenue when applied during seasonal peaks**
- Revenue **differs significantly across store location segments**
- **Strong positive correlation** exists between Units Sold and Revenue
- Markdown discounts show **high revenue sensitivity when timed correctly**
- Economic indicators (**CPI, Fuel Price, Unemployment**) show only **mild correlation** and are weak drivers alone.

### Business-conclusion
> “Discount campaigns and inventory distribution should be planned based on seasonal peaks, holidays, and top store contribution rather than external economic trends.”

---

## Predictive Modeling — Regression / Forecasting

### 1️**Linear Regression**
- Predicting: **Revenue / Weekly Sales**
- Features used: Discount, Units proxy, CPI, Fuel, Unemployment
- Evaluation:
  - **RMSE: 22,723.04**
  - **R² Score: 0.01 (Very Low Explanatory Power)**
- **Conclusion:** Not reliable for forecasting unless feature set is redesigned

### 2️**ARIMA**
- Approach: **Time-only forecasting**
- Used for: **Next 4-week demand trend**
- **Result:** More reliable trend capture for short-term planning
- Business value: Supports inventory planning to avoid stock-outs

### Model Comparison

| Model | Accuracy | Use Case | Recommendation |
|-------|--------|----------|--------------|
| Linear Regression | Poor | Not suitable | Feature redesign needed |
| ARIMA / Exponential Smoothing | Better for trend | Short-term demand planning | Use forecast for inventory and markdown timing |

---

## Prescriptive Recommendations

### Suggested Business Actions
- Boost inventory **1–2 weeks before holiday demand spikes**
- Apply markdown discounts **seasonally and store-targeted**
- Allocate inventory based on:
  - **Top 10–20% store revenue share**
  - **Derived Units movement proxy**
  - **Seasonal trend momentum**
- Promotions should be **targeted**, not uniform across all stores

---

## Deliverables Included

✔ Cleaned dataset exported: `CLeanedData.csv`  
✔ Notebook with polished structure and reproducible code  
✔ EDA + correlation + forecasting **charts exported for slide reuse**  
✔ 4-week forecast and model performance documented  
✔ Discussions summarised into stakeholder-friendly insights  

---

## Skills & Tools Demonstrated

- **Pandas** → Data Cleaning & Transformation  
- **Matplotlib & Seaborn** → Visual Insights  
- **Statsmodels / Scipy** → t-test, ANOVA, Correlation  
- **Scikit-learn** → Linear Regression Modeling  
- **Time-Series Forecasting** → ARIMA / Exponential Smoothing  
- *(Bonus)* **Plotly Dashboards** → Interactive analysis  

---

## Final Takeaways

1. **Retail sales show strong seasonal trends**
2. **Holiday and markdown discounts drive high revenue uplift**
3. **Few top stores contribute most of the total revenue**
4. **Time-series models outperform regression for trend forecasting here**
5. **Promotion and inventory must be seasonal + store-specific**

---

## Reproducibility

To validate reproducibility:
1. Restart kernel
2. Run all cells → Notebook executes without errors
3. All visuals generate and save into correct folders

---

## Portfolio Note

This is a **business-focused data analyst project**, showcasing full analytical depth from raw data merging to forecasting, statistical proof, visual storytelling, and strategic recommendations.

---

### Thank you for viewing my project!

