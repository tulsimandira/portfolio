---

### **Exploring the Zomato Dataset Step by Step**

My journey with the Zomato dataset began with curiosity: **What makes a restaurant successful?** With a dataset filled with restaurant names, locations, cuisines, costs, and ratings, I was excited to uncover patterns that explain customer preferences and restaurant performance. Using Python, I delved into this dataset to clean, analyze, and visualize its insights.

---

### **Diving Into the Dataset**

The first step was to understand the structure of the dataset. I loaded it using **Pandas** and explored its columns and rows. The dataset included key features such as:

- **Geographical Information**: `City`, `Locality`, and `Address`.
- **Operational Features**: Availability of `Online Delivery` and `Table Booking`.
- **Customer Metrics**: `Aggregate Rating`, `Votes`, and `Price Range`.

I examined the dataset’s structure (`.info()` and `.head()`) and quickly identified challenges:

1. **Missing Values**: Columns like `Cuisines` and `Locality` had null entries that needed attention.
2. **Inconsistent Data Types**: Some columns required type adjustments for analysis.
3. **Duplicates**: Potential duplicate entries needed to be removed to ensure clean results.

---

### **Cleaning the Data**

To ensure meaningful analysis, I took several steps to clean the data:

1. **Handling Missing Values**:
    - Columns with missing data, such as `Cuisines`, were reviewed, and appropriate imputations were applied to retain valuable information.
2. **Standardizing Formats**:
    - Text-based columns like `City` and `Cuisines` were cleaned for consistency, fixing capitalization and other inconsistencies.
3. **Removing Duplicates**:
    - Duplicate rows were identified and removed to avoid skewing the results.

These efforts prepared the dataset for further exploration, ensuring accuracy and reliability in the analysis.

---

### **Analyzing the Data**

With the data cleaned, I moved on to **Exploratory Data Analysis (EDA)**. This phase was all about finding hidden patterns and relationships:

### **1. Cities and Restaurant Distribution**

To understand the distribution of restaurants across cities, I visualized the data using a **pie chart**. The visualization revealed:

- **New Delhi** emerged as the city with the most restaurants, accounting for a significant **68.87%** of the total.
- Other cities like **Gurgaon** (14.07%) and **Noida** (13.59%) also had a substantial number of restaurants.
- Smaller cities such as **Ghaziabad** (3.16%) and **Faridabad** (0.31%) had relatively fewer restaurants.

This pie chart provided a clear perspective on how restaurant density is concentrated in metropolitan areas, with **New Delhi** dominating the scene.

### **2. Cuisine Preferences**

I used **bar charts** to analyze the distribution of cuisines across restaurants:

- **North Indian**, **Chinese**, and **Fast Food** were the most popular cuisines across all cities.
- Niche cuisines like **Mexican** and **Mediterranean** had smaller shares but often higher ratings, showcasing potential for growth in specific markets.

The bar charts visually highlighted the diversity and customer preferences for certain cuisines in the restaurant industry.

### **3. Cost and Ratings**

To investigate how restaurant pricing influenced ratings, I used **scatter plots**. The results showed:

- Higher-priced restaurants tended to have better ratings, reflecting premium experiences and quality.
- However, many budget-friendly restaurants stood out, achieving high ratings through excellent food and value for money.

This visualization emphasized the balance between affordability and quality in attracting customers.

### **4. Customer Engagement**

Analyzing `Votes` and `Aggregate Rating` through **correlation heatmaps**, I discovered:

- Restaurants with higher ratings (`4.5+`) attracted significantly more votes, demonstrating the role of customer satisfaction in driving engagement.

---

### **Relationships Between Features**

To deepen the analysis, I examined interactions between variables:

1. **Correlation Analysis**:
    - Using a **heatmap**, I visualized the relationships between numerical features, finding strong positive correlations between `Votes` and `Aggregate Rating`.
2. **Categorical Insights**:
    - I explored `Cuisines` and `City` together to identify which cuisines were most popular in different areas.

This analysis provided a comprehensive understanding of what drives restaurant success.

---

### **Key Insights**

By the end of my analysis, I had uncovered several valuable insights:

1. **Restaurant Hubs**:
    - Cities like **New Delhi** dominate in numbers, while other cities like **Ghaziabad** and **Faridabad** have far fewer restaurants.
2. **Cuisines**:
    - Popular cuisines like **Chinese** and **Italian** perform well, but niche cuisines often shine in specific markets.
3. **Pricing**:
    - While expensive restaurants receive higher ratings, many budget-friendly options also thrive with high customer satisfaction.
4. **Customer Loyalty**:
    - High ratings drive votes and engagement, emphasizing the importance of delivering quality experiences.

---

### **Explore More**

Want to see the full analysis and dive into the visuals and code that brought these insights to life? You can check out the complete project on my GitHub:

[Zomato Dataset Exploratory Data Analysis.ipynb](https://github.com/tulsimandira/portfolio/blob/main/zomato-eda/Zomato%20Dataset%20Exploratory%20Data%20Analysis.ipynb)
