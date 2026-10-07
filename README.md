💊 Delta Pharmacy – Manual & Functional Testing Project

A manual QA project for Delta Pharmacy, a web application that lets customers browse pharmaceutical products, place orders, and manage prescriptions, with separate Customer, Pharmacist, and Admin roles.

This repository documents the test design, execution results, and defects found while testing the application.

Project type: Training project Role: QC / QA Engineer (manual testing) Author: Lobna Abdelaziz Mohamed Bar

📑 Test Documentation
Document	Link
Test Cases, Bug Report & Summary Report (Google Sheet)	Open the test suite

The workbook contains three sheets:

Test Cases – every test case with data, steps, expected vs. actual result, and status
Bug Report – defects found during execution
Report – summary of the test execution
🎯 Objectives
Verify that the core user flows work as specified
Validate input handling (valid, invalid, empty, boundary, and malicious input)
Check role-based behavior for Customer, Pharmacist, and Admin users
Identify and document defects with clear steps to reproduce
🧭 Scope
Modules tested
Module	What was covered
Registration	Form fields, required-field validation, name / email / password / phone / address rules, duplicate email, special characters, long input, multiple clicks, navigation, responsive view, response time
Login	Valid and invalid credentials, empty fields, email format, spaces, letter case, long input, Enter-key submit, refresh behavior, error-message safety, login per role
Dashboard	Dashboard cards and counts, user info, sidebar navigation, search, notifications badge, logout, page refresh behavior, role-based metrics
Products	Page access, product cards (name, description, category, price, stock), images, product details, search
Roles covered

Customer · Pharmacist · Admin

🧪 Testing Approach
Test Type	Examples
Functional testing	Registration, login, dashboard, product listing
Negative testing	Empty fields, invalid email formats, wrong passwords, unregistered users
Boundary-value testing	Minimum / maximum field lengths, one-character names, very long input
Security (basic) testing	SQL Injection patterns and XSS script input in form fields; password masking; error messages that do not expose sensitive data
UI / usability testing	Field and button display, active menu highlighting, responsive/mobile view
Role-based testing	Dashboard content and behavior for Customer, Pharmacist, and Admin
Basic performance check	Registration response time under normal conditions
📝 Test Case Structure

Each test case in the sheet includes:

Column	Description
Module	Feature area under test
Test Case ID	Unique ID (e.g., TC-001)
Test Case Title	What is being verified
Precondition	State required before execution
Test Data	Input values used
Steps to Reproduce	Numbered steps
Expected Result	Behavior defined by the requirement
Actual Result	Behavior observed during execution
Status	Pass / Fail
Example
Field	Value
ID	TC-016
Title	Verify Email without @ symbol
Precondition	User is on the Registration page
Steps	1. Enter an invalid email 2. Complete remaining fields 3. Click Register
Expected	Email validation message is displayed and registration is blocked
Actual	Validation message displayed and registration blocked
Status	✅ Pass
🐞 Key Defects Found

A selection of the failed test cases (full details are in the Bug Report sheet):

Test Case	Module	Defect	Suggested Severity
TC-083 / TC-084	Dashboard	Refreshing the page converts a Customer / Pharmacist account into an Admin account	🔴 Critical
TC-042	Login	After an invalid-password attempt, clicking Login a second time logs the user in; the error message also disappears too quickly to read	🔴 High
TC-087	Dashboard	"Active Users" card is shown to the Pharmacist although the Users module is Admin-only	🟠 High
TC-079	Dashboard	Search button does not work and returns no results	🟠 Medium
TC-010, TC-011	Registration	Full Name accepts numbers only and special characters	🟠 Medium
TC-027, TC-028, TC-029	Registration	Phone number accepts letters, emoji, and spaces only	🟠 Medium
TC-021	Registration	Email without a domain extension (e.g., name@test) is accepted	🟠 Medium
TC-031, TC-032	Registration	Address accepts spaces only and emoji/special characters	🟡 Low–Medium
TC-014	Registration	One-character Full Name accepted (no length validation)	🟡 Low–Medium
TC-038	Registration	Extremely long Full Name is accepted and breaks the dashboard layout	🟡 Medium
TC-098	Products	No product detail page is available	🟡 Medium
TC-097	Products	Product images are not displayed	🟡 Low
TC-082	Dashboard	Notification badge is displayed when there are no notifications	🟡 Low
TC-080	Dashboard	User name / avatar is not clickable for any role	🟡 Low

Severity levels above are suggestions and can be adjusted to match your Bug Report sheet.

✅ Notable Passed Checks
Required-field validation on Registration and Login
Duplicate email registration is rejected
Email format validation (missing @, missing domain, spaces, special characters)
Password fields are masked and cleared after refresh
SQL Injection and script input are treated as plain text and do not execute
Login error messages do not expose sensitive information
Registration and Login pages work in responsive/mobile view
🛠️ Tools & Environment
Item	Details
Test management	Google Sheets
Application under test	Delta Pharmacy web application (run locally on localhost:3001)
Testing type	Manual
Browser	[add browser and version]
Operating system	[add OS]
🚀 How to Use This Project
Open the test suite.
Review the Test Cases sheet to see the coverage by module.
Filter the Status column by Fail to see the defects.
Check the Bug Report and Report sheets for details and the execution summary.
📚 What I Practiced
Writing clear, structured, and reproducible test cases
Applying equivalence, boundary-value, and negative testing techniques
Basic security testing (SQL Injection and XSS input validation)
Role-based access and behavior testing
Documenting actual vs. expected results and reporting defects
👩‍💻 Author

Lobna Abdelaziz Mohamed Bar Junior Quality Control Engineer | ISTQB Certified Tester (CTFL 4)

📧 lobna.bar2022@gmail.com
💼 LinkedIn
🐙 GitHub
