### **Blinkit Sales Analysis: A Data-Driven Journey**

This project was an opportunity for me to analyze Blinkit’s sales data and uncover valuable insights. Using **Power BI**, I transformed raw data into an interactive dashboard that showcases trends, correlations, and actionable insights. The dataset included details about sales, product categories, outlet sizes, customer preferences, and locations. My goal was to create a dashboard that not only visualized performance metrics but also provided a deeper understanding of Blinkit’s operations.

---

### **The Challenge**

The dataset posed interesting questions to explore:

1. **What are the total sales, and what factors influence them the most?**
2. **How do sales and customer preferences vary across product types and locations?**
3. **What role do outlet size and type play in overall performance?**

To answer these questions, I needed to clean, model, and analyze the data effectively, ensuring the dashboard was both intuitive and insightful.

---

### **The Process: From Data Chaos to Clarity**

This project involved the following key steps:

1. **Data Cleaning and Quality Checks**
    
    I addressed missing values, duplicates, and inconsistencies in the data. This ensured that the metrics and visualizations were accurate and reliable.
    
2. **Data Modeling**
    
    Using Power BI’s **Data Model**, I created relationships between the tables, linking sales data with product and outlet information to enable seamless analysis.
    
3. **DAX Calculations**
    
    I used **Data Analysis Expressions (DAX)** to create dynamic measures and calculations that powered the dashboard’s insights.
    
4. **Dashboard Development**
    
    Finally, I designed a visually appealing and interactive dashboard with filters, slicers, and charts to make data exploration easy and effective.
    

---

### **Key DAX Formulas Used in the Dashboard**

Here are the key measures I created for the dashboard, along with their purpose and how they were used:

### **1. Total Sales**

**Formula:**

```DAX
Total Sales = SUM('BlinkIT Grocery Data'[Sales])
```

**Purpose:**

Calculates the total revenue by summing the `Sales` column in the dataset.

**Usage in Dashboard:**

- Displayed as a **card visualization** to show overall sales.
- Incorporated into charts like **Sales by Fat Content** and **Sales by Item Type** to analyze total sales across different dimensions.

---

### **2. Average Sales**

**Formula:**

```DAX
Avg Sales = AVERAGE('BlinkIT Grocery Data'[Sales])
```

**Purpose:**

Calculates the average revenue per transaction by taking the average of the `Sales` column.

**Usage in Dashboard:**

- Displayed as a card and included in **Matrix Cards** to compare the average revenue across various outlet types and product categories.

---

### **3. Number of Items**

**Formula:**

```DAX
No of Items = COUNTROWS('BlinkIT Grocery Data')
```

**Purpose:**

Counts the total number of transactions or rows in the dataset.

**Usage in Dashboard:**

- Used in a **bar chart** to analyze sales volume by product type, outlet size, and location.
- Helpful in determining the overall activity and frequency of transactions.

---

### **4. Average Customer Rating**

**Formula:**

```DAX
Avg Rating = AVERAGE('BlinkIT Grocery Data'[Rating])
```

**Purpose:**

Calculates the average customer rating for products, indicating overall customer satisfaction.

**Usage in Dashboard:**

- Included in the **Matrix Card** to compare average ratings across outlet types and product categories.
- Used as a key indicator of customer feedback.

---

### **Visualizing the Story**

Here’s how the dashboard answered key questions through its visualizations:

### **1. Total Sales by Fat Content (Donut Chart)**

**Objective:** Understand how fat content affects total sales.

**Insight:** High-fat products contributed the most revenue, but low-fat items showed notable demand in urban areas.

---

### **2. Total Sales by Item Type (Bar Chart)**

**Objective:** Evaluate the performance of different product categories.

**Insight:** Certain categories like snacks and beverages outperformed others, offering clear guidance for inventory planning.

---

### **3. Fat Content by Outlet for Total Sales (Stacked Column Chart)**

**Objective:** Compare how fat content drives sales across outlets.

**Insight:** Urban outlets sold more low-fat products, while rural outlets leaned toward high-fat items, reflecting regional differences in preferences.

---

### **4. Total Sales by Outlet Establishment Type (Line Chart)**

**Objective:** Analyze how outlet age or type impacts sales performance.

**Insight:** Newer outlets showed rapid growth, while established outlets demonstrated consistent revenue trends.

---

### **5. Sales by Outlet Size (Donut Chart)**

**Objective:** Assess the relationship between outlet size and performance.

**Insight:** Larger outlets generated significantly higher sales, showcasing the importance of offering a broader product range.

---

### **6. Sales by Outlet Location (Funnel Map)**

**Objective:** Visualize the geographic distribution of sales.

**Insight:** Urban areas contributed the highest revenue, emphasizing the importance of Tier 1 regions.

---

### **7. All Metrics by Outlet Type (Matrix Card)**

**Objective:** Provide a consolidated view of KPIs (Total Sales, Average Sales, Number of Items Sold, and Average Ratings) by outlet type.

**Insight:** Premium supermarkets achieved the highest ratings and sales, highlighting their value in catering to high-spending customers.

---

### **Filter Panel: Purpose and Explanation**

The **Filter Panel** allowed for dynamic exploration of the dashboard by enabling users to focus on specific dimensions:

### **1. Outlet Location Type Filter**

- **Purpose:** Analyze sales by Tier 1 (urban), Tier 2 (suburban), and Tier 3 (rural) outlets.
- **How It Works:** Selecting a tier dynamically updates the visuals to reflect metrics for that location type.


### **2. Outlet Size Filter**

- **Purpose:** Segment performance by outlet size (High, Medium, Small).
- **How It Works:** Changing the filter reveals how metrics like sales and ratings vary by store size.


### **3. Outlet Type Filter**

- **Purpose:** Explore metrics for Grocery Stores and different Supermarket Types.
- **How It Works:** Filtering by outlet type updates the dashboard to focus on performance trends for the selected format.


---

### **Insights and Recommendations**

From the analysis, I uncovered actionable insights:

1. **Expand Low-Fat Options in Urban Areas:** Low-fat products are gaining traction, especially in Tier 1 regions.
2. **Focus on Large Outlets for Growth:** Large outlets consistently generate the highest sales, making them a priority for expansion.
3. **Tailor Inventory for Regional Preferences:** Rural and suburban customers prefer high-fat products, while urban customers favor low-fat options.
4. **Support New Outlets:** Newly established outlets grow rapidly and require operational support to sustain growth.

---

### **Conclusion: My Key Takeaways**

This project was a comprehensive learning experience, allowing me to apply my skills in **data cleaning**, **DAX calculations**, and **dashboard design**. By leveraging Power BI, I transformed Blinkit’s data into an interactive tool that provides actionable insights.

This project taught me the importance of creating user-friendly dashboards and using data storytelling to deliver impactful insights.

---

## PPT Link

[Blinkit.pptx](https://prod-files-secure.s3.us-west-2.amazonaws.com/d726f00f-ae88-4ffd-b00b-913fb8e98b6f/bf4abd0b-e043-48da-81d3-fe1c2be34498/Blinkit.pptx)
