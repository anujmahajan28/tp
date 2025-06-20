✅ Bug Title (JIRA Summary):

[REQUEST][Facilities] Second pop-up after warning appears misaligned during import

⸻

✅ Description:

When a user clicks on Import Facility without entering any data and confirms the initial warning pop-up, the following pop-up appears misaligned on the screen.

⸻

✅ Steps to Reproduce:
	1.	Create a new request.
	2.	Navigate to the Facilities page.
	3.	Click on Import Facility.
	4.	Without selecting or entering any values, click Import.
	5.	A warning pop-up is displayed (e.g., “Please select facility data”).
	6.	Click OK on the warning pop-up.
	7.	Observe the alignment of the next pop-up displayed.

⸻

✅ Expected Result:

The second pop-up should appear properly aligned and centered on the screen.

⸻

✅ Actual Result:

The second pop-up appears misaligned, breaking the visual flow and user experience.


New bug found
Given I create request 
And i am on Facilities page
And i click on Import facility 
And without taking any type of entry i click on import
And pop up is displayed with warning 
When i click on ok for warning 
Then the next pop up is displayed miss aligned
