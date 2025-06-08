### DAX MEASURES
1. Total Sales
```Total Sales = SUM(Sales[Sales_Amount])```

2. YTD Sales
```YTD Sales = TOTALYTD([Total Sales], 'DateTable'[Date])```

3. Conversion Rate
``` Conversion Rate = DIVIDE([Total Sales], SUM(Sales[Leads]), 0) ```

### KEY INSIGHTS FROM SALES DATA
1. Total Sales for 2023: INR 11.15M <br>
2. Conversion Rate: 352.15 <br>
3. YTD Sales = Total Sales (since data is only from one year) <br>
4. Previous Year Sales = INR 0 (no data for 2022) <br>
5. YoY Growth % = 0.00% (due to absence of previous year data) <br>
