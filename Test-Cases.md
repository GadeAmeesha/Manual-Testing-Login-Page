**Login Page Manual Testing — Detailed Test Cases**

## 1. Project Information

**Project Name:** Login Page Manual Testing  
**Testing Type:** Manual Testing  
**Application:** Sample Web Application Login Page  
**Test Level:** System Testing (when testing the complete login feature)  
**Test Approach:** Black-box Testing  
**Status:** Test cases designed; execution pending  
**Author:** Ameesha Gade

## 2. Objective

To verify the login functionality of a web application, validate user inputs, identify defects, and evaluate security, usability, compatibility, and error handling.

## 3. Scope

- Valid and invalid login credentials
- Mandatory field validation
- Input length and boundary validation
- Equivalence partitioning
- Boundary value analysis
- Decision table testing
- State transition testing
- Error guessing and exploratory testing
- Functional and negative testing
- Security checks
- Usability and accessibility checks
- Compatibility and responsive UI checks
- Basic performance observations
- Defect reporting and test summary

## 4. Assumptions

The following are assumptions for designing the test cases. Confirm them against the actual application requirements before execution.

1. The login page contains username/email, password, and Login button.
2. A valid test account is available.
3. Empty mandatory fields should not allow login.
4. Invalid credentials should be rejected.
5. Passwords should be masked by default.
6. Successful login should navigate to an authorized page.
7. Account lockout, password length restrictions, session timeout, and CAPTCHA are application-dependent features. Related tests should be executed only when supported by the requirements.

## 5. Test Case Format

Each test case contains:
- Test Case ID
- Test Scenario
- Testing Technique
- Priority
- Preconditions
- Test Data
- Test Steps
- Expected Result
- Actual Result
- Status

**Initial execution status for every test case: Not Executed.**



# 6. Functional Testing

## TC001 — Login with Valid Credentials

**Technique:** Positive Testing  
**Priority:** High

**Precondition:** An active test account exists.

**Test Data:** Valid username and valid password.

**Steps:**
1. Open the login page.
2. Enter the valid username.
3. Enter the valid password.
4. Click Login.
5. Observe the resulting page.

**Expected Result:** The application authenticates the user and navigates to the authorized landing page.

**Actual Result:** To be recorded during execution.  
**Status:** Not Executed

## TC002 — Login with Invalid Username

**Technique:** Negative Testing  
**Priority:** High

**Test Data:** Invalid username and valid password.

**Steps:**
1. Open the login page.
2. Enter an unregistered username.
3. Enter a valid test password.
4. Click Login.

**Expected Result:** Authentication is rejected, and an appropriate error message is displayed.

**Status:** Not Executed

## TC003 — Login with Invalid Password

**Technique:** Negative Testing  
**Priority:** High

**Test Data:** Valid username and incorrect password.

**Steps:**
1. Open the login page.
2. Enter the valid username.
3. Enter an incorrect password.
4. Click Login.

**Expected Result:** Login is rejected, and the application displays an appropriate error message.

**Status:** Not Executed

## TC004 — Login with Both Credentials Invalid

**Technique:** Negative Testing  
**Priority:** High

**Test Data:** Unregistered username and incorrect password.

**Steps:**
1. Open the login page.
2. Enter an unregistered username.
3. Enter an incorrect password.
4. Click Login.

**Expected Result:** Login is rejected without exposing sensitive account information.

**Status:** Not Executed

## TC005 — Verify Case Sensitivity of Username

**Technique:** Functional Testing  
**Priority:** Medium

**Precondition:** A valid account exists with a known username.

**Steps:**
1. Log in using the exact username.
2. Record the result.
3. Change the letter case of the username.
4. Keep the password unchanged.
5. Submit the form.

**Expected Result:** Username matching follows the application's documented case-sensitivity rules.

**Status:** Not Executed

## TC006 — Verify Password Case Sensitivity

**Technique:** Functional Testing  
**Priority:** High

**Steps:**
1. Enter a valid username.
2. Enter the correct password and verify the login behavior.
3. Repeat using a password with altered letter case.
4. Compare the results.

**Expected Result:** The correct password authenticates successfully; a case-modified password is rejected unless it is actually the same password.

**Status:** Not Executed

## TC007 — Verify Login Button Behavior

**Technique:** Functional Testing  
**Priority:** High

**Steps:**
1. Open the login page.
2. Enter valid credentials.
3. Click Login once.
4. Observe the response.
5. Check whether duplicate submissions occur during processing.

**Expected Result:** The form submits correctly, displays appropriate feedback, and does not create duplicate login actions.

**Status:** Not Executed

## TC008 — Verify Login Using Enter Key

**Technique:** Functional and Usability Testing  
**Priority:** Medium

**Steps:**
1. Enter a valid username.
2. Enter a valid password.
3. Press Enter while focused on the password field.
4. Observe the behavior.

**Expected Result:** The form submits as expected by the application's keyboard interaction design.

**Status:** Not Executed

## TC009 — Verify Logout and Re-login

**Technique:** Functional Testing  
**Priority:** High

**Steps:**
1. Log in with a valid account.
2. Click Logout.
3. Attempt to open a protected page.
4. Return to the login page.
5. Log in again.

**Expected Result:** Logout ends the authenticated session, protected pages require authentication, and a valid subsequent login works.

**Status:** Not Executed

---

# 7. Mandatory Field Validation

## TC010 — Submit with Both Fields Empty

**Technique:** Negative Testing  
**Priority:** High

**Steps:**
1. Open the login page.
2. Leave username and password empty.
3. Click Login.

**Expected Result:** Login is prevented, and appropriate mandatory-field validation is shown.

**Status:** Not Executed

## TC011 — Submit with Empty Username

**Technique:** Negative Testing  
**Priority:** High

**Steps:**
1. Leave username empty.
2. Enter a valid password.
3. Click Login.

**Expected Result:** Login is prevented and username validation is displayed.

**Status:** Not Executed

## TC012 — Submit with Empty Password

**Technique:** Negative Testing  
**Priority:** High

**Steps:**
1. Enter a valid username.
2. Leave password empty.
3. Click Login.

**Expected Result:** Login is prevented and password validation is displayed.

**Status:** Not Executed

## TC013 — Enter Spaces Only in Username

**Technique:** Negative Testing / Error Guessing  
**Priority:** Medium

**Test Data:** Username containing only spaces.

**Steps:**
1. Enter spaces into the username field.
2. Enter a valid password.
3. Click Login.

**Expected Result:** Whitespace-only input is handled according to validation rules and must not authenticate an invalid account.

**Status:** Not Executed

## TC014 — Enter Spaces Only in Password

**Technique:** Negative Testing  
**Priority:** Medium

**Test Data:** Password containing spaces only.

**Steps:**
1. Enter a valid username.
2. Enter spaces in the password field.
3. Click Login.

**Expected Result:** Authentication succeeds only if those spaces are genuinely part of the account's correct password; otherwise, login is rejected.

**Status:** Not Executed

## TC015 — Verify Leading and Trailing Spaces

**Technique:** Error Guessing  
**Priority:** Medium

**Steps:**
1. Enter a valid username with leading spaces.
2. Submit the form.
3. Repeat with trailing spaces.
4. Test the password with spaces only if relevant to the account's actual password.

**Expected Result:** Username whitespace handling follows documented rules. Password contents are not silently changed in ways that violate the application's authentication design.

**Status:** Not Executed

---

# 8. Equivalence Partitioning

Equivalence Partitioning divides input values into groups expected to behave similarly. Use the application's actual validation rules to define the groups.

## TC016 — Valid Username Partition

**Technique:** Equivalence Partitioning  
**Priority:** High

**Test Data:** A correctly formatted, registered username.

**Steps:**
1. Enter a username from the valid partition.
2. Enter the correct password.
3. Submit the form.

**Expected Result:** Authentication succeeds for valid credentials.

**Status:** Not Executed

## TC017 — Invalid Username Partition

**Technique:** Equivalence Partitioning  
**Priority:** High

**Test Data:** A syntactically invalid username or an unregistered username.

**Steps:**
1. Enter an input from an invalid username partition.
2. Enter a password.
3. Submit the form.

**Expected Result:** The application rejects invalid input or credentials with appropriate feedback.

**Status:** Not Executed

## TC018 — Valid Password Partition

**Technique:** Equivalence Partitioning  
**Priority:** High

**Test Data:** The exact correct password for the test account.

**Steps:**
1. Enter a valid username.
2. Enter the correct password.
3. Submit the form.

**Expected Result:** Login succeeds.

**Status:** Not Executed

## TC019 — Invalid Password Partition

**Technique:** Equivalence Partitioning  
**Priority:** High

**Test Data:** An incorrect password.

**Steps:**
1. Enter a valid username.
2. Enter an incorrect password.
3. Submit the form.

**Expected Result:** Login is rejected.

**Status:** Not Executed

---

# 9. Boundary Value Analysis

Boundary Value Analysis focuses on values at, immediately below, and immediately above defined limits.

**Important:** The following example assumes a username length limit of 8–20 characters. This is a practice assumption, not a universal login requirement. Replace it with the application's documented limits before execution.

## TC020 — Username Length Below Minimum

**Technique:** Boundary Value Analysis  
**Priority:** Medium

**Test Data:** 7 characters, assuming a minimum length of 8.

**Steps:**
1. Enter a 7-character username.
2. Enter a password.
3. Submit the form.

**Expected Result:** If the application enforces an 8-character minimum, the input is rejected with appropriate validation.

**Status:** Not Executed

## TC021 — Username Length at Minimum

**Technique:** Boundary Value Analysis  
**Priority:** Medium

**Test Data:** 8 characters.

**Steps:**
1. Enter an 8-character username.
2. Submit using appropriate test credentials.

**Expected Result:** The input passes the length check if all other requirements are met. Authentication still depends on whether the account and password are valid.

**Status:** Not Executed

## TC022 — Username Length Above Minimum

**Technique:** Boundary Value Analysis  
**Priority:** Low

**Test Data:** 9 characters.

**Steps:**
1. Enter a 9-character username.
2. Submit the form with suitable test credentials.

**Expected Result:** The value passes the assumed minimum-length check.

**Status:** Not Executed

## TC023 — Username Length at Maximum

**Technique:** Boundary Value Analysis  
**Priority:** Medium

**Test Data:** 20 characters.

**Steps:**
1. Enter a 20-character username.
2. Submit the form.

**Expected Result:** The input is accepted by the length validator if it satisfies the remaining rules.

**Status:** Not Executed

## TC024 — Username Length Above Maximum

**Technique:** Boundary Value Analysis  
**Priority:** Medium

**Test Data:** 21 characters.

**Steps:**
1. Enter a 21-character username.
2. Submit the form.

**Expected Result:** The application handles the value according to its documented maximum length, without crashing or truncating it silently.

**Status:** Not Executed

## TC025 — Empty and One-Character Username

**Technique:** Boundary Value Analysis  
**Priority:** Medium

**Test Data:** Empty input and a single-character username.

**Steps:**
1. Submit with an empty username.
2. Repeat with a single-character username.
3. Record each result.

**Expected Result:** Empty input is rejected. A one-character username is handled according to the documented validation rules.

**Status:** Not Executed

---

# 10. Decision Table Testing

Decision Table Testing checks combinations of conditions and resulting actions.

## TC026 — Credential Combination Validation

**Technique:** Decision Table Testing  
**Priority:** High

**Conditions:**
- Username valid?
- Password valid?
- Required fields populated?

| Rule | Username | Password | Fields populated | Expected action |
|---|---|---|---|---|
| R1 | Valid | Valid | Yes | Authenticate successfully |
| R2 | Valid | Invalid | Yes | Reject login |
| R3 | Invalid | Valid | Yes | Reject login |
| R4 | Invalid | Invalid | Yes | Reject login |
| R5 | Empty | Any | No | Show validation |
| R6 | Any | Empty | No | Show validation |
| R7 | Empty | Empty | No | Show required-field validation |

**Steps:**
1. Prepare test data for each rule.
2. Execute the corresponding login attempt.
3. Record the actual response.
4. Compare it with the expected action.

**Expected Result:** Each input combination produces the documented outcome.

**Status:** Not Executed

---

# 11. State Transition Testing

State Transition Testing verifies behavior when an application moves between states. Execute lockout cases only if the application supports account lockout.

## TC027 — Successful Login State Transition

**Technique:** State Transition Testing  
**Priority:** High

**Steps:**
1. Start from the logged-out state.
2. Enter valid credentials.
3. Submit the form.
4. Observe the resulting state.

**Expected Result:** The user moves from logged out to authenticated.

**Status:** Not Executed

## TC028 — Failed Login State Transition

**Technique:** State Transition Testing  
**Priority:** High

**Steps:**
1. Start from the logged-out state.
2. Enter an incorrect password.
3. Submit the form.
4. Observe the resulting state.

**Expected Result:** The user remains unauthenticated and receives appropriate feedback.

**Status:** Not Executed

## TC029 — Account Lockout After Repeated Failures

**Technique:** State Transition Testing  
**Priority:** High, if supported

**Precondition:** The account lockout threshold and reset behavior are documented.

**Steps:**
1. Start with an unlocked test account.
2. Submit incorrect credentials repeatedly up to the configured threshold.
3. Observe each response.
4. Attempt another login.
5. Verify the documented unlock or recovery procedure.

**Expected Result:** The application follows its configured failed-login policy and provides safe recovery behavior.

**Status:** Not Executed

## TC030 — Session Expiry

**Technique:** State Transition Testing  
**Priority:** High, if supported

**Steps:**
1. Log in successfully.
2. Remain inactive for the configured session timeout period.
3. Attempt to access a protected page.
4. Observe the response.

**Expected Result:** An expired session cannot access protected resources and the user is prompted to authenticate again as required.

**Status:** Not Executed

## TC031 — Browser Back After Logout

**Technique:** State Transition Testing  
**Priority:** High

**Steps:**
1. Log in successfully.
2. Open a protected page.
3. Log out.
4. Press the browser Back button.
5. Attempt to interact with the previous page.

**Expected Result:** Protected information must not become accessible through a stale page or cached authenticated state.

**Status:** Not Executed

---

# 12. Error Guessing and Exploratory Testing

Error Guessing uses experience to anticipate common mistakes. Exploratory Testing involves learning, designing, and executing tests while investigating the application.

## TC032 — Extremely Long Input

**Technique:** Error Guessing  
**Priority:** Medium

**Steps:**
1. Enter a very long username.
2. Enter a very long password.
3. Submit the form.
4. Observe validation, page responsiveness, and error handling.

**Expected Result:** The application handles oversized input safely, applies documented limits, and does not crash.

**Status:** Not Executed

## TC033 — Special Characters in Username

**Technique:** Error Guessing  
**Priority:** Medium

**Test Data:** Characters such as `@`, `.`, `_`, `-`, and other characters relevant to the username format.

**Steps:**
1. Enter a username containing permitted special characters.
2. Submit using suitable test credentials.
3. Repeat with unsupported characters.

**Expected Result:** Permitted characters follow the application's rules; invalid characters are handled safely.

**Status:** Not Executed

## TC034 — Rapid Repeated Login Clicks

**Technique:** Error Guessing  
**Priority:** Medium

**Steps:**
1. Enter valid credentials.
2. Click Login repeatedly in quick succession.
3. Observe the application's response.

**Expected Result:** The application handles repeated submissions consistently without duplicate actions or an unstable interface.

**Status:** Not Executed

## TC035 — Refresh During Login

**Technique:** Exploratory Testing  
**Priority:** Medium

**Steps:**
1. Enter valid credentials.
2. Submit the login form.
3. Refresh the page during or immediately after the response.
4. Observe the final state.

**Expected Result:** The application reaches a consistent state and does not expose credentials or create unexpected authenticated sessions.

**Status:** Not Executed

## TC036 — Network Interruption During Login

**Technique:** Exploratory Testing  
**Priority:** Medium

**Steps:**
1. Open the login page.
2. Enter valid test credentials.
3. Simulate a network interruption using browser developer tools or an approved test environment.
4. Submit the form.
5. Restore the connection and retry.

**Expected Result:** The application handles the failure gracefully, provides appropriate feedback, and allows a safe retry.

**Status:** Not Executed

## TC037 — Error Message Consistency

**Technique:** Exploratory Testing  
**Priority:** Medium

**Steps:**
1. Submit an invalid username.
2. Submit a valid username with an incorrect password.
3. Compare the error messages.
4. Check whether the messages reveal unnecessary account information.

**Expected Result:** Messages are clear and secure, consistent with the application's authentication policy.

**Status:** Not Executed

---

# 13. Security Testing

Perform security checks only on an application you own or have explicit permission to test. These manual checks do not replace a professional security assessment.

## TC038 — Password Masking

**Technique:** Security / UI Testing  
**Priority:** High

**Steps:**
1. Open the login page.
2. Enter a password.
3. Observe how the password is displayed.

**Expected Result:** The password is masked by default.

**Status:** Not Executed

## TC039 — Show/Hide Password Control

**Technique:** Functional / Security Testing  
**Priority:** Medium, if supported

**Steps:**
1. Enter a password.
2. Click the Show Password control.
3. Verify the displayed value.
4. Click Hide Password.
5. Verify the value is masked again.

**Expected Result:** The control toggles visibility correctly and does not change the entered password.

**Status:** Not Executed

## TC040 — SQL Injection Input Handling

**Technique:** Security Testing  
**Priority:** High

**Test Data:** In an authorized test environment, use a harmless input such as `' OR '1'='1` in a username field.

**Steps:**
1. Open the test login page.
2. Enter the test string in the username field.
3. Enter a non-sensitive test password.
4. Submit the form.
5. Observe the response and application logs if authorized.

**Expected Result:** The input does not bypass authentication or expose database errors. Authentication remains secure through appropriate input handling and parameterized queries.

**Status:** Not Executed

## TC041 — Script Injection Input Handling

**Technique:** Security Testing  
**Priority:** High

**Test Data:** A harmless script-like string such as `<script>alert(1)</script>` in an authorized test environment.

**Steps:**
1. Enter the test string into the username field.
2. Submit the form.
3. Observe whether the value is rendered as executable content or safely handled.
4. Check error messages and relevant output.

**Expected Result:** User input is safely handled and not executed as script.

**Status:** Not Executed

## TC042 — Password Exposure in URL

**Technique:** Security Testing  
**Priority:** High

**Steps:**
1. Enter test credentials.
2. Submit the login form.
3. Inspect the browser address bar and request method using developer tools.
4. Check that the password is not included in the URL or query string.

**Expected Result:** Passwords are not exposed in URLs, query parameters, or navigation history.

**Status:** Not Executed

## TC043 — Protected Page Access Without Login

**Technique:** Security Testing  
**Priority:** High

**Steps:**
1. Log out of the application.
2. Open a protected page using its direct URL.
3. Observe the response.
4. Repeat in a fresh browser session if appropriate.

**Expected Result:** Unauthenticated users cannot access protected information.

**Status:** Not Executed

## TC044 — Sensitive Information in Error Messages

**Technique:** Security Testing  
**Priority:** High

**Steps:**
1. Submit invalid credentials.
2. Observe the error message.
3. Check for passwords, stack traces, internal paths, database details, or other sensitive information.

**Expected Result:** Error messages do not disclose secrets or unnecessary internal implementation details.

**Status:** Not Executed

---

# 14. Usability and Accessibility Testing

## TC045 — Keyboard Navigation

**Technique:** Usability / Accessibility Testing  
**Priority:** Medium

**Steps:**
1. Open the login page.
2. Use Tab to navigate between controls.
3. Use Shift+Tab to navigate backwards.
4. Verify visible focus indicators.
5. Submit using the keyboard if supported.

**Expected Result:** Interactive elements can be reached and operated using the keyboard, with a logical focus order.

**Status:** Not Executed

## TC046 — Field Labels and Error Messages

**Technique:** Usability / Accessibility Testing  
**Priority:** Medium

**Steps:**
1. Inspect the username and password labels.
2. Submit the form with missing fields.
3. Observe whether errors identify the relevant fields.
4. Check whether errors can be understood without relying on color alone.

**Expected Result:** Inputs have understandable labels and validation messages identify the problem clearly.

**Status:** Not Executed

## TC047 — Password Field Copy/Paste Behavior

**Technique:** Usability / Security Testing  
**Priority:** Low

**Steps:**
1. Enter a password in the password field.
2. Check the application's documented copy/paste behavior.
3. Test password-manager autofill if supported.

**Expected Result:** Behavior follows the application's requirements and supports secure, accessible password entry.

**Status:** Not Executed

## TC048 — Login Page Layout and Readability

**Technique:** UI Testing  
**Priority:** Medium

**Steps:**
1. Open the login page.
2. Inspect labels, text, buttons, spacing, and alignment.
3. Check whether validation messages overlap other elements.
4. Verify that the Login button is visible and understandable.

**Expected Result:** The page is readable, usable, and free from obvious layout defects.

**Status:** Not Executed

---

# 15. Compatibility and Responsive Testing

## TC049 — Cross-Browser Login

**Technique:** Compatibility Testing  
**Priority:** Medium

**Browsers:** Supported versions of Chrome, Firefox, and Edge.

**Steps:**
1. Open the application in each supported browser.
2. Execute one valid login.
3. Execute one invalid login.
4. Compare layout, validation, and navigation.

**Expected Result:** Login behavior is consistent across supported browsers.

**Status:** Not Executed

## TC050 — Responsive Layout

**Technique:** Compatibility / Responsive UI Testing  
**Priority:** Medium

**Test Viewports:** Example widths of 320 px, 375 px, 768 px, and 1024 px.

**Steps:**
1. Open the login page.
2. Resize the viewport to each test width.
3. Inspect the username field, password field, button, and messages.
4. Attempt to complete a login at each supported viewport.

**Expected Result:** The page remains usable without unintended overlap, clipping, or inaccessible controls.

**Status:** Not Executed

## TC051 — Mobile Keyboard and Input Behavior

**Technique:** Compatibility Testing  
**Priority:** Medium

**Steps:**
1. Open the application on a supported mobile device or mobile browser.
2. Focus the username field.
3. Observe the keyboard behavior.
4. Move to the password field.
5. Submit the form and inspect the response.

**Expected Result:** Input controls remain accessible and the page behaves according to mobile requirements.

**Status:** Not Executed

---

# 16. Performance Observations

Manual checks can identify obvious delays but do not replace load or stress testing.

## TC052 — Login Response Time Observation

**Technique:** Basic Performance Testing  
**Priority:** Medium

**Precondition:** The expected response-time requirement is known.

**Steps:**
1. Open the application under normal test conditions.
2. Submit valid credentials.
3. Record the elapsed time until the expected response.
4. Repeat several times.
5. Compare the measurements with the documented requirement.

**Expected Result:** Response time meets the defined requirement under the tested conditions.

**Status:** Not Executed

## TC053 — Login Page Load Observation

**Technique:** Basic Performance Testing  
**Priority:** Low

**Steps:**
1. Open the login page in the supported browser.
2. Record the time until the form becomes usable.
3. Repeat under the same network conditions.
4. Compare the results with the documented performance requirement.

**Expected Result:** The page becomes usable within the specified performance target.

**Status:** Not Executed

---

# 17. Retesting and Regression Testing

## TC054 — Retest a Fixed Login Defect

**Technique:** Retesting  
**Priority:** High, when a defect is fixed

**Precondition:** A defect has been reported, fixed, and made available in the test environment.

**Steps:**
1. Review the defect's reproduction steps.
2. Execute the original failing test.
3. Compare actual behavior with expected behavior.
4. Record the result.

**Expected Result:** The original defect no longer occurs.

**Status:** Not Executed

## TC055 — Regression Test Existing Login Behavior

**Technique:** Regression Testing  
**Priority:** High, after a relevant change

**Steps:**
1. Execute a valid login test.
2. Execute an invalid-password test.
3. Execute empty-field validation tests.
4. Check logout and protected-page behavior.
5. Compare results against the established baseline.

**Expected Result:** Existing login functionality continues to work after the change.

**Status:** Not Executed

---

# 18. Test Execution Record

Update this section only after executing the test cases against an actual application.

| Metric | Value |
|---|---|
| Total designed test cases | 55 |
| Executed | 0 initially |
| Passed | 0 initially |
| Failed | 0 initially |
| Blocked | 0 initially |
| Not Executed | 55 initially |

## Execution Status Definitions

- **Pass:** Actual result matches the expected result.
- **Fail:** Actual result differs from the expected result.
- **Blocked:** Execution cannot proceed because a dependency or environment is unavailable.
- **Not Executed:** The test has not yet been run.

A failed test does not automatically prove a product defect. Investigate the result and document the defect when the evidence confirms a deviation from requirements.

# 19. Defect Report Template

Use this format only when an issue is observed and reproducible.

**Defect ID:** To be assigned  
**Defect Title:** Short description of the issue  
**Related Test Case ID:** TC___  
**Environment:** Browser, version, operating system, application build  
**Severity:** Based on business and technical impact  
**Priority:** Based on urgency and business needs  
**Precondition:** Required setup  
**Steps to Reproduce:**
1. Step one
2. Step two
3. Step three

**Expected Result:** What should happen  
**Actual Result:** What actually happened  
**Evidence:** Screenshot, logs, or other relevant proof  
**Status:** New / Assigned / Fixed / Retest / Closed

# 20. Testing Techniques Covered



 Positive Testing ----  TC001, TC006, TC016, TC018 
 Negative Testing --  TC002–TC004, TC010–TC014 
 Equivalence Partitioning -- TC016–TC019 
 Boundary Value Analysis --- TC020–TC025 
 Decision Table Testing -- TC026 
 State Transition Testing --- TC027–TC031 
 Error Guessing ----- TC013, TC015, TC032–TC034 
 Exploratory Testing  ---- TC035–TC037 
 Security Testing ----- TC038–TC044 
 Usability / Accessibility Testing --- TC045–TC048 
 Compatibility Testing ----- TC049–TC051 
 Basic Performance Testing ------- TC052–TC053 
 Retesting  --- TC054 
 Regression Testing -------  TC055 

**Important limitation:** This suite covers major applicable manual test design techniques, not every testing technique in software testing. Pairwise testing, cause-effect graphing, use-case testing, API testing, database testing, and automation testing may be added when the application and requirements support them.

# 21. Final Project Outcome

This project demonstrates the preparation of a structured manual testing suite for login functionality. It includes functional scenarios, negative cases, input validation, major black-box test design techniques, security observations, usability, compatibility, and execution documentation.

Final execution results, defect counts, and pass/fail metrics must be added only after testing has actually been performed.

