# Bug Report Template — Login Page Testing

## 1. Objective

This document provides a standard template for reporting, tracking, and documenting software defects identified during manual testing.

## 2. Bug Report Fields

- **Bug ID:** BUG-001
- **Bug Title:** [Short and clear description of the issue]
- **Project:** Login Page Manual Testing
- **Module:** Login
- **Reported By:** Tester
- **Reported Date:** [Enter actual date]
- **Environment:** [Browser, operating system, test environment]
- **Build Version:** [Enter version if available]
- **Severity:** [Critical / High / Medium / Low]
- **Priority:** [High / Medium / Low]
- **Status:** [New / Open / Assigned / Fixed / Retest / Closed / Reopened]
- **Test Case ID:** [Related test case ID]

## 3. Steps to Reproduce

1. Open the login page in the test environment.
2. Enter the required test data.
3. Click the Login button.
4. Observe the application behavior.

## 4. Expected Result

The application should behave according to the approved requirements and display the appropriate result or validation message.

## 5. Actual Result

[Record the actual behavior observed during test execution.]

## 6. Evidence

Attach a screenshot, screen recording, or relevant logs if available. Do not include real passwords, session tokens, or other sensitive information.

## 7. Sample Bug Report — Illustrative Example

**Bug ID:** BUG-001

**Bug Title:** Login form accepts submission when required fields are empty

**Module:** Login

**Severity:** Medium — illustrative; confirm based on impact.

**Priority:** High — illustrative; confirm with the project team.

**Status:** New — example only.

**Precondition:** Login page is available in an authorized test environment.

**Steps to Reproduce:**

1. Open the login page.
2. Leave the username field empty.
3. Leave the password field empty.
4. Click the Login button.

**Expected Result:**

The application should display appropriate required-field validation and should not authenticate the user.

**Actual Result:**

To be recorded after executing the test. No actual defect has been confirmed.

**Evidence:**

To be attached after execution, if applicable.

## 8. Severity vs Priority

- **Severity:** Measures the impact of the defect on the application.
- **Priority:** Indicates how urgently the defect should be fixed.

Example: A login failure affecting every user may be High or Critical severity and High priority, depending on business impact.

## 9. Bug Life Cycle

New → Assigned → Open/In Progress → Fixed → Retest → Closed

If the defect still occurs during retesting:

Retest Failed → Reopened → Fixed → Retest

Actual status names and transitions depend on the project workflow.

## 10. Important Notes

- Write clear, reproducible steps.
- Include expected and actual results.
- Attach evidence where possible.
- Use appropriate severity and priority based on impact and urgency.
- Never report an unverified issue as a confirmed defect.
- Do not include confidential production information.

**Document Status:** Template prepared.

**Execution Status:** No actual defect confirmed.
