# Purpose
- Help owner in automating property ledger
- Keep information private
	- Some support should not have access to the customer data
# Objectives and Success Criteria
- Excel based VBA menu
	- Reduces human error with rental ledger
	- Also be able to do it manually like before
## Phase 0
- VBA can potentially be hacked by disabling macros
## Phase 1
- Move to a more secure web based solution
	- Access data from any device
- Logging and viewing of user activity
# High Level Requirements
- Ledger transaction data  should be kept in the spreadsheet
	- Customer data, and other restricted data is stored in access database
	- ==Non-admin users shouldn't be able to enter or view any spreadsheets in its raw form==
		- Should look like a menu driven application
- Support staff have access to a subset of rentals grouped and assigned by admin
	- ==Functions==
		- ==Add new entry==
		- ==Comment rent received==
		- ==Enter charge for damages==
		- ==Give credit to tenant for rent collect and/or materials purchased for the property by the tenant==
	- Only view the full ledger including balance
		- Shouldn't be able to modify any past entries
	- Access to read the tenants phone numbers, property address and email address, due dates, and late fee grace period
- After authentication
	- For admin and support staff
		- ==Prompt for any ledger items to be entered based on the date==
			- ==Monthly charge for rent based on each properties monthly rent anniversary==
			- ==Prompt user to enter an entry for a late fee to be applied if rent is past due==
		- After all prompts property manager should be able to enter credit for rent
- ==Business analyst generates reports==
	- ==Should not have access to any customer data or ledger entries==
	- ==Just rollup of number in the ledger==
- Admin
	- ==Should be able to choose menu or legacy mode after authentication==
	- Legacy mode
		- Take them to spreadsheet like currently and do nothing else
	- Menu mode
		- Show warning for all properties that have lease expiring within 90 days
	- ==Add/close out a tenant from a property==
	- ==Add/change roles for the application==
	- ==Add a new spreadsheet for a property==
	- ==Preset the property groups for reports and access rights of the support staff==
# WBS Assignment
- Sections to add
	- Website design
	- Home page design
	- Database
	- Authentication
	- Reports
	- Legacy and Menu Mode