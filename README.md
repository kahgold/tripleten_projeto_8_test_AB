# Project: Prioritizing Hypothesis and A/B Testing Analysis

*You are an **analyst** at a large online store. You and your marketing team have **compiled a list of hypotheses** to help **increase revenue**. The lists are:*

1. **Add two new channels** for attracting traffic. This will bring **30% more users**
2. **Launch** your own **delivery service**. This will **shorten delivery time**
3. **Add product recommendation blocks** to the store's site. This will **increase conversion and average purchase size**
4. **Change the category structure**. This will **increase conversion** since users will find the products they want more quickly
5. **Change the background color** on the main page. This will **increase user engagement**
6. **Add a customer review page**. This will **increase the number of orders**
7. **Show banners with current offers and sales** on the main page. This will **boost conversion**
8. **Add a subscription form** to all the main pages. This will help you compile a **mailing list**
9. **Launch a promotion** that gives users **discounts on their birthdays**

*Hypothesis testing requires substantial funding, while the resources you have may be limited. This is a natural thing to happen. Therefore, you must be able to **determine** which hypotheses need to be **tested** and which hypotheses should be **removed** first. In order to maximize growth in key business metrics, the hypotheses you formulate should be **prioritized**.*

*Your supervisor want you to implement a **framework to prioritize** hypotheses. Impact, confidence, and effort or **ICE** for short, are among the most popular methods used to prioritize problems. There is also a modified version of ICE, namely **RICE**.*

*RICE consists of four components, namely:*

- **Reach** — how **many** users will be affected by the update you want to introduce
- **Impact** — how **strongly** the update will **affect** users, their experience, and their satisfaction with the product
- **Confidence** — how **confident** you are that your product **will influence** users in the way you introduce it
- **Effort** — how much it **costs** to test a hypothesis

*During the brainstorming session, all departments involved have given their assessment of each parameter for each hypothesis. These values are then averaged on a scale of 1-10 and compiled on /datasets/hypotheses_us.csv.*

*After prioritizing hypothesis, UX Research team will conduct the A/B testing based on the selected hypothesis and the results will be compiled on /datasets/orders_us.csv and /datasets/visits_us.csv.*

**Project Instructions**

1. ***Prioritizing Hypotheses***

- *The file hypotheses_us.csv contains nine hypotheses for increasing the income of an online store with Reach, Impact, Confidence, and Effort predefined for each of the hypotheses. your tasks are:*
    - Implement an `ICE` framework to prioritize hypotheses. Sort those hypotheses in descending order of priority.
    - Implement a `RICE` framework to prioritize hypotheses. Sort those hypotheses in descending order of priority.
    - Indicates the change in the priority of the hypothesis when `RICE` applied to replace `ICE`. Provide an explanation for the change.

2. ***A/B Testing Analysis***
- Describe **cumulative income by group**. Make the conclusions and assumptions.
- Draw a **cumulative average order size by group**. Make the conclusions and assumptions.
- Draw a **relative difference** for the **cumulative average order size** of **group B compared to group A**. Make conclusions and assumptions.
- Calculate the **conversion rate of each cohort** as the ratio of orders to the number of visits each day.
- **Graph the daily conversion rates** of both groups and explain the differences. Make the conclusions and assumptions.
- Create a **scatter chart for the number of orders per user**. Make the conclusions and assumptions.
- Calculate the **95th and 99th percentiles** for the **number of orders per user**. Determine the point at which a data point turns into an anomaly.
- Create a **scatter chart for the order revenue**. Make the conclusions and assumptions.
- Calculate the **95th and 99th percentiles** for the **order revenue**. Determine the point at which a data point turns into an anomaly.
- Find the **statistical significance of conversion differences** between groups using **raw data**. Make the conclusions and assumptions.
- Find the **statistical significance of the difference in average order size** between groups using **raw data**. Make the conclusions and assumptions.
- Find the **statistical significance of conversion differences** between groups using **filtered data**. Make the conclusions and assumptions.
- Find the **statistical significance of the difference in average order size** between groups using **filtered data**. Make the conclusions and assumptions.
- Make a **decision** based on the test results. Possible decisions are:
    - **Stop testing**, as well as **consider one of the groups as a leader**.
    - **Stop the test**, as well as **conclude that there is no difference** between the two groups.
    - **Continue testing**.

**Data dictionary**
**The hypotheses table:**
- `Hypotheses` — brief descriptions of the hypotheses
- `Reach` — user reach, on a scale of one to ten
- `Impact` — impact on users, on a scale of one to ten
- `Confidence` — confidence in the hypothesis, on a scale of one to ten
- `Effort` — the resources needed to test a hypothesis, on a scale of one to ten. The higher the `Effort` value, the more resources are required for the test.

**The orders table:**
- `transactionId` — order identifier
- `visitorId` — identifier of the user who placed the order
- `date` — order date
- `revenue` — order revenue
- `group` — the A/B testing group the user belongs to

**The visits table:**
- `date` — date
- `group` — A/B testing group
- `visits` — the number of visits on the specified date for the specified A/B test group

**Conclusions**
**Overview do dataframe df_hypotheses:**
- *The dataframe consists of five columns: `hypothesis`, `reach`, `impact`, `confidence` and `effort`, with 9 rows each, no significant difference between mean and median, no duplicates, missing data, or outliers.*

**Overview do dataframe df_orders:**
- *The dataframe contains five columns: `transaction_id`, `visitor_id`, `date`, `revenue` and `group`, with 1197 rows each, after removing stacked data, now the dataframe has 1016 rows in each column. The columns are of type int64, datetime64[ns], float64, and object. The name of the columns `transactionId` and `visitorId` has been changed, and the `date` column has been converted from object to datetime. No duplicates, missing data, or outliers are found.*

**Overview do dataframe df_visits:**
- *The dataframe contains three columns: `date`, `group`, and `visits`, with 62 rows each. The `date` column has been converted from object to datetime, and there are no outliers in the `visits` column.*

- Either the raw data or the filtered data showed statistically significant differences in terms of conversions between cohorts.
- Neither the raw data nor the filtered data showed any statistically significant differences in terms of average order size between groups.
- A graph showing conversion differences between groups shows that group B's results are better. Which proven by an increase of 16\%.
- A graph showing the difference in average order size between groups shows that group B's results are higher than group A. A presence of anomalies may have skewed the results, but a method to filter this outlier shows that there is a decline of 3\% compared to group A.

*This A/B testing have been done to test hypothesis 3, which is:*

- Add product recommendation blocks to the store's site. This will increase conversion and average purchase size.

*Based on these facts, it can be concluded that this test did go well partially. There is a probability that segment B will get better than segment A. Therefore, we recommend to continue the test for another month so we can get more data.*
