# Customer Segmentation Using Transactional Data

## Project question
How can a retailer use observed purchasing behavior to identify practical customer groups and design testable marketing actions?

## Project contents
- analysis.ipynb: complete Google Colab analysis notebook.
- customer_rfm_segments.csv: one row per identified customer, with RFM features and cluster assignment.
- figures/: exploratory and clustering charts.
- business_insights.pdf: concise business interpretation and recommendations.

## Data and methods
The project uses the public UCI Online Retail transaction dataset (December 2010–December 9, 2011). Cleaning removes rows without CustomerID, duplicate rows, cancellations, and non-positive quantities or unit prices. Transaction revenue is Quantity × UnitPrice. Customer-level Recency, Frequency, and Monetary (RFM) features are calculated, log-transformed with log1p, standardized, and clustered with K-Means. K values from 2 through 8 are compared using inertia and silhouette score.

The two-cluster solution had the highest silhouette score among the tested values (0.433). It is an exploratory starting point, not a definitive or causal classification.

## Main findings
- Cluster 0 contains 2,672 customers (61.6%); median Recency is 96 days, Frequency is 1 invoice, and Monetary is 363.08.
- Cluster 1 contains 1,666 customers (38.4%); median Recency is 16 days, Frequency is 6 invoices, and Monetary is 2,061.08.
- Cluster 1's median observed spend is about 5.68 times Cluster 0's. Monetary is historical revenue in the dataset's currency units, not profit or lifetime value.

## Suggested next step
Test retention and win-back ideas with randomized holdout groups. Measure incremental repeat purchases, revenue, gross margin, offer cost, and opt-outs before scaling.

## Limitations
The data are historical and include only customers with an identifiable CustomerID. RFM reflects recorded transactions, not motivation, demographics, satisfaction, or response propensity. K-Means segments depend on feature and modeling choices and do not establish cause and effect. Profit, campaign costs, and customer lifetime value are not measured.

## Reproducibility
Open analysis.ipynb in Google Colab and run the cells from top to bottom. The source dataset is public at https://archive.ics.uci.edu/dataset/352/online+retail.
