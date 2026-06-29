# Order Analysis with NumPy

## Project Overview

This project analyzes a commercial order dataset using **NumPy**.  
The goal is to build an initial quantitative analysis of order performance by evaluating economic, operational, and customer-related dimensions.

The notebook starts from a structured NumPy array and develops a complete analytical workflow: from variable extraction and performance metric calculation to the creation of a synthetic indicator called **Quality Score**.

The project was developed for educational purposes, with the aim of strengthening NumPy skills through a practical data analysis case.

---

## Analysis Objectives

The analysis focuses on five main objectives:

1. Explore the structure of the dataset using NumPy arrays.
2. Calculate revenue, cost, and margin for each order.
3. Evaluate order profitability through percentage margin.
4. Compare fast and slow deliveries in terms of customer satisfaction and economic performance.
5. Build a synthetic indicator to classify the overall quality of each order.

---

## Dataset

The dataset contains **30 orders** and **5 variables**.

| Column | Variable | Description |
|---:|---|---|
| 0 | `quantity` | Number of units purchased |
| 1 | `unit_price` | Selling price per unit |
| 2 | `unit_cost` | Cost per unit |
| 3 | `delivery_days` | Number of days required for delivery |
| 4 | `satisfaction` | Customer satisfaction rating |

The dataset was manually created inside the notebook as a NumPy array.

---

## Tools Used

- Python
- NumPy
- Jupyter Notebook

---

## Notebook Structure

The notebook is organized into the following sections:

1. Library import and dataset creation
2. Preliminary check of the array structure
3. Extraction of the main variables
4. Calculation of revenue, cost, and margin per order
5. Calculation of aggregate economic indicators
6. Percentage margin analysis
7. Identification of high-margin orders
8. Analysis of high-margin orders with fast delivery
9. Segmentation between fast and slow orders
10. Customer satisfaction comparison
11. Economic comparison between segments
12. Quality Score construction
13. Qualitative classification of orders
14. Final analytical report

---

## Calculated Metrics

The analysis calculates several metrics, including:

- Revenue per order
- Cost per order
- Margin per order
- Total revenue
- Total cost
- Total margin
- Average margin per order
- Average percentage margin
- Average customer satisfaction
- Number of fast orders
- Number of slow orders
- Quality Score per order
- Classification of orders into qualitative categories

---

## Quality Score

The **Quality Score** is a synthetic indicator created to evaluate the overall quality of each order by combining three dimensions:

- order profitability;
- customer satisfaction;
- delivery speed.

The formula used is:

```python
quality_score = percentage_margin + satisfaction * 10 - delivery_days * 2
```

The indicator assigns a positive weight to percentage margin and customer satisfaction, while penalizing orders with longer delivery times.

---

## Order Classification

Orders are classified into three categories based on the Quality Score:

| Class | Condition | Interpretation |
|---|---:|---|
| Excellent | `quality_score >= 80` | Order with very strong overall performance |
| Good | `quality_score >= 60` | Order with positive but improvable performance |
| Critical | `quality_score < 60` | Order with weak or problematic performance |

---

## Main Results

The final report highlights the following results:

| Indicator | Value |
|---|---:|
| Number of analyzed orders | 30 |
| Total revenue | 7,500 |
| Total cost | 4,911 |
| Total margin | 2,589 |
| Average percentage margin | 36.98% |
| Average customer satisfaction | 3.87 |
| Average Quality Score | 66.18 |
| Maximum Quality Score | 91.00 |
| Minimum Quality Score | 32.33 |

The qualitative distribution of orders is as follows:

| Class | Number of orders | Percentage |
|---|---:|---:|
| Excellent | 6 | 20% |
| Good | 12 | 40% |
| Critical | 12 | 40% |

---

## Best and Worst Order

The best order according to the Quality Score is:

```python
[3, 40, 22, 2, 5]
```

with a **Quality Score of 91.00**.

The worst order according to the Quality Score is:

```python
[1, 600, 430, 8, 2]
```

with a **Quality Score of 32.33**.

---

## Key Insights

The analysis shows that:

- the dataset presents a positive average profitability;
- faster deliveries tend to be associated with higher customer satisfaction;
- absolute margin alone is not enough to evaluate the overall quality of an order;
- the Quality Score combines profitability, satisfaction, and operational speed into a single indicator;
- a relevant share of orders falls into the `Critical` category, highlighting possible areas for improvement.

---

## Skills Demonstrated

This project demonstrates the use of NumPy to:

- create and manipulate multidimensional arrays;
- select rows and columns through slicing;
- apply vectorized operations;
- calculate aggregate metrics;
- use Boolean conditions;
- filter data based on logical criteria;
- classify observations using `np.where`;
- create a simple analytical report.

---

## Possible Future Improvements

The project could be further improved by introducing:

- data visualizations with Matplotlib or Seaborn;
- a correlation matrix between variables;
- outlier analysis on margins and delivery times;
- dataset import from a CSV file;
- export of the results to Excel;
- development of a Power BI dashboard;
- comparison between different scoring systems.

---

## Author

Project developed by **Andrea Tagliabue** as a practical data analysis exercise with Python and NumPy.

