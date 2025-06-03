 Description

When editing a Facility’s fields during the decision phase and navigating away (specifically to Legal Entities) without saving, the user is redirected without any warning. This can lead to data loss due to the absence of a confirmation popup.

⸻

Steps to Reproduce

Given I create a new Request
And I add BG and LE
And I add a Facility
And I submit to Credit Committee and the decision process starts
And I am on the Decision page

When I navigate to the Facility Summary
And I click the arrow to expand and edit Facility fields
And I make changes but do not click the Save button
And I directly click on “Legal Entities” from the left menu

Then I am redirected to the Legal Entities section without any warning popup

⸻

Expected Result

When navigating away from edited (but unsaved) Facility fields to another section (like Legal Entities), a popup should appear saying:
“Do you really want to exit without saving?”
This confirmation should offer options like Stay on Page / Leave Page.

⸻

Actual Result

User is redirected to the Legal Entities section directly, without any warning, resulting in potential loss of unsaved data.


![image](https://github.com/user-attachments/assets/12a67d1a-e853-4365-9659-fbe97b20368c)
