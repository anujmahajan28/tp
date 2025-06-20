✅ JIRA Summary:

[REQUEST][Facilities] Misaligned pop-up appears after confirming import warning

⸻

✅ Description:

When a user tries to import a facility without selecting any input, a warning pop-up is triggered (e.g., “Please select at least one facility to import”). After clicking “OK” on the warning, the next pop-up appears misaligned on the screen, affecting visual consistency.

⸻

✅ Steps to Reproduce:
	1.	Create or open an editable Request (e.g., in “Draft” status).
	2.	Navigate to the Facilities page.
	3.	Click on Import Facility.
	4.	Do not enter any filters or select any facility.
	5.	Click on the green “Import(0)” button.
	6.	Observe the warning pop-up message: “Please select at least one facility to import”.
	7.	Click OK on the warning pop-up.
	8.	Observe the position of the next pop-up or modal.

⸻

✅ Expected Result:

After confirming the warning, any subsequent pop-up or modal should appear properly aligned and centered on the screen.

⸻

✅ Actual Result:

The next pop-up appears misaligned (as seen in the attached screenshot), affecting the UI layout.


New bug found
Given I create request 
And i am on Facilities page
And i click on Import facility 
And without taking any type of entry i click on import
And pop up is displayed with warning 
When i click on ok for warning 
Then the next pop up is displayed miss aligned
