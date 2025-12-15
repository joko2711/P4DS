# 📊 PROJECT PRESENTATION - E-COMMERCE INVOICE ANALYSIS

**Team** : KUBIK Aleksander, KOBANA Johan, JOUYIT Matthieu, Thomas BOULAINE (DIA4)  
**Dataset** : invoices.csv  
**Deliverable** : Interactive Dash Dashboard + Python

---

## 📌 SLIDE 1 : THE BUSINESS PROBLEM

### Objective
**How can we analyze online store activity to make data-driven decisions?**

### Context
- 📦 Thousands of customer invoices
- 🌍 Sales distributed geographically
- 📅 10-year history
- ❓ Questions: Which products? When? Where?

### Proposed Solution
An **interactive dashboard** extracting **4 key indicators** from the `invoices.csv` dataset.

---

## 🔧 SLIDE 2 : TECHNICAL STEPS (Architecture)

### Phase 1 : Data Preparation
```
invoices.csv → Cleaning → Date parsing → Year/month extraction
```

### Phase 2 : Extraction of 4 Indicators
1. **Grouping** : Top 10 products by revenue
2. **Transformation** : Pattern mining (association rules / frequent itemsets)
3. **Temporal** : Sales forecasting (Prophet forecasting)
4. **Spatial** : City clustering (geocoding + mapping)

### Phase 3 : Dash Integration
Dashboard with 4 interactive charts + team/objective metadata.

---

## 📊 SLIDE 3 : INDICATOR 1 - TOP PRODUCTS

### Technique Used
**Grouping (GroupBy) + Aggregation**

```python
Sum of amounts by product_id → Descending sort → Top 10
```

### Key Result
- Product 164: **€7,000** (champion)
- Products 42, 18, 75... : **€6,000-7,000** (stable)

### Business Decision
✅ **Stock management** : Ensure sufficient stock on these 10 products  
✅ **Marketing** : Tailored promotional campaigns

### Visualization
Bar chart: Products (X) vs Revenue (Y)

---

## 🔗 SLIDE 4 : INDICATOR 2 - PATTERN MINING

### Technique Used
**FP-Growth + Association Rules (Frequent Pattern Mining)**

```
Basket = (job, product) → Frequent itemsets → Association rules
```

### Concrete Example
```
IF customer buys Product A (mouse)
THEN they buy Product B (keyboard) with 30% confidence
Strength: 1.8× more likely than random
```

### Business Decision
✅ **Bundling** : "Mouse + keyboard pack = -15%"  
✅ **Cross-selling** : Recommend product B after A

### Visualization
Scatter plot: Confidence (X) vs Lift (Y), colored by product

---

## 📈 SLIDE 5 : INDICATOR 3 - TEMPORAL ANALYSIS + FORECAST

### Technique Used
**Prophet Forecasting (Facebook)**

```
Data 2014-2024 → Trend/seasonality detection → 2025 forecasts
```

### Key Result
- **Trend** : Stability ~€50,000/month
- **Forecast** : Next 12 months with 95% confidence interval
- **Uncertainty** : Green zone widening (increasing uncertainty)

### Business Decision
✅ **Annual budget** : Plan €600k for 2025  
✅ **Stock management** : Anticipate peaks (if seasonality detected)

### Visualization
3 curves: Actual sales (blue) + Trend (orange) + Forecast (green)

---

## 🗺️ SLIDE 6 : INDICATOR 4 - SPATIAL ANALYSIS

### Technique Used
**Geographic clustering + Geocoding (Nominatim)**

```
Cities → Geocoding (lat/lon) → Aggregation by city
```

### Key Result
```
Paris     : 🟡 700 invoices, €85,000  (VIP)
Lyon      : 🟠 250 invoices, €35,000  (Important)
Marseille : 🔵 120 invoices, €18,000  (Emerging)
```

### Business Decision
✅ **Logistics** : Create regional warehouses in Paris, Lyon  
✅ **Geo-targeted marketing** : Region-specific campaigns

### Visualization
Mapbox map: Real location + Circle size = invoices + Color = revenue

---

## 🎯 SLIDE 7 : ORGANIZATION & DOCUMENTATION

### Applied Principles

| Criterion | Implementation |
|-----------|---|
| **Modularity** | All code in independent, reusable `def()` functions |
| **Documentation** | Explicit Input/Output for each function |
| **Interpretation** | Markdown cells explaining method + results |
| **Entry point** | `if __name__ == "__main__":` orchestrating full pipeline |
| **Visualization** | Plotly + Dash for interactivity |

### Code Structure
```
1. load_data()           → Load CSV
2. basic_info()          → Data exploration
3. preprocess_dates()    → Temporal transformation
4. top_products()        → Indicator 1
5. pattern_mining_by_job() → Indicator 2
6. temporal_analysis()   → Indicator 3
7. spatial_analysis_by_city() → Indicator 4
8. main()               → Orchestration
9. Dash App            → Final presentation
```

---

## 💡 SLIDE 8 : BENEFITS & CONCLUSION

### Business Benefits

| Aspect | Gain |
|--------|------|
| **Performance** | Identify 10% of products generating 80% of revenue |
| **Customer** | Effective cross-selling (+10-15% avg basket) |
| **Forecasting** | Reduce planning error |
| **Geography** | Optimize logistics distribution |

### Possible Next Steps
1. 🔄 Automate dashboard (daily refresh)
2. 🎯 Add interactive filters (by date, by region)
3. 📧 Email alerts if anomalies detected
4. 🤖 Advanced ML (K-means customer clustering, anomaly detection)

### Conclusion
✅ **4 key indicators** in production  
✅ **Modular** and documented code  
✅ **Interactive dashboard** ready for decision-making  
✅ **Data-driven decisions** operational

---
