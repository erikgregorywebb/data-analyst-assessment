### Background

Clair is a digital banking platform that reaches hourly workers by embedding financial services in the software they use to clock-in and clock-out. Clair’s flagship offering is a free earned-wage advance product to grant workers early access to money they've already earned.

Workers sign up for Clair by tapping a “get paid early” button within the app they use to clock-in and clock-out. This opens an embedded onboarding experience in which a worker (1) creates a bank account, (2) switches their paycheck (direct deposit) to the account, and (3) takes their first wage advance. 

### Dataset

Event tracking has been implemented for each onboarding step. Events are captured in the `events` table – each row represents a unique action taken by a user:
- `user_id` unique identifier for each user
- `event_name` specifies the action taken by the user; possible events are ordered below:
  - `start_onboarding` tracks when the user opens the onboarding experience for the first time
  - `accepted_tos` tracks when the user accepts the terms of service
  - `create_account` tracks when the user has successfully created an account by passing KYC (Know Your Customer)
  - `attempted_direct_deposit_update` tracks when the user attempts to move their paycheck to Clair
  - `updated_direct_deposit` tracks when the user successfully moves their paycheck to Clair
  - `took_first_wage_advance` tracks when the user takes a wage advance for the first time
- `event_timestamp` specifies when the event occurred

General information about each user is captured in the `users` table:
- `user_id` unique identifier for each user
- `business_id` identifies the user's employer, meaning the business they work for
- `partner_id` identifies the app where the worker clocks in and out 
- `state` identifies where the user lives

These tables are located in a cloud-hosted PostgreSQL database:
- Host: `pg-285c4482-getclair-7a3a.a.aivencloud.com`
- Port: `10594`
- Database: `assessment`

*Username and password credentials will be shared by email.*

### Your Task

Using the tools of your choice, analyze the data to identify where drop-off is occurring during onboarding. Identify pain points by calculating how long it takes users to move through each step. The Product team intends to prioritize the feature backlog based on your recommendations. There is no “right” answer; the emphasis is creativity and clearly communicating your approach and findings. For your own sake, please limit time spent on the assessment to 3 hours.

### Deliverables
- 2-4 slides describing your approach, findings, and recommendations; include visuals to support your conclusions
- A copy of the underlying analysis (e.g., Tableau workbook, Jupyter Notebook, etc.)

*Note: While this dataset is structured to imitate real user activity, the event names, timestamps, and user identifier are synthetically generated. Given the randomness infused into the exercise, this is not an effort to outsource work to interviewing candidates, but rather, an opportunity to share a flavor of the data you’ll interact with working at Clair.*
