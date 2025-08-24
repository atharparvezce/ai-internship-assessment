# Purchase Order Item Categorization

This project aims to build a scalable, multilingual solution for categorizing purchase order items based on their descriptions. The goal is to uncover actionable insights into spending patterns across product categories, supporting credit optimization and procurement analysis for **Aajil Accelerate**.

---

## Objectives

- Categorize purchase order items with multilingual, unstructured descriptions.
- Enable spend analysis across logical product categories.
- Support business decisions around credit, procurement, and risk.

---

## Step 0: Problem Understanding

Before implementation, I reviewed the business context and assessment guidelines. Key principles guiding the solution:

- Prioritize real-world applicability over theoretical perfection.
- Emphasize iterative reasoning and explainability.
- Handle multilingual and noisy text effectively.

---

## Step 1: Exploratory Data Analysis (EDA)

Initial data exploration focused on:

- Understanding data structure and distribution.
- Identifying missing values and language patterns.
- Validating assumptions about item types and descriptions.

This step informed preprocessing and modeling choices.

---

## Step 2: Rule-Based Categorization (Baseline)

A keyword-driven rule-based approach was used to:

- Quickly prototype and interpret category logic.
- Build intuition around item descriptions.

**Limitations:**

- Labor-intensive feature engineering.
- Poor handling of multilingual and ambiguous text.
- Limited scalability and generalization.

---

## Step 3: Embedding-Based Clustering

To improve scalability and semantic understanding, I adopted an unsupervised clustering approach using sentence embeddings.

### Embedding Models Tested

| Model Name                                 | Outcome                              |
|-------------------------------------------|--------------------------------------|
| `paraphrase-multilingual-MiniLM-L3-v2`    | Most logical and compact clusters |
| `paraphrase-multilingual-mpnet-base-v2`   | Decent but less interpretable        |
| `distiluse-base-multilingual-cased-v2`    | Lower semantic coherence             |

**Selected Model:** `MiniLM-L3-v2` for its balance of performance and interpretability.

### Clustering Algorithms

- **KMeans**: Tuned using Elbow Method and Silhouette Score.
- **DBSCAN**: Less effective due to high-dimensional sparsity.

KMeans produced more coherent and business-relevant clusters.

---

## Step 4: Cluster Labeling with LLM

To assign meaningful category names:

- Used a Large Language Model (LLM) to summarize top terms per cluster.
- Generated human-readable labels based on semantic patterns.

This hybrid approach combined automation with interpretability.

---

## Step 5: Spend Analysis & Visualization

Analyzed purchase amounts across categories using:

- Bar charts for absolute spend.
- Pie charts for relative proportions.
- Time-series plots for seasonal trends and anomalies.

These visualizations support strategic decisions in credit and procurement.

---

## Outcomes

- A scalable, multilingual categorization pipeline.
- Logical, interpretable product categories.
- Actionable insights into spending behavior.

---

## Repository Structure

### data/ 
Raw and cleaned data(1. purchase-order-items.xlsx, 2. purchase_orders_clean_cleaned.xlsx and 3. purchase_orders_clean_final.xlsx) 

### notebooks/ 
EDA and modeling notebooks(1. EDA-and-Cleaning.ipynb, 2. Rule-Based-Categorization.ipynb and 3_Unsupervised_ML_with_embeddings_+_clustering.ipynb)

### README.md  
Project overview

### .gitignore  
for ignoring some file to github

---

## Contact

For any questions feel free to reach out with me directly.

