
# Walmart Sales Dashboard – DAX Measures & Key Business Insights

## 🚀 DAX MEASURES

### **1. Total Sales**
```DAX
Total Sales = SUM(Walmart_sales[Weekly_Sales])
```

### **2. Average Weekly Sales**
```DAX
Avg Weekly Sales = AVERAGE(Walmart_sales[Weekly_Sales])
```

### **3. YoY Growth**
```DAX
YoY Growth =
VAR CurrentYear = YEAR( SELECTEDVALUE(Walmart_sales[Date]) )
VAR CurrentSales = [Total Sales]
VAR PreviousSales =
    CALCULATE(
        [Total Sales],
        FILTER(
            ALL(Walmart_sales),
            YEAR(Walmart_sales[Date]) = CurrentYear - 1
        )
    )
RETURN DIVIDE(CurrentSales - PreviousSales, PreviousSales)
```

### **4. Holiday Sales**
```DAX
Holiday Sales = CALCULATE([Total Sales], Walmart_sales[Holiday_Flag] = 1)
```

### **5. Non-Holiday Sales**
```DAX
Non-Holiday Sales = CALCULATE([Total Sales], Walmart_sales[Holiday_Flag] = 0)
```

---

# 📊 KEY BUSINESS INSIGHTS

### **1. Strong Overall Sales Performance**
- Total sales exceed **$2.45B**, showing strong consumer demand.
- Average weekly sales around **$1.05M** per store-week reflect consistent performance.

### **2. Holiday vs. Non-Holiday Sales**
- Holiday weeks drive significantly **higher sales spikes**, though they make up a small portion of total revenue.
- Holiday periods should be leveraged for **promotions, staffing, and optimized inventory**.

### **3. Seasonal Trends**
- **Q2 is the highest-performing quarter**, likely due to summer demand.
- **Q1 shows the lowest sales**, indicating a post-holiday drop in activity.

### **4. Strategic Takeaways**
- Holiday periods provide the highest return per week and should be aggressively leveraged.
- Strong overall stability enables reliable demand forecasting and resource planning.
- Wide variation across stores suggests meaningful opportunities to improve performance through localized strategy.

# ✅ Summary
This markdown file includes the essential **DAX measures** used in your Power BI dashboard along with concise but impactful **business insights** derived from your Walmart sales dataset.
