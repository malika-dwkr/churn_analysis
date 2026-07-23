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

---

### Objective
To perform data analysis on this dataset to:
1.	Understand how subscribers evolve in their month-to-month behaviour.
2.	Identify early indicators of churn.
3.	Define a target group/segment (TG) of users with high churn propensity that can be targeted for retention.
4.	Develop and benchmark multiple churn classification models to determine the best-performing approach.
5.	Stratify the subscriber base into 3 risk tiers for targeted, cost-efficient retention efforts.

---

### Outcomes to Deliver
1.	Key insights from the EDA
2.	Explanation of patterns that correlate with churn
3.	A well-defined, high-risk (TG)
4.	Comparative model evaluation with subscribers segmented into 3 risk tiers
5.	Suggested next steps
 
---
 
### Key Insights

1. Churn is not directly a result of low engagement. 

While the TG shows significantly lower usage and feature adoption, a higher proportion of churn is actually observed among active low-risk users. Therefore, low engagement alone does not fully explain churn behaviour. 

2. Editing is the most critical feature linked to retention. 

- `Editing` shows the largest behavioural gap between retained and churned users, acting as the core feature within the product workflow. 
- This was further validated by the predictive models, where `avg_edits` and `edit_adoption` consistently ranked among the top predictors of churn across all 3 models. 

3. Long-term retention is largely determined during the onboarding and early product exposure phase. 

- Churn is heavily concentrated within the first 5 months of usage, and the target group (TG) reflects users who have not fully realised product value, therefore highlighting the importance of early lifecycle intervention. 
- `total_tenure` being the strongest or second strongest predictor across all 3 models reinforced this finding. 

4. Incomplete workflow adoption is a stronger churn signal than raw activity levels. 

- Users who fail to consistently move through the editing pipeline (culling -> editing -> retouching) show higher churn propensity than users with low but structured engagement.
- `retouch_adoption` carried the strongest protective coefficient in the logistic regression model (-2.15), further supporting this. 

5. XGBoost is the best performing churn prediction model. 

XGBoost achieved the highest AUC (0.78), accuracy (70.9%), sensitivity (70.0%), and specificity (71.6%), confirming it to be the most reliable model for identifying at-risk users and assigning risk tiers. 

6. Risk tier profiling reveals distinct behavioural patterns across segments. 

- High Risk users are characterised by short tenure, low project activity, and significantly lower feature adoption compared to Low Risk users.
- This confirms early lifecycle stage and feature adoption depth as the clearest differentiators between churned and retained users. 

---

### Limitations

1. No financial metrics (pricing or revenue) data is available. 

As a result, churn impact cannot be weighed against customer value or subscription plans. 

2. Churn definition is activity-based, not cancellation-based. 

Users are classified as churned based on absence of activity after the cutoff month, which may include temporary inactivity or delayed usage cycles rather than true subscription cancellations. 

3. Reactivation behaviour is not accounted for. 

Users returning after a period of inactivity are treated the same as churned users, which may be inflating churn signals and misclassifying reactivated users in the risk tiers. 

---

### Suggested Next Steps - Action Plan

1. Data Requirements: 

- Incorporate pricing, subscription tier, plan type, revenue information to weigh churn impact against customer value.
- Add geographic level data to segment customers based on geographies.
- Add reactivation details to distinguish between temporary inactivity and true churn, which could also improve model accuracy. 

2. Product Actions: 

- Provide in-product guidance to encourage progression through the full editing pipeline (e.g. guided checklist; progress bar showing workflow completion status).
- Deploy targeted interventions differentiated by risk tiers. For example:
 - High Risk users: "Quick Start Guides", dedicated assistance, 24/7 AI chatbot support
 - Medium Risk users: feature discovery prompts, usage tips
 - Low Risk users: loyalty incentives to deepen engagement 

*3. Experiments:* 

- Test different onboarding efforts that guide users towards early engagement (e.g. "Complete your first edit to unlock advanced features"; step-by-step workflow prompts inside the editor).
- Experiment with behavioural nudges for users showing early-stage decline (e.g. "Complete your first edit" notifications; reminder nudges after 3 days of inactivity).
- Re-run the models after incorporating financial and reactivation data to evaluate whether predictive performance improves. 
