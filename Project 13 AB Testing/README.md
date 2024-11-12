# A/B Test Analysis for Recommender System Test

## Project Overview

This project is an analysis of an A/B test conducted by an international online store to evaluate the impact of an improved recommendation system. The analysis follows the setup, data exploration, and hypothesis testing to determine if the new recommendation system (Group B) improves user engagement and purchase conversions compared to the control group (Group A).

## Objectives

The primary goal of this analysis is to verify whether the A/B test was conducted correctly and to assess its results. The expected outcome is that within 14 days of signing up, users in the test group (B) will show a 10% increase at each stage of the conversion funnel:
1. Product Page Views (event: `product_page`)
2. Product Card Views (event: `product_card`)
3. Purchases (event: `purchase`)

The analysis will evaluate:
- The accuracy of the test setup.
- User conversion across different funnel stages.
- Statistical significance of the conversion differences between groups A and B.

## Data Description

The dataset includes several CSV files:

1. **ab_project_marketing_events_us.csv**  
   Contains the marketing event schedule for 2020.
   - `name`: Marketing event name.
   - `regions`: Regions where the campaign was held.
   - `start_dt`: Campaign start date.
   - `finish_dt`: Campaign end date.

2. **final_ab_new_users_upd.csv**  
   Contains information about new users who signed up from December 7 to 21, 2020.
   - `user_id`: Unique identifier for each user.
   - `first_date`: Sign-up date.
   - `region`: User's region.
   - `device`: Device used to sign up.

3. **final_ab_events_upd.csv**  
   Contains all events of new users from December 7, 2020, to January 1, 2021.
   - `user_id`: User identifier.
   - `event_dt`: Event date and time.
   - `event_name`: Type of event (e.g., `product_page`, `product_card`, `purchase`).
   - `details`: Additional event data (e.g., order total for purchases).

4. **final_ab_participants_upd.csv**  
   Lists all test participants.
   - `user_id`: User identifier.
   - `ab_test`: Name of the test.
   - `group`: Group assignment (A = control, B = new funnel).

## Analysis Steps

### 1. Research Goals

   - Verify that the A/B test setup is correct.
   - Analyze user conversion across funnel stages in both groups.
   - Confirm statistical significance of conversion differences.
   - Document findings on test accuracy and results.

### 2. Data Exploration

   - **Data Types**: Check for type consistency across all files and convert where necessary.
   - **Missing and Duplicate Values**: Identify and understand any missing or duplicate entries and their implications.
   - **User Overlap**: Confirm if any users are present in both groups (A and B).
   - **Daily Events Distribution**: Explore event distribution by day to check for test consistency.
   - **Marketing Events**: Examine if any marketing events overlapped with the test period that could impact results.

### 3. Exploratory Data Analysis (EDA)

   - **Conversion Rates**: Calculate and analyze conversion rates for each funnel stage (`product_page`, `product_card`, `purchase`).
   - **Events per User**: Check the event count distribution per user in both groups.
   - **Funnel Drop-Off**: Analyze drop-off rates between stages for each group.

### 4. A/B Test Evaluation

   - **A/A Test**: Evaluate if the groups were split correctly by checking baseline equivalency.
   - **Z-Test for Proportion Differences**: Apply the z-test to check for statistically significant differences between groups A and B at each funnel stage.

### 5. Conclusions and Recommendations

   - Summarize the A/B test setup validation and EDA findings.
   - Document statistical analysis results, indicating whether the new recommendation system achieved the expected lift.
   - Provide recommendations for future A/B testing and potential improvements.

## Tools and Libraries Used

- **Python Libraries**: pandas, numpy, scipy, matplotlib, seaborn
- **Statistical Tests**: Z-test for proportions
