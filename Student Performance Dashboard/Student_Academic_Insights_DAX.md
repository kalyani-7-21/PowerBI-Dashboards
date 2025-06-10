
# Student Academic Journey – DAX Queries & Key Insights

This markdown contains useful DAX queries and corresponding visualization insights for analyzing the `Cleaned_Student_Academic_Journey` dataset in Power BI.

---

## Dataset Fields
| Column Name | Description |
|-------------|-------------|
| Age Group | Age bracket of students |
| Gender | Male / Female |
| Pre-Qual Exam | Pre-degree exam (JEE, NEET, etc.) |
| Pre-Qual Score | Numeric score or rank |
| Degree | Current academic degree |
| CGPA Range | CGPA bracket (< 7.00, 7.00 - 8.99, > 9.00) |
| Changed Career Path | Whether career path was changed |
| Reason of Changes | Explanation for change (if any) |
| Entrepreneurship Interest | Interested in starting business |
| Future Shifts | Planning future changes in study/career |
| External Factors | Influences from family, peers, etc. |

---

## DAX Queries

### Total Students
```DAX
Total Students = COUNTROWS('Cleaned_Student_Academic_Journey')
```

### CGPA Numeric Score (Column)
```DAX
CGPA Numeric = 
SWITCH(
    TRUE(),
    'Cleaned_Student_Academic_Journey'[CGPA Range] = "< 7.00", 6,
    'Cleaned_Student_Academic_Journey'[CGPA Range] = "7.00 - 8.99", 8,
    'Cleaned_Student_Academic_Journey'[CGPA Range] = "> 9.00", 9.5,
    BLANK()
)
```

### Career Change Count
```DAX
Career Changed = 
CALCULATE(
    [Total Students],
    'Cleaned_Student_Academic_Journey'[Changed Career Path] = "Yes"
)
```

### Entrepreneurial Interest Count
```DAX
Entrepreneurial Interest = 
CALCULATE(
    [Total Students],
    'Cleaned_Student_Academic_Journey'[Entrepreneurship Interest] = "Yes"
)
```

### External Influences
```DAX
External Influence = 
CALCULATE(
    [Total Students],
    'Cleaned_Student_Academic_Journey'[External Factors] = "Yes"
)
```

### Male and Female Count
```DAX
Male Students = CALCULATE([Total Students], 'Cleaned_Student_Academic_Journey'[Gender] = "Male")
Female Students = CALCULATE([Total Students], 'Cleaned_Student_Academic_Journey'[Gender] = "Female")
```

---

## Visualizations Overview

### 1. Academic Path Insights
- **Stacked Column Chart:** Degree by Gender
- **Bar Chart:** Degree vs Student Count

### 2. CGPA vs Pre-Qualification Score
- **Scatter Plot:** Pre-Qual Score vs CGPA Numeric
- **Box Plot:** CGPA Range by Pre-Qual Score

### 3. Career Path Changes
- **Pie Chart:** Changed vs Not Changed

### 4. Entrepreneurial Intent
- **Donut/Bar Chart:** Interest in Entrepreneurship by Gender.

### 5. External Influences
- **Bar Chart:** Students Affected by External Factors
- **Text/Word Cloud:** Descriptions of Influence

### 6. Demographics Overview
- **Stacked Column:** Age Group by Gender
- **Pie Chart:** Gender Breakdown.