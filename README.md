## User Behaviour & Churn Analysis

### Background
This project is based on a subscription-based product that allows active subscribers to create projects using photo editing features such as Culling, Editing, and Retouching. Each active month appears as a row in the dataset in the monthly usage logs.

The dataset includes the following fields:

- user_id – Unique subscriber identification number
- active_month – Calendar month in which the subscription is active
- first_payment_date – Date when the user became a paying subscriber
- total_projects – Number of unique projects created that month
- culls – Number of projects that used culling
- edits – Number of projects that used editing
- retouchs – Number of projects that used retouching

Each user will have multiple rows, one per active month, until they churn.

A user who stops having an active month entry from a given month onward can be treated as churned. They may reactivate also.

### Objective
To perform data analysis on this dataset to:
1.	Understand how subscribers evolve in their month-to-month behaviour.
2.	Identify early indicators of churn.
3.	Define a target group/segment (TG) of users with high churn propensity that can be targeted for retention.
4.	Develop and benchmark multiple churn classification models to determine the best-performing approach.
5.	Stratify the subscriber base into 3 risk tiers for targeted, cost-efficient retention efforts.

### Outcomes to Deliver
1.	Key insights from the EDA
2.	Explanation of patterns that correlate with churn
3.	A well-defined, high-risk (TG)
4.	Comparative model evaluation with subscribers segmented into 3 risk tiers
5.	Suggested next steps
