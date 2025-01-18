# **Pizza Sales Report Dashboard**

---

Pizza is not just a meal—it’s a cultural phenomenon. Businesses must understand the nuances of customer behavior, product preferences, and revenue patterns to thrive in a competitive market. This dashboard takes a deep dive into pizza sales, uncovering actionable insights from detailed sales data. Using two interconnected dashboards, the analysis reveals valuable trends in pizza sales, highlighting what sells, when it sells, and where it sells the most.

## **PIZZA SALES SQL QUERIES**

**A. KPI’s**

**1. Total Revenue:**

```sql
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;
```

**2. Average Order Value:**

```sql
SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales;
```

**3. Total Pizzas Sold:**

```sql
SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales;
```

**4. Total Orders:**

```sql
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales;
```

**5. Average Pizzas Per Order:**

```sql
SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2)) AS Avg_Pizzas_per_order FROM pizza_sales;
```

**B. Hourly Trend for Total Pizzas Sold**

```sql
SELECT DATEPART(HOUR, order_time) as order_hours, SUM(quantity) as total_pizzas_sold
FROM pizza_sales
GROUP BY DATEPART(HOUR, order_time)
ORDER BY DATEPART(HOUR, order_time);
```

**C. Weekly Trend for Orders**

```sql
SELECT DATEPART(ISO_WEEK, order_date) AS WeekNumber, YEAR(order_date) AS Year, COUNT(DISTINCT order_id) AS Total_orders
FROM pizza_sales
GROUP BY DATEPART(ISO_WEEK, order_date), YEAR(order_date)
ORDER BY Year, WeekNumber;
```

**D. % of Sales by Pizza Category**

```sql
SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
FROM pizza_sales
GROUP BY pizza_category;
```

**E. % of Sales by Pizza Size**

```sql
SELECT pizza_size, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
FROM pizza_sales
GROUP BY pizza_size
ORDER BY pizza_size;
```

**F. Total Pizzas Sold by Pizza Category**

```sql
SELECT pizza_category, SUM(quantity) as Total_Quantity_Sold
FROM pizza_sales
WHERE MONTH(order_date) = 2
GROUP BY pizza_category
ORDER BY Total_Quantity_Sold DESC;
```

**G. Top 5 Pizzas by Revenue**

```sql
SELECT TOP 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue DESC;
```

**H. Bottom 5 Pizzas by Revenue**

```sql
SELECT TOP 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue ASC;
```

**I. Top 5 Pizzas by Quantity**

```sql
SELECT TOP 5 pizza_name, SUM(quantity) AS Total_Pizza_Sold
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Pizza_Sold DESC;
```

**J. Bottom 5 Pizzas by Quantity**

```sql
SELECT TOP 5 pizza_name, SUM(quantity) AS Total_Pizza_Sold
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Pizza_Sold ASC;
```

**K. Top 5 Pizzas by Total Orders**

```sql
SELECT TOP 5 pizza_name, COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Orders DESC;
```

**L. Bottom 5 Pizzas by Total Orders**

```sql
SELECT TOP 5 pizza_name, COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Orders ASC;
```

## **Dashboard 1: Sales Overview**

### **Total Revenue and KPIs**

This section presents key performance indicators (KPIs) at a glance:

- **Total Revenue:** $817.9K—The overall earnings from all pizzas sold.
- **Average Order Value:** $38.31—The average amount spent per order.
- **Total Pizzas Sold:** 49.6K—The total number of pizzas purchased by customers.
- **Total Orders:** 21.4K—The total number of individual orders placed.
- **Average Pizzas per Order:** 2.32—The average number of pizzas included in each order.

These KPIs offer a comprehensive snapshot of business performance.

### **Hourly Trend of Total Pizzas Sold**

A bar chart visualizes pizza sales by the hour. Sales peak between 12 PM and 1 PM during lunch hours and again from 4 PM to 7 PM in the evening. These trends reveal customer dining habits and help optimize staffing and delivery logistics.

### **Weekly Trends for Total Orders**

The line chart tracks weekly order volumes, highlighting a pronounced spike in the 48th week of the year. This aligns with holiday shopping and celebrations, making it a critical period for maximizing sales through promotions and inventory readiness.

### **Percentage of Sales by Pizza Category**

A donut chart breaks down revenue by pizza categories:

- **Classic:** 26.91%—The leading category in sales contribution.
- **Veggie:** 23.68%—Catering to health-conscious customers.
- **Supreme:** 25.46%—Popular among premium pizza enthusiasts.
- **Chicken:** 23.96%—A strong contender in revenue generation.

### **Percentage of Sales by Pizza Size**

A horizontal bar chart evaluates sales by pizza size:

- **Large:** 45.9%—The top-selling size, appealing to group diners.
- **Medium:** 30.5%—A favorite among small families and individuals.
- **Regular:** 21.8%—Catering to single customers and quick meals.
- **Extra Large and XXL:** Minor contributions highlight niche appeal.

### **Total Orders and Pizzas Sold by Pizza Category**

This stacked bar chart compares the total number of pizzas sold and orders placed across categories. The Classic category outperforms others, followed by Supreme, Veggie, and Chicken.

## **Dashboard 2: Best/Worst Sellers**

### **Top 5 Pizzas by Revenue**

The Thai Chicken Pizza leads with $43.43K in revenue, followed by the Barbecue Chicken Pizza and the California Chicken Pizza. These findings help identify the most profitable pizzas.

### **Bottom 5 Pizzas by Revenue**

Pizzas such as the Brie Carre Pizza and Green Garden Pizza generate the least revenue. These pizzas could benefit from enhanced marketing or recipe modifications to boost appeal.

### **Top 5 Pizzas by Total Pizzas Sold**

The Classic Deluxe Pizza tops the chart with 2.45K units sold, followed by the Barbecue Chicken and Hawaiian pizzas. These results highlight customer favorites based on quantity.

### **Bottom 5 Pizzas by Total Pizzas Sold**

Pizzas like the Soppressata Pizza and Brie Carre Pizza have the lowest sales volumes, suggesting limited customer interest or availability.

### **Interactive Filters**

The dashboards feature dynamic filters, allowing users to:

- Select specific pizza categories such as Classic, Supreme, Veggie, or Chicken.
- Adjust the date range to focus on seasonal or historical trends.

## **Interactive Dashboard Link**

Explore the full dashboard here:

[Pizza Sales Dashboard](https://public.tableau.com/views/PizzaSales_17354142507290/Home?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
