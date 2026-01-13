## Clustering (Unsupervised Learning)

**Clustering** is an **unsupervised learning technique** that groups data objects into **clusters** such that:
- Objects in the **same cluster are similar**
- Objects in **different clusters are dissimilar**

⚠️ In clustering:
- There are **no class labels**
- The algorithm finds patterns **on its own**

---

## Why Clustering is Used

- Discover hidden patterns in data
- Group similar data points
- Data exploration and summarization
- Useful when labels are **not available**

---

## Simple Example

Consider students with attributes **(Age, Marks)**:

- Students with similar marks and ages → same cluster
- Different patterns → different clusters

---

## How Clustering Works (Basic Idea)

1. Measure **similarity or distance** between data points  
   (e.g., Euclidean distance)
2. Group closer points together
3. Form clusters based on similarity

---

## Common Clustering Algorithms

- **K-Means**  
  Groups data into *K* clusters using distance

- **Hierarchical Clustering**  
  Creates a tree-like structure of clusters

- **DBSCAN**  
  Groups dense regions and detects outliers

---

## Applications of Clustering

- Customer segmentation
- Market analysis
- Image segmentation
- Document grouping
- Anomaly detection

---

## Key Differences (Clustering vs Classification)

| Feature | Clustering | Classification |
|------|-----------|----------------|
| Learning Type | Unsupervised | Supervised |
| Labels | ❌ No | ✅ Yes |
| Output | Groups | Classes |
| Goal | Find structure | Predict label |

---

## One-Line Exam Answer

**Clustering is an unsupervised learning technique that groups similar data points without using labeled data.**

---
## Regression (Supervised Learning)

**Regression** is a **supervised learning technique** used to **predict a continuous numeric value** based on input features.

In regression:
- **Labeled data is required**
- Output is a **number**, not a category

---

## Why Regression is Used

- Predict future values
- Understand relationship between variables
- Estimate trends and patterns

---

## Simple Example

Predicting **house price** based on:
- Area
- Number of rooms
- Location

👉 Output: a **number** (e.g., 5,000,000 PKR)

---

## How Regression Works (Basic Idea)

1. Use labeled data (input + output)
2. Learn relationship between variables
3. Fit a line or curve to minimize error
4. Predict continuous values for new data

---

## Common Regression Algorithms

- **Linear Regression**
- **Multiple Linear Regression**
- **Polynomial Regression**
- **Ridge & Lasso Regression**

---

## Applications of Regression

- Price prediction
- Sales forecasting
- Temperature prediction
- Risk analysis

---

## Regression vs Classification

| Feature | Regression | Classification |
|------|-----------|---------------|
| Learning Type | Supervised | Supervised |
| Output | Continuous value | Class/Category |
| Example | Price = 500,000 | Pass / Fail |

---

## One-Line Exam Answer

**Regression is a supervised learning technique used to predict continuous numerical values.**

---

# Data, Attributes, and Data Preprocessing (Data Mining)

This document explains the basic concepts of **Data**, **Attributes**, **Measurement**, **Data Types**, **Data Quality**, and **Data Preprocessing** as used in **Data Mining**.

---

## 1. What is Data?

**Data** is a collection of **objects** and their **attributes**.

- **Object**: An entity or instance  
  (also called record, case, sample, point, or entity)
- **Attribute**: A property or characteristic of an object  
  (also called variable, field, feature)

### Example:
| Object (Person) | Attributes |
|----------------|-----------|
| Ali | Age, Height, Eye Color |

---

## 2. Attribute Values

- Attribute values are **numbers or symbols** assigned to attributes.
- The **same attribute** can have different values depending on how it is measured.

### Example:
- Height → meters or feet
- Age → integer values

⚠️ Different attributes can use the **same values** but mean **different things**  
(e.g., ID and Age both use numbers, but ID has no order meaning).

---

## 3. Measurement of Length (Important Concept)

> The way you measure an attribute may **not match its real properties**.

### Explanation:
If we convert real measurements (like length) into **ranks**, we lose real distance information.

### Example:
| Object | Real Length | Assigned Rank |
|------|------------|---------------|
| A | 5 | 1 |
| B | 7 | 2 |
| C | 8 | 3 |
| D | 10 | 4 |
| E | 15 | 5 |

- Rank preserves **order**
- Rank does **not preserve actual differences**

➡️ This can cause **wrong conclusions** in data analysis.

---

## 4. Types of Attributes

### 4.1 Nominal
- Categories only
- No order

**Examples**:
- ID number
- Eye color
- Zip code

---

### 4.2 Ordinal
- Categories with order
- Differences are not meaningful

**Examples**:
- Grades (A, B, C)
- Rankings
- Height (short, medium, tall)

---

### 4.3 Interval
- Ordered
- Difference is meaningful
- No true zero

**Examples**:
- Temperature in Celsius or Fahrenheit
- Calendar dates

---

### 4.4 Ratio
- Ordered
- Difference & ratio are meaningful
- True zero exists

**Examples**:
- Length
- Weight
- Time
- Temperature in Kelvin

---

## 5. Properties of Attribute Values

| Property | Meaning |
|--------|--------|
| Distinctness | Values are different |
| Order | Values can be compared |
| Addition | Differences make sense |
| Multiplication | Ratios make sense |

### Attribute Types vs Properties

| Attribute Type | Properties |
|--------------|------------|
| Nominal | Distinctness |
| Ordinal | Distinctness + Order |
| Interval | Distinctness + Order + Addition |
| Ratio | All four |

---

## 6. Discrete vs Continuous Attributes

### Discrete Attributes
- Finite or countable values
- Usually integers

**Examples**:
- Zip codes
- Number of students
- Binary values (0,1)

---

### Continuous Attributes
- Real numbers
- Measured values

**Examples**:
- Height
- Weight
- Temperature

---

## 7. Types of Data Sets

- Record Data
- Data Matrix
- Document Data
- Transaction Data
- Graph Data
- Ordered / Sequential Data
- Spatial & Temporal Data
- Genomic Data

---

## 8. Record Data & Data Matrix

### Record Data
- Fixed set of attributes
- Each row is an object

### Data Matrix
- m × n matrix
- Rows → objects
- Columns → attributes

---

## 9. Document Data

- Each document is a **vector**
- Attributes are words (terms)
- Values are word frequencies

---

## 10. Transaction Data

- Each record is a set of items

**Example**:
- Grocery shopping cart
- Items = products
- Transaction = one shopping trip

---

## 11. Data Quality Issues

### Common Problems:
- Noise
- Outliers
- Missing values
- Duplicate data

---

## 12. Noise

- Random error in data

**Examples**:
- Poor phone audio
- Distorted sensor values

---

## 13. Outliers

- Data points very different from others
- May indicate errors or rare events

---

## 14. Missing Values

### Reasons:
- Data not collected
- Not applicable

### Handling Methods:
- Remove record
- Estimate value
- Ignore during analysis
- Replace with probable values

---

## 15. Duplicate Data

- Same data repeated
- Common when merging datasets

**Solution**: Data cleaning

---

## 16. Data Preprocessing Techniques

- Aggregation
- Sampling
- Dimensionality Reduction
- Feature Selection
- Feature Creation
- Discretization
- Attribute Transformation

---

## Aggregation

**Aggregation** is the process of **combining multiple data objects or attributes into a single object or attribute**.

It is mainly used to **reduce data size** and make data **simpler and more stable** for analysis.

---

### Why Aggregation is Used

- **Data Reduction**:  
  Reduces the number of records or attributes.

- **Change of Scale**:  
  Converts detailed data into higher-level summaries.

- **Stability**:  
  Aggregated data usually has **less noise and variability**.

---

### Examples

- Daily sales → Monthly sales  
- City-wise data → Country-wise data  
- Hourly temperature → Average daily temperature  

---

### Simple Example Table

| Original Data (Daily Sales) | Aggregated Data (Monthly Sales) |
|----------------------------|--------------------------------|
| Day 1 = 100 | Month = 3000 |
| Day 2 = 120 | |
| Day 3 = 90 | |

---

### Key Point

Aggregation helps in **summarizing data** so that it is easier to analyze, visualize, and process in data mining.

---

## 18. Sampling

**Sampling** is the process of selecting a **subset of data** from a large dataset.  
It is used when processing the **entire dataset is too large, expensive, or time-consuming**.

A good sample should **represent the original data** as closely as possible.

---

### 1. Random Sampling

- Every data object has an **equal chance** of being selected.
- Selection is done **randomly**.
- Simple and commonly used method.

**Example:**  
Selecting 100 students randomly from a list of 10,000 students.

---

### 2. Sampling with Replacement

- Once a data object is selected, it is **put back** into the dataset.
- The **same object can be selected multiple times**.
- Dataset size remains the same.

**Example:**  
Picking a ball from a bag, noting its color, and putting it back before the next pick.

---

### 3. Sampling without Replacement

- Once a data object is selected, it is **removed** from the dataset.
- The **same object cannot be selected again**.
- More common in practical applications.

**Example:**  
Picking lottery numbers where each number is used only once.

---

### 4. Stratified Sampling

- Dataset is divided into **groups (strata)** based on a specific attribute.
- Random samples are taken **from each group**.
- Ensures all important groups are represented.

**Example:**  
A class has 60% boys and 40% girls.  
Sampling maintains the same ratio in the selected data.

---

### Key Point

Sampling improves **efficiency** while maintaining **data quality**, provided the sample is **representative** of the original dataset.
---

## 19. Dimensionality Reduction

**Dimensionality Reduction** is the process of **reducing the number of attributes (features)** in a dataset while keeping the most important information.

### Why it is used
- Reduces **computation time**
- Saves **memory**
- Avoids the **curse of dimensionality**
- Makes data easier to **visualize**
- Reduces **noise**

### Common Technique
- **PCA (Principal Component Analysis)**  
  Finds new features that capture the **maximum variance** in the data.

---

## 20. Feature Subset Selection

**Feature Subset Selection** means selecting a **subset of original features** and removing:
- **Redundant features** (duplicate information)
- **Irrelevant features** (no useful information)

⚠️ Unlike dimensionality reduction, features are **not transformed**, only **selected or removed**.

### Example
- Keeping **GPA** but removing **Student ID** when predicting performance.

### Methods
- Filter methods
- Wrapper methods
- Embedded methods

---

## 21. Feature Creation

**Feature Creation** is the process of **creating new features** from existing data to improve model performance.

### Why it is used
- Captures important information more efficiently
- Improves accuracy

### Types
- **Feature Extraction**:  
  Creating new features from raw data  
  (e.g., pixels → edges in images)

- **Feature Construction**:  
  Combining existing features  
  (e.g., Total Price = Quantity × Unit Price)

---

## 22. Discretization

**Discretization** converts **continuous data** into **discrete categories or intervals**.

### Why it is used
- Simplifies data
- Makes data easier to understand
- Useful for classification algorithms

### Example
| Age | Category |
|----|---------|
| 0–18 | Child |
| 19–35 | Adult |
| 36+ | Senior |

---

## 23. Attribute Transformation

**Attribute Transformation** applies a **mathematical function** to change attribute values.

### Purpose
- Improve data distribution
- Reduce skewness
- Normalize values

### Common Transformations
- log(x)
- x²
- √x
- |x|

### Normalization & Standardization
- **Normalization**: scales values to range [0,1]
- **Standardization**: mean = 0, standard deviation = 1

---

## Quick Summary

| Technique | Purpose |
|--------|--------|
| Dimensionality Reduction | Reduce number of features |
| Feature Subset Selection | Remove unnecessary features |
| Feature Creation | Create new useful features |
| Discretization | Convert continuous → categorical |
| Attribute Transformation | Change scale or distribution |

---

## 24. Normalization & Standardization

## Normalization & Standardization

Both **Normalization** and **Standardization** are **data preprocessing techniques** used to scale numeric attributes so that features are comparable.

---

## Normalization

**Normalization** rescales data into a **fixed range**, usually **[0, 1]**.

### Why Normalization is used
- Features have different scales
- Prevents large values from dominating smaller ones
- Required for distance-based algorithms

### Formula (Min–Max Normalization)

---

## 25. Key Takeaway

Correct data representation and preprocessing are **critical** in data mining.  
Wrong measurement or poor-quality data can lead to **incorrect results**, even with good algorithms.

---
