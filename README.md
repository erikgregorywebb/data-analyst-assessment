### Background

Clair reaches hourly workers by embedding financial services in the software they use to get paid and clock shifts. Clair’s flagship offering is an earned-wage advance product that gives workers early access to money they've already earned.

Workers sign up for Clair by tapping a “get paid early” button within thier payroll or time tracking app This opens an embedded onboarding experience.

### Dataset

Event tracking has been implemented for each onboarding step. Events are captured in the `onboarding_events` table – each row represents a unique action taken by a user:
- `user_id` unique identifier for each user
- `event_type` specifies the action taken by the user; possible events are ordered below:
  - `started_onboading` tracks when the user opens the onboarding experience for the first time
  - `accepted_terms_of_service` tracks when the user has agreed to Clair's terms of service and initiated the [KYC](https://en.wikipedia.org/wiki/Know_your_customer) (Know Your Customer) processs
  - `passed_kyc` tracks when the user has successfully completed the KYC check
  - `started_application` tracks when the user has started an application for an advance
  - `submitted_application` tracks when the user has submitted an application for an advance
  - `confirmed_advance` tracks when the user has fully agreed to the terms of the advance
  - `opted_for_instant_transfer` tracks when the user opts to upgrade the disbursement speed of thier advance to instant for a fee
- `event_at` specifies when the event occurred

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
