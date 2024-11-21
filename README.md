# User-Pruchase-record-
    USER PURCHASE RECORD DOCUMENTATION REPORT 


•	Customer Segmentation and Model Evaluation Report
1.	Dataset Overview :
The dataset contains customer purchase records with details like purchase amounts, returns, payment methods, and churn status. The main goal of this analysis is to:
  1.	Segment customers into meaningful clusters using unsupervised techniques.
  2.	Evaluate supervised models to predict customer behaviors like churn and returns.




•	Clustering Analysis
    	1. KMeans Clustering
				KMeans was applied to group customers into two clusters based on:
				•	Total Purchases
				•	Average Purchase Amount
				•	Total Returns
				•	Churn Status
				Cluster Summary :

					Cluster	Total Purchases (Avg)	 Average Purchase Amount	  Total Returns (Avg)	  Churn Status
					 0	     7876.70	              969.47	                   3.91	                 0.42
					 1       3118.15	              655.31	                   1.79	                 0.13

		Insights
		 •	Cluster 0: Represents high-value customers with higher average purchase amounts, but also higher returns and churn likelihood.
		 •	Cluster 1: Contains lower-value customers with reduced purchase amounts, fewer returns, and lower churn rates.
		     
2.DBSCAN Clustering

 The DBSCAN algorithm identified 9 clusters (including one noise cluster labelled as -1) based on customer purchasing patterns,           returns, and churn status. Each cluster represents a distinct segment of customers, with notable variations in spending, return          rates, and likelihood of churn.

Cluster-by-Cluster Analysis
		
		Cluster -1 (Noise Cluster)
			•	Total Purchases: Highest at 30,703.42, suggesting these customers are outliers with very high spending.
			•	Average Purchase Amount: 925.82, indicating high-value transactions.
			•	Total Returns: 15.78, higher than most clusters, reflecting frequent returns.
			•	Churn Status: 65%, indicating a high likelihood of churn, which aligns with these customers being classified as "noise" or anomalous.

			Cluster 0 (Moderate Spenders, Low Returns, No Churn)
						•	Total Purchases: 4,397.47, moderate spending compared to other clusters.
						•	Average Purchase Amount: 765.25, indicating mid-range purchases.
						•	Total Returns: 2.34, relatively low.
						•	Churn Status: 0%, showing strong loyalty and no churn risk.

			Cluster 1 (Moderate Spenders, High Churn)
					•	Total Purchases: 5,482.14, slightly higher than Cluster 0.
					•	Average Purchase Amount: 765.69, mid-range.
					•	Total Returns: 2.89, slightly higher than Cluster 0.
					•	Churn Status: 100%, indicating complete churn within this segment.


			Cluster 2 (High Value, Minimal Returns)
					•	Total Purchases: 2,306.88, this cluster reflects customers who make a single high-value purchase (matching the average purchase amount).
					•	Average Purchase Amount: 2,306.88, very high-value purchases.
					•	Total Returns: 0.12, minimal returns.
					•	Churn Status: 100%, high churn risk despite minimal returns.


			Cluster 3 (High Spenders, Frequent Returns, High Churn)
						•	Total Purchases: 29,246.14, among the highest spenders.
						•	Average Purchase Amount: 809.20, indicating consistent mid-to-high-value purchases.
						•	Total Returns: 18.43, frequent returns.
						•	Churn Status: 100%, indicating significant dissatisfaction.


	Cluster 4 (High Spenders, High Loyalty)
					•	Total Purchases: 25,505.67, high spending.
					•	Average Purchase Amount: 802.72, mid-range transactions.
					•	Total Returns: 13.44, frequent returns.
					•	Churn Status: 0%, indicating strong loyalty despite high returns.


			Cluster 5 (High Returns, High Churn)
					•	Total Purchases: 27,609.54, high spending.
					•	Average Purchase Amount: 715.53, lower compared to other high spenders.
					•	Total Returns: 16.46, frequent returns.
					•	Churn Status: 100%, complete churn, possibly due to dissatisfaction.


			Cluster 6 (High Spenders, Highest Returns, High Churn)
					•	Total Purchases: 34,063.17, the highest spending cluster.
					•	Average Purchase Amount: 769.69, mid-range transactions.
					•	Total Returns: 20.17, the highest return rate.
					•	Churn Status: 100%, indicating extreme dissatisfaction or mismatch in expectations.


			Cluster 7 (Loyal High Spenders)
					•	Total Purchases: 31,190.20, very high spending.
					•	Average Purchase Amount: 808.64, mid-range transactions.
					•	Total Returns: 14.20, frequent returns.
					•	Churn Status: 100%, suggesting unresolved issues despite loyalty in spending.


•	Summary of Supervised Model Performance.

    This table presents the evaluation metrics for various supervised learning models trained on the dataset. Here's an in-depth 
    analysis of each model's performance:


		1. Logistic Regression
	
			•	Accuracy: High (0.799973) but misleading due to imbalanced metrics.
			•	Precision, Recall, F1 Score: All metrics are 0, indicating that the model fails to identify the positive class effectively.
			•	ROC-AUC: Near random performance (0.502599), suggesting poor discrimination.

		2. K-Nearest Neighbour’s (KNN)
			•	Accuracy: Moderate (0.766040), slightly lower than Logistic Regression.
			•	Precision: 0.203587, showing better specificity in predicting positives compared to Logistic Regression.
			•	Recall: Very low (0.058259), indicating the model struggles to capture true positives.
			•	F1 Score: Low (0.090593), reflecting the imbalance between precision and recall.
			•	ROC-AUC: Marginally better than random (0.503566).

		3. Decision Tree
			•	Accuracy: Lowest (0.661187) among the models.
			•	Precision: 0.201525, indicating moderate ability to identify positives.
			•	Recall: Higher (0.234235) than Logistic Regression and KNN.
			•	F1 Score: Moderate (0.216653), the best balance achieved so far.
			•	ROC-AUC: Nearly random (0.501102), reflecting limited discriminatory power.

		4. Random Forest
			•	Accuracy: High (0.794880), comparable to Logistic Regression.
			•	Precision: 0.208841, slightly higher than KNN and Decision Tree.
			•	Recall: Very low (0.009132), highlighting its inability to detect positives effectively.
			•	F1 Score: Very poor (0.017499), due to low recall.
			•	ROC-AUC: Slightly better (0.509322) than the other models.

		5. XGBoost
			•	Accuracy: High (0.799667), similar to Logistic Regression.
			•	Precision, Recall, F1 Score: Low scores, reflecting poor handling of the positive class.
			•	ROC-AUC: Best among all models (0.513246), but still close to random.
