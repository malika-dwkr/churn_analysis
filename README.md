## FocAlign: User Behaviour & Churn Analysis

### Background
FocAlign is a subscription-based product where active subscribers can create as many projects as they want, and they can use any of the features – Culling, Editing, or Retouching – within those projects. Each active month appears as a row in the dataset in the monthly usage logs.
The dataset includes the following fields:
•	user_id – Unique subscriber identifier
•	active_month – The subscription-active calendar month
•	first_payment_date – The date the user became a paying subscriber
•	total_projects – Number of unique projects created that month
•	culls – Number of projects with culling used
•	edits – Number of projects with editing used
•	retouchs – Number of projects with retouching used

Each user will have multiple rows, one per active month, until they churn.

A user who stops having an active month entry from a given month onward can be treated as churned. They may reactivate also.

### Objective
Perform data analysis on this monthly usage dataset to:
1.	Understand how subscribers evolve in their month-to-month behaviour.
2.	Identify early indicators of churn.
3.	Define a target group/segment (TG) of users with high churn propensity that can be targeted for retention.
4.	Develop and benchmark multiple churn classification models to determine the best-performing approach, and stratify the subscriber base into three risk tiers (low, medium, high) for targeted, cost-efficient retention efforts.

### Deliverables Expected
1.	Key insights from the EDA
2.	Explanation of patterns that correlate with churn
3.	A well-defined, high-risk (TG)
4.	Comparative model evaluation with subscribers segmented into 3 risk tiers
5.	Suggested next steps
