Description:

This test verifies that a user with read-only access to a specific originating site should not be able to view or select that site from the dropdown when attempting to create a new request. This ensures access control compliance in the jurisdiction logic during request creation.

⸻

Preconditions:
	1.	User is logged in with read-only access to a specific originating site (e.g., OS-123).
	2.	User is on the Request Dashboard page.
	3.	User clicks on the “Create Request” button.
	4.	The request creation popup appears with fields like Request Name and Main Originating Site.

 Given I have read-only access to the originating site of the request  
And I am on the "Request Dashboard" page  
And I have clicked the "Create Request" button  
And I see the popup with the "Main Originating Site" dropdown  
When I click on the "Main Originating Site" dropdown  
Then the originating site I have read-only access to is not visible in the list  


https://www.figma.com/files/team/1336177960749114040/recents-and-sharing?fuid=1336177955794246988
