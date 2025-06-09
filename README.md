Absolutely! Below are 4 separate Gherkin scenarios, each focused on a single, clear action. This aligns with best practices and review expectations for modular, testable cases.

⸻

✅ Scenario 1: Navigate to Stakeholders Section

Feature: Navigate to Stakeholders Section

Scenario: Open the Stakeholders section from the left-side menu

  Given I have successfully created a new request
  And I am on the Request details page
  When I click on the "Stakeholders" option from the left-side menu
  Then the Stakeholders page is displayed


⸻

✅ Scenario 2: Click on ‘User or Team’ Input Field

Feature: Stakeholder Entry

Scenario: Click on the 'User or Team' input field

  Given I am on the "Stakeholders" page of a request
  When I click on the "User or Team" input field
  Then the field becomes active and ready for input


⸻

✅ Scenario 3: Enter Team Name Prefix

Feature: Stakeholder Search

Scenario: Enter the first few characters of a team name

  Given I am on the "Stakeholders" page of a request
  And the "User or Team" input field is active
  When I enter the first few characters of a team name (e.g., "CTM")
  Then a list of matching teams is displayed below the input field


⸻

✅ Scenario 4: Select Team from Suggestions

Feature: Stakeholder Selection

Scenario: Select a team from the list of suggestions

  Given a list of teams is displayed after entering partial team name
  When I select one or more teams from the suggestion list
  Then the selected team(s) are displayed under the input field with a cross (×) icon


⸻

Let me know if you want to combine them into a single end-to-end flow, or convert them into a test suite structure (e.g., for Xray or JIRA).
