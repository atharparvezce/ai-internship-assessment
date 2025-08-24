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
## How to Run the Code

This project is built using Jupyter notebooks and is designed to run directly in **Google Colab**.

### Why Google Colab?
Due to performance limitations on my local machine, I transitioned to Google Colab for faster execution and smoother handling of embedding and clustering tasks.

### Steps to Execute

1. **Open Google Colab**  
2. **Upload Notebooks**  
3. **Upload Data Files**  
4. **Run Cells Sequentially**
5. **View Outputs**  
   Visualizations and clustering results will appear inline within the notebooks.

---

## Repository Structure

### data/ 
It content below three data file original data , clean data and final data with categories.
1. original-purchase-order-items.xlsx
2. cleaned-data-after-eda.xlsx
3. final-data-with-categories.xlsx 

### notebooks/ 
It contains three notebook files EDA , Rules based and Clustering
1. eda-and-cleaning.ipynb
2. rule-based-categorization.ipynb
3. clustering using embeddings.ipynb

### README.md  
Project overview

### .gitignore  
For ignoring some file to github

---

## Tools & Resources Used

This project combined technical rigor with practical research and collaborative assistance. Key tools and resources included:

- **Google Search**  
  Used extensively to research construction-related terminology and industry-specific product categories, ensuring accurate and business-relevant labeling.

- **ChatGPT (GPT-5)**  
  Assisted in:
  - Debugging Python and clustering logic during development.
  - Refining documentation and verifying spelling and grammar.
  - Summarizing cluster semantics for category naming.

---



## Contact

For any questions feel free to reach out with me directly.

