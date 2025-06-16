Summary:

Duplicate tooltip appears on hovering over instruction icons in Facility Summary

⸻

📝 Description:

When hovering over info tooltips in the Facility Summary section (e.g., Timeline for Implementation, Market Facility, For Decision), two overlapping tooltip popups with the same content are shown. This causes a cluttered UI experience and might confuse users.

Given I create a new request  
And I add Business Group and Legal Entity  
And I add a Facility  
When I navigate to the Facility Summary  
And I click the arrow to expand the facility section  
And I hover over the tooltip of fields like "Timeline for Implementation", "Market Facility", or "For Decision"  
Then I see two tooltip popups with identical information

✅ Expected:

Only a single tooltip should appear when hovering over instruction icons.

⸻

❌ Actual:

Two identical tooltips are displayed simultaneously, overlapping each other.

