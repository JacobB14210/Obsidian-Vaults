# Requirements
- Email employees out of office every morning
- Employees can submit time off requests
	- Place the approved time off for an employee on the calendar
	- Record when people request time off
	- Types of requests:
		- Automatic approval: Sick
		- Manual approval: Vacation, Personal, Non-work
- Tracker for people who uses sick days
- Tracker for if people haven't used manual type of requests by the end of the year
- Run the server at the district
- Use MySQL database, easier for local implementation
# Database Schema
- Employee Name
- Employee Password
	- Serialized
- Employee ID?
- Employee Type
- Hours:
	- Sick
	- Vacation
	- Personal
	- Non Work
# Permissions
- 