 Description

When the user is on the General Information page during the decision phase and clicks on the DECISIONS section, they are incorrectly redirected to the Credit Proposal page instead of staying within the Decisions section.

⸻

Steps to Reproduce

Given I create a new Request
And I add Legal Entities (LE), Bank Guarantee (BG), and Facilities
And I fill all necessary fields and click Save
And I Submit to Credit Committee (CC) and the decision phase starts
And I am currently on the General Information page

When I click on the DECISIONS section from the left-hand navigation

Then I am incorrectly redirected to the Credit Proposal page

⸻

Expected Result

When I click on the DECISIONS section, I should be taken to the Decisions interface/page, not the Credit Proposal page.

There should be a clear and distinct navigation flow separating the Credit Proposal and Decisions workflows.
They cannot be linked to each other as they serve different business processes and user intents.

⸻

Actual Result

Clicking on the DECISIONS section redirects to the Credit Proposal page unexpectedly, disrupting the intended workflow and causing confusion.
