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

### Purpose:
- Reduce number of features
- Avoid curse of dimensionality
- Improve visualization

### Technique:
- PCA (Principal Component Analysis)

---

## 20. Feature Subset Selection

- Remove redundant or irrelevant features

### Methods:
- Brute force
- Filter
- Wrapper
- Embedded

---

## 21. Feature Creation

- Create new meaningful attributes

### Methods:
- Feature extraction
- Feature construction
- Mapping to new space

---

## 22. Discretization

- Convert continuous values into categories
- Often uses entropy or class labels

---

## 23. Attribute Transformation

- Change attribute values using functions

### Examples:
- log(x)
- x²
- |x|

---

## 24. Normalization & Standardization

### Normalization
- Scale values to range [0,1]

### Standardization
- Mean = 0
- Standard deviation = 1

---

## 25. Key Takeaway

Correct data representation and preprocessing are **critical** in data mining.  
Wrong measurement or poor-quality data can lead to **incorrect results**, even with good algorithms.

---
