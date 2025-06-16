📝 Summary:

UI misalignment when all Request Status filters are selected — “Stakeholders” and “Main Originating Site” fields shift down on the dashboard.

⸻

🧾 Description:

When all checkboxes under the “Request Status” filter are selected on the Request Dashboard, the layout becomes unbalanced. Specifically, key fields such as “Stakeholders” and “Main Originating Site” are pushed down, disrupting the alignment of the filter section. This leads to a poor user experience and inconsistent UI behavior.

Given I am on the "Request Dashboard" page  
And I have opened the filter section  
When I select all available options under the "Request Status" filter  
Then the "Stakeholders" and "Main Originating Site" fields should remain in their original positions  
But they are pushed down and misaligned in the filter layout

Expected Result:

The filter fields layout should remain consistent regardless of how many status options are selected. No displacement of “Stakeholders” or “Main Originating Site” fields should occur.

⸻

💥 Actual Result:

Selecting all request status filters causes “Stakeholders” and “Main Originating Site” fields to move down, affecting layout and usability.

