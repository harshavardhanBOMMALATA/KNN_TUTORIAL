# KNN_MODEL_FOR_MEDICAL_DIAGNOSIS
---

In this project, we explore K-Nearest Neighbors (KNN) from scratch to advanced concepts. It’s not aimed specifically at beginners or experts, but at learners who want to understand KNN thoroughly and refresh their knowledge. We will build KNN completely from scratch, progressing from an introduction to a real-world project. This tutorial covers how KNN works with real-world datasets, the mathematical intuition behind it, and how majority voting and averaging are used for predictions. We will implement KNN for both classification and regression tasks, and discuss its advantages and disadvantages. By the end, you’ll have a strong practical and theoretical grasp of KNN.

---

### 🛠️ Tools & Technologies Used

* **📘 Jupyter Notebook** – for writing and executing the code step-by-step with explanations
* **🐍 Python** – core programming language used for building the logic
* **📂 CSV Files** – dataset used for training and predictions
* **📊 pandas** – for reading and handling the dataset
* **📈 matplotlib** – for visualizing the data and regression line
* **📐 numpy** – for performing numerical and statistical operations 

---

## 📘 Project Overview

**Project Title**: KNN Algorithm
**Level**: Beginner to Advance  
**Tool**: Jupyter Notebook  
**Libraries Used**: `pandas`, `numpy`, `matplotlib`

---

## 📁 File Structure 

1. **Introduction to KNN**
2. **Working and Why It Works**
3. **Mathematical Intuition**
4. **Implementation Without Scikit-Learn**
5. **Implementation With Scikit-Learn**
6. **Applications**
7. **Advantages and Disadvantages**

---

## 📘 Introduction to KNN

## What is KNN?

KNN stands for **K-Nearest Neighbors**. It is one of the algorithms under **supervised machine learning**.  

👉 If you want more clarity about machine learning and supervised learning, check my [Linear Regression repository](https://github.com/harshavardhanBOMMALATA/Linear-Regression.git).  

KNN can be used for both **regression** and **classification**, but it is mostly applied in **classification problems**.  

The algorithm works based on the concept of **neighbors**.  

**Example:**
- A person with **black hair, light brown skin tone, and thick eyebrows** might be classified as **Indian**.  
- A person with a **dark black skin tone** might be classified as **African**.  

This is how KNN makes predictions — by looking at the closest neighbors and deciding based on similarity.  

---

## How KNN Works and Why It Works

KNN works on the basis of **neighbors**.  

1. It takes all the data points.  
2. For a given input data point, it calculates how close it is to the other points using a **distance formula** (like Euclidean distance).  
3. It then selects the **k nearest points**.  
4. For **classification**, it performs a **majority vote** among those neighbors and assigns the class based on the highest votes.  
5. For **regression**, instead of voting, it takes the **average** of the neighbors’ values.  

👉 **Why does it work?**  
Because the algorithm makes predictions by checking the closest neighbors. Data points that are close to each other usually share similar characteristics, so this method is both simple and effective.  

---

## KNN Example (Step by Step)

We will now understand KNN with a simple dataset.  

### Dataset

| Person | Height (cm) | Weight (kg) | Category |
|--------|-------------|-------------|----------|
| A      | 170         | 65          | Fit      |
| B      | 160         | 60          | Fit      |
| C      | 180         | 80          | Fit      |
| D      | 155         | 72          | Unfit    |
| E      | 165         | 85          | Unfit    |

New data point:  Height = 167 cm
                 Weight = 70 kg

Our task: **Predict whether this person is Fit or Unfit using KNN.**

---

### Step 1: Distance Formula

We use **Euclidean distance**:  

\[
d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}
\]

Where:  
- \(x\) = Height  
- \(y\) = Weight  

---

### Step 2: Calculate Distances

- Distance(New, A) = √((167−170)² + (70−65)²) = √(9 + 25) = √34 ≈ **5.83**  
- Distance(New, B) = √((167−160)² + (70−60)²) = √(49 + 100) = √149 ≈ **12.21**  
- Distance(New, C) = √((167−180)² + (70−80)²) = √(169 + 100) = √269 ≈ **16.40**  
- Distance(New, D) = √((167−155)² + (70−72)²) = √(144 + 4) = √148 ≈ **12.16**  
- Distance(New, E) = √((167−165)² + (70−85)²) = √(4 + 225) = √229 ≈ **15.13**  

---

### Step 3: Select Nearest Neighbors

Let’s take **k = 3** nearest neighbors:  
- A → Fit (5.83)  
- D → Unfit (12.16)  
- B → Fit (12.21)  

---

### Step 4: Voting

- Fit = 2 votes  
- Unfit = 1 vote  

👉 Majority = **Fit**

---

### Final Result

The new person with **Height = 167 cm** and **Weight = 70 kg** is predicted as:  

✅ **Fit**


