## 1.3 Project Plan

**1. Executive Summary** 

This project will address the challenge of understanding and predicting user engagement for the Tasty Bytes website. We will develop a machine learning model to predict the popularity of new recipes based on the data provided by the product manager. The successful implementation of this model is expected to increase site traffic by enabling the promotion of highly popular recipes, directly contributing to business growth and customer retention.

---

**2. Business Problem & Context**

Tasty Bytes operates on a subscription model, where customer retention and engagement are paramount. The product manager has observed that featuring popular recipes on the homepage can increase website traffic by up to 40%; however, they currently lack a method to predict which recipes will be popular before they are featured. This leads to the promotion of unpopular recipes, resulting in wasted marketing efforts, reduced site traffic, and a potential decrease in user satisfaction. This project aims to solve this predictability problem.

---

**3. Project Goals & Objectives**

**Business Goals:**
* Predict high traffic recipes at least 80% of the time.
* Better understand business opportunities with data-driven insights and recommendations.
* Improve user engagement and satisfaction by consistently featuring popular recipes.
* Reduce the risk associated with developing and marketing new recipes.

**Project Objectives:**
1. **Develop a classification model** that predicts whether a recipe will be "popular" with a recall score of **80% or greater** on the "high traffic" class as requested by the client, and using a held-out data set.
2.  **Perform an Exploratory Data Analysis (EDA)** to identify the key drivers (e.g., ingredients, nutritional values, cuisine type) of recipe popularity.
3.  **Deliver a final report** that provides actionable, data-driven recommendations for the product manager to help curate the recipe selection.

---

**4. Proposed Approach & Methodology**

The project will be executed in four distinct phases:
1.  **Data Cleaning and Preparation:** We will handle missing values, correct data types, and prepare the dataset for analysis.
2.  **Exploratory Data Analysis (EDA):** We will use statistical tests and visualizations to uncover initial patterns and relationships between recipe features and popularity.
3.  **Feature Engineering and Model Development:** We will create new features and build several classification models (e.g., Logistic Regression, Random Forest) to predict recipe popularity.
4.  **Model Evaluation and Interpretation:** We will select the best-performing model based on our success metrics and interpret its results to provide clear business recommendations.

---

**5. Success Metrics**

The client explicitly asks us too **"correctly predict high traffic recipes 80% of the time."** This is the definition of Recall because the phrasing focuses on the positive class (`high_traffic` recipes). Based on the client's request, the primary KPI they are asking for is Recall, but a successful project will require balancing it with Precision.

* **KPI:** The final prediction model must achieve a recall score of **80% or greater** on the "high traffic" class as requested by the client, using a held-out data set.

---

**6. Scope & Deliverables**

**In Scope:**
* Analysis of the provided static dataset.
* Development and evaluation of a predictive model.
* A final report summarizing findings and recommendations.

**Out of Scope:**
* Deployment of the model into a live production environment.
* Building a real-time recipe recommendation engine.
* A/B testing the model's recommendations on the live website.

**Final Deliverables:**
1.  A complete Jupyter Notebook containing all code for the analysis.
2.  A trained model.
3.  A presentation slide deck summarizing the project for non-technical stakeholders.


## Summary and Recommendations  

---
**Summary of Findings**

Our analysis began with a significant data validation challenge: the provided nutritional data was corrupted and did not align with its description. Despite this, we discovered that the features contained valuable, non-linear predictive signals.

Through extensive feature engineering, we developed several advanced feature sets, including those with interaction features (which model how a nutrient's effect changes per category) and those with features derived from PCA and Autoencoders (which create compressed, non-linear representations of the nutritional data).

The key finding is that models using these sophisticated, context-aware features consistently and dramatically outperform baseline models. By optimizing for the business goal of correctly identifying at least 80% of high-traffic recipes (Recall), we have successfully developed several models that exceed this target.

---
**Top 5 Model Rankings**

The following models are ranked based on their ability to meet the primary business goal (Recall ≥ 80%) while maintaining the highest possible precision to minimize showing unpopular recipes.

1. 	Logistic Regression on PCA Interaction
- Recall: 97%
- Precicion: 68%	
- This model is the clear winner. It identifies an outstanding 97% of all popular recipes, far exceeding the business target. The PCA interaction features successfully create category-specific nutritional profiles, which a linear model can then use to great effect. While its precision is moderate, its exceptional recall makes it the best choice for maximizing traffic.
     
2. 	Random Forest on PCA Interaction
- Recall: 95%
- Precicion: 71%	
- This model also achieves extremely high recall with slightly better precision than the top model. It confirms the power of the PCA interaction features and provides a robust, non-linear alternative that performs nearly as well.
  
3.	Logistic Regression on Alternative Interaction
- Recall: 92%
- Precicion: 74%	
- This model offers the best balance between recall and precision. It comfortably surpasses the 80% recall target while being correct 76% of the time it predicts a recipe will be popular. The interaction features are highly effective and more directly interpretable than PCA.
  
4. 	Logistic Regression on Autoencoder Interaction
- Recall: 93%
- Precicion: 76%	
- This model's performance is almost identical to the model ranked #3, proving the effectiveness of non-linear feature engineering. The autoencoder is a more "black-box" approach, making this model slightly less preferable than the more interpretable interaction model above it.

5. 	Random Forest on Autoencoder Interaction
- Recall: 92%
- Precicion: 76%	
- This model again demonstrates the power of the autoencoder interaction features. It provides another strong option that easily meets the business goal, confirming that this feature engineering strategy is highly effective across different model types.

---
Business Recommendations
Based on this analysis, we can confidently move forward with a data-driven strategy to increase site traffic.

**Deploy the Top Model:**

We recommend immediately deploying the #1 ranked model: Logistic Regression with PCA Interaction Features. This model will allow the product team to identify 97% of all high-traffic recipes, giving them a powerful tool to select engaging homepage content and significantly increase the chances of achieving the 40% traffic boost.

**Establish a Key Performance Indicator (KPI):**

The business should adopt High-Traffic Recipe Recall as the primary KPI for this initiative. The goal was to achieve 80%, and our recommended model has established an initial performance benchmark of 97%. This metric should be monitored weekly to ensure the model's performance remains high and to measure its impact on site-wide subscriptions.

**Improve Future Data Collection:**

Our analysis proved that the initial dataset was heavily corrupted. To improve future modeling efforts, we recommend implementing stricter data validation rules at the point of data entry. Ensuring that nutritional information is physically plausible will lead to even more powerful and interpretable models in the future and will be a valuable asset for other data-driven initiatives at Tasty Bytes.
