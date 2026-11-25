
# Login Page Manual Testing — Test Data

## 1. Project Information

| Parameter | Details |
|---|---|
| Project Name | Login Page Manual Testing |
| Testing Type | Manual Testing |
| Test Approach | Black-box Testing |
| Test Level | System Testing |
| Total Test Cases | 55 |
| Total Test Data Records | 45 |
| Test Data Status | Prepared |
| Result Verification | Pending |
| Author | Gade Ameesha |

---

## 2. Objective

The objective of this document is to define structured
test data for validating login functionality, authentication,
input validation, boundary conditions, security, usability,
compatibility, and error-handling behavior.

This document maintains traceability between test data
and corresponding manual test cases.

---

## 3. Test Data Categories

- Functional Testing
- Positive Testing
- Negative Testing
- Mandatory Field Validation
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table Testing
- State Transition Testing
- Error Guessing
- Exploratory Testing
- Security Testing
- Usability and Accessibility Testing
- Compatibility Testing
- Basic Performance Testing
- Retesting
- Regression Testing

---

## 4. Functional and Negative Testing

### TD001 — Valid Credentials

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Related Test Cases: TC001, TC007, TC008, TC016, TC018, TC027
- Expected Result: Login succeeds when the credentials belong to an active test account.
- Expected Behavior Classification: Positive
- Verification Status: Pending

### TD002 — Invalid Username

- Username: `invalid_user_999`
- Password: `ValidPass@123`
- Related Test Cases: TC002, TC017, TC037
- Expected Result: Login is rejected with an appropriate error message.
- Expected Behavior Classification: Negative
- Verification Status: Pending

### TD003 — Incorrect Password

- Username: `ameesha_test`
- Password: `WrongPass@123`
- Related Test Cases: TC003, TC019, TC028, TC037
- Expected Result: Authentication is rejected.
- Expected Behavior Classification: Negative
- Verification Status: Pending

### TD004 — Both Credentials Invalid

- Username: `unknown_user`
- Password: `WrongPass@456`
- Related Test Cases: TC004
- Expected Result: Login is rejected without exposing sensitive information.
- Expected Behavior Classification: Negative
- Verification Status: Pending

### TD005 — Both Fields Empty

- Username: Empty
- Password: Empty
- Related Test Cases: TC010
- Expected Result: Required-field validation is displayed.
- Expected Behavior Classification: Negative
- Verification Status: Pending

### TD006 — Username Empty

- Username: Empty
- Password: `ValidPass@123`
- Related Test Cases: TC011
- Expected Result: Username validation is displayed and login is prevented.
- Expected Behavior Classification: Negative
- Verification Status: Pending

### TD007 — Password Empty

- Username: `ameesha_test`
- Password: Empty
- Related Test Cases: TC012
- Expected Result: Password validation is displayed and login is prevented.
- Expected Behavior Classification: Negative
- Verification Status: Pending

---

## 5. Input Validation Testing

### TD008 — Username With Leading or Trailing Spaces

- Username: `  ameesha_test  `
- Password: `ValidPass@123`
- Related Test Cases: TC015
- Expected Result: Whitespace is handled according to documented requirements.
- Verification Status: Pending

### TD009 — Username With Different Letter Case

- Username: `AMEESHA_TEST`
- Password: `ValidPass@123`
- Related Test Cases: TC005
- Expected Result: Authentication follows the username case-sensitivity rules.
- Verification Status: Pending

### TD010 — Password With Different Letter Case

- Username: `ameesha_test`
- Password: `validpass@123`
- Related Test Cases: TC006
- Expected Result: Authentication is rejected when the password does not match.
- Verification Status: Pending

### TD011 — Username With Special Characters

- Username: `ameesha@#$`
- Password: `ValidPass@123`
- Related Test Cases: TC033
- Expected Result: Input is handled according to validation rules without crashing.
- Verification Status: Pending

### TD012 — Username With Numeric Characters

- Username: `ameesha123`
- Password: `ValidPass@123`
- Related Test Cases: TC016, TC017
- Expected Result: Input is accepted or rejected according to the username rules and account validity.
- Verification Status: Pending

### TD013 — Extremely Long Input

- Username: A string containing 500 characters
- Password: A string containing 500 characters
- Related Test Cases: TC032
- Expected Result: Oversized input is handled safely according to documented limits.
- Verification Status: Pending

---

## 6. Boundary Value Analysis

### Assumed Username Length

- Minimum Length: 8 characters
- Maximum Length: 20 characters

These limits are hypothetical practice requirements.
Actual application requirements must be confirmed
before execution.

### TD014 — Minimum Valid Length

- Username: `user1234`
- Length: 8 characters
- Related Test Cases: TC021
- Expected Result: Satisfies the assumed minimum length.
- Verification Status: Pending

### TD015 — Below Minimum Length

- Username: `user123`
- Length: 7 characters
- Related Test Cases: TC020
- Expected Result: Rejected if the minimum length rule applies.
- Verification Status: Pending

### TD016 — Maximum Valid Length

- Username: `user1234567890123456`
- Length: 20 characters
- Related Test Cases: TC023
- Expected Result: Satisfies the assumed maximum length.
- Verification Status: Pending

### TD017 — Above Maximum Length

- Username: `user12345678901234567`
- Length: 21 characters
- Related Test Cases: TC024
- Expected Result: Handled according to the maximum length rule.
- Verification Status: Pending

### Boundary Value Summary

| Boundary | Length | Test Data | Expected Length Validation |
|---|---:|---|---|
| Minimum - 1 | 7 | user123 | Invalid |
| Minimum | 8 | user1234 | Valid |
| Minimum + 1 | 9 | user12345 | Valid |
| Maximum - 1 | 19 | user123456789012345 | Valid |
| Maximum | 20 | user1234567890123456 | Valid |
| Maximum + 1 | 21 | user12345678901234567 | Invalid |

Note: Passing length validation does not guarantee
successful authentication. A registered account and
matching password are also required.

---

## 7. Security Testing Inputs

Security-related test data must be used only in an
owned or explicitly authorized testing environment.

### TD018 — SQL Injection Input Handling

- Test Data: Authorized SQL injection validation input
- Related Test Cases: TC040
- Expected Result: Authentication is not bypassed and database errors are not exposed.
- Verification Status: Pending

### TD019 — Script Injection Input Handling

- Test Data: Authorized script-like validation input
- Related Test Cases: TC041
- Expected Result: Input is safely handled and is not executed as script.
- Verification Status: Pending

### TD020 — Password URL Exposure Check

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Action: Submit the login form and inspect the URL.
- Related Test Cases: TC042
- Expected Result: Password does not appear in the URL or query parameters.
- Verification Status: Pending

### TD021 — Repeated Invalid Login Attempts

- Username: `ameesha_test`
- Password: `WrongPass@123`
- Attempt Count: As defined by the application requirements
- Related Test Cases: TC029
- Expected Result: Behavior follows the documented failed-login and lockout policy.
- Verification Status: Pending

---

## 8. Usability Testing Data

### TD022 — Keyboard Navigation

- Input Method: Keyboard
- Keys: Tab, Shift+Tab and Enter
- Related Test Cases: TC008, TC045
- Expected Result: Interactive controls are accessible in a logical order.
- Verification Status: Pending

### TD023 — Password Masking

- Password: `ValidPass@123`
- Related Test Cases: TC038
- Expected Result: Password characters are masked by default.
- Verification Status: Pending

### TD024 — Empty Input Error Messages

- Username: Empty
- Password: Empty
- Related Test Cases: TC046
- Expected Result: Validation messages clearly identify the relevant input problems.
- Verification Status: Pending

---

## 9. Additional Boundary and Whitespace Test Data

### TD025 — Above Minimum Length

- Username: `user12345`
- Length: 9 characters
- Related Test Cases: TC022
- Expected Result: Satisfies the assumed minimum length requirement.
- Verification Status: Pending

### TD026 — Below Maximum Length

- Username: `user123456789012345`
- Length: 19 characters
- Related Test Cases: Supplementary boundary coverage
- Expected Result: Satisfies the assumed username length range.
- Verification Status: Pending

### TD027 — Empty and Single-Character Username

- Username 1: Empty
- Username 2: `a`
- Length: 0 and 1 character
- Related Test Cases: TC025
- Expected Result: Empty input is rejected and single-character input follows documented rules.
- Verification Status: Pending

### TD028 — Username Containing Only Spaces

- Username: Three space characters
- Password: `ValidPass@123`
- Related Test Cases: TC013
- Expected Result: Invalid whitespace-only username does not authenticate.
- Verification Status: Pending

### TD029 — Password Containing Only Spaces

- Username: `ameesha_test`
- Password: Three space characters
- Related Test Cases: TC014
- Expected Result: Authentication is rejected unless the spaces are the actual registered password.
- Verification Status: Pending

---

## 10. State Transition and Session Testing Data

### TD030 — Logout and Re-login

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Initial State: Authenticated
- Action: Logout and log in again.
- Related Test Cases: TC009
- Expected Result: Logout ends the session and valid re-login succeeds.
- Verification Status: Pending

### TD031 — Session Timeout

- Initial State: Authenticated
- Inactivity Duration: Application-configured timeout
- Related Test Cases: TC030
- Expected Result: Expired sessions cannot access protected resources.
- Verification Status: Pending

### TD032 — Browser Back After Logout

- Initial State: Logged out after successful login
- Action: Press the browser Back button.
- Related Test Cases: TC031
- Expected Result: Protected information is not accessible through the previous session.
- Verification Status: Pending

### TD033 — Protected Page Direct Access

- Initial State: Unauthenticated
- Test Data: Authorized protected-page URL
- Related Test Cases: TC043
- Expected Result: Protected resources require authentication.
- Verification Status: Pending

---

## 11. Error Guessing and Exploratory Test Data

### TD034 — Rapid Login Button Clicks

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Action: Repeated clicks during form submission.
- Related Test Cases: TC034
- Expected Result: Application handles repeated submissions consistently.
- Verification Status: Pending

### TD035 — Page Refresh During Login

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Action: Refresh during or immediately after login.
- Related Test Cases: TC035
- Expected Result: Application reaches a consistent authentication state.
- Verification Status: Pending

### TD036 — Network Interruption

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Network Conditions: Online, Offline, Restored
- Related Test Cases: TC036
- Expected Result: Network failure is handled gracefully and safe retry is supported.
- Verification Status: Pending

### TD037 — Sensitive Information in Error Messages

- Username: `unknown_user`
- Password: `WrongPass@123`
- Related Test Cases: TC044
- Expected Result: Error messages do not expose passwords, stack traces or internal implementation details.
- Verification Status: Pending

---

## 12. Additional UI and Accessibility Test Data

### TD038 — Show and Hide Password

- Password: `ValidPass@123`
- Action: Toggle password visibility, if supported.
- Related Test Cases: TC039
- Expected Result: Password visibility changes without modifying the entered value.
- Verification Status: Pending

### TD039 — Password Copy/Paste and Autofill

- Password: `ValidPass@123`
- Input Methods: Manual entry, paste and supported password-manager autofill
- Related Test Cases: TC047
- Expected Result: Password input behavior follows application requirements.
- Verification Status: Pending

### TD040 — Login Page Layout

- UI Elements: Username field, password field, Login button and validation messages
- Related Test Cases: TC048
- Expected Result: Elements are readable, properly aligned and usable.
- Verification Status: Pending

---

## 13. Compatibility and Responsive Testing Data

### TD041 — Browser Compatibility

| Browser | Test Data | Expected Result |
|---|---|---|
| Google Chrome | Valid and invalid credentials | Consistent login behavior |
| Mozilla Firefox | Valid and invalid credentials | Consistent login behavior |
| Microsoft Edge | Valid and invalid credentials | Consistent login behavior |

- Related Test Cases: TC049
- Browser Versions: To be recorded during execution
- Verification Status: Pending

### TD042 — Responsive and Mobile Testing

| Device Category | Example Viewport |
|---|---:|
| Small Mobile | 320 px |
| Mobile | 375 px |
| Tablet | 768 px |
| Desktop | 1024 px |
| Large Desktop | 1920 px |

- Related Test Cases: TC050, TC051
- Test Data: Valid and invalid credentials
- Expected Result: Login controls remain accessible and usable without unintended clipping or overlap.
- Verification Status: Pending

---

## 14. Performance Testing Data

### TD043 — Login and Page Load Time

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Network Condition: Normal test network
- Related Test Cases: TC052, TC053
- Performance Target: As defined by the application requirements
- Expected Result: Response and page-load times meet the documented targets.
- Actual Measurements: Not recorded
- Verification Status: Pending

### Performance Measurement Template

| Measurement | Attempt 1 | Attempt 2 | Attempt 3 | Average |
|---|---|---|---|---|
| Login Response Time | Pending | Pending | Pending | Pending |
| Login Page Load Time | Pending | Pending | Pending | Pending |

---

## 15. Retesting and Regression Test Data

### TD044 — Defect Retesting

- Test Data: Original failing input values
- Precondition: A confirmed defect has been fixed.
- Related Test Cases: TC054
- Expected Result: The original defect no longer occurs.
- Verification Status: Pending applicable defect fix

### TD045 — Regression Testing

- Valid Username: `ameesha_test`
- Valid Password: `ValidPass@123`
- Invalid Password: `WrongPass@123`
- Additional Inputs: Empty username and empty password
- Related Test Cases: TC055
- Precondition: A relevant application change is available.
- Expected Result: Existing login functionality continues to work after the change.
- Verification Status: Pending applicable application change

---

## 16. Equivalence Partitioning Test Data

| Partition | Test Data | Expected Behavior | Test Case |
|---|---|---|---|
| Valid registered username | ameesha_test | Accepted with correct password | TC016 |
| Invalid username | invalid_user_999 | Rejected | TC017 |
| Valid password | ValidPass@123 | Authentication succeeds with matching account | TC018 |
| Invalid password | WrongPass@123 | Authentication rejected | TC019 |
| Empty username | Empty | Validation displayed | TC011 |
| Empty password | Empty | Validation displayed | TC012 |
| Whitespace-only username | Spaces | Invalid account not authenticated | TC013 |
| Whitespace-only password | Spaces | Rejected if incorrect | TC014 |

---

## 17. Decision Table Testing Data

Related Test Case: TC026

| Rule | Username | Password | Expected Result | Test Data ID |
|---|---|---|---|---|
| R1 | Valid | Valid | Login successful | TD001 |
| R2 | Valid | Invalid | Login rejected | TD003 |
| R3 | Invalid | Valid | Login rejected | TD002 |
| R4 | Invalid | Invalid | Login rejected | TD004 |
| R5 | Empty | Valid | Username validation | TD006 |
| R6 | Valid | Empty | Password validation | TD007 |
| R7 | Empty | Empty | Required-field validation | TD005 |

All rules require actual execution before their
results can be confirmed.

---

## 18. Test Data Traceability Matrix

| Test Case ID | Test Data ID |
|---|---|
| TC001 | TD001 |
| TC002 | TD002 |
| TC003 | TD003 |
| TC004 | TD004 |
| TC005 | TD009 |
| TC006 | TD010 |
| TC007 | TD001 |
| TC008 | TD001, TD022 |
| TC009 | TD030 |
| TC010 | TD005 |
| TC011 | TD006 |
| TC012 | TD007 |
| TC013 | TD028 |
| TC014 | TD029 |
| TC015 | TD008 |
| TC016 | TD001, TD012 |
| TC017 | TD002, TD012 |
| TC018 | TD001 |
| TC019 | TD003 |
| TC020 | TD015 |
| TC021 | TD014 |
| TC022 | TD025 |
| TC023 | TD016 |
| TC024 | TD017 |
| TC025 | TD027 |
| TC026 | TD001–TD007 |
| TC027 | TD001 |
| TC028 | TD003 |
| TC029 | TD021 |
| TC030 | TD031 |
| TC031 | TD032 |
| TC032 | TD013 |
| TC033 | TD011 |
| TC034 | TD034 |
| TC035 | TD035 |
| TC036 | TD036 |
| TC037 | TD002, TD003 |
| TC038 | TD023 |
| TC039 | TD038 |
| TC040 | TD018 |
| TC041 | TD019 |
| TC042 | TD020 |
| TC043 | TD033 |
| TC044 | TD037 |
| TC045 | TD022 |
| TC046 | TD024 |
| TC047 | TD039 |
| TC048 | TD040 |
| TC049 | TD041 |
| TC050 | TD042 |
| TC051 | TD042 |
| TC052 | TD043 |
| TC053 | TD043 |
| TC054 | TD044 |
| TC055 | TD045 |

TD026 provides supplementary maximum-boundary coverage
and can be included in an additional dedicated test case.

---

## 19. Test Data Summary

| Test Data Category | Records |
|---|---:|
| Functional and Negative Testing | 7 |
| Input Validation | 6 |
| Boundary Value Analysis | 4 |
| Security Testing | 4 |
| Usability Testing | 3 |
| Additional Boundary and Whitespace | 5 |
| State Transition and Session | 4 |
| Error Guessing and Exploratory | 4 |
| Additional UI and Accessibility | 3 |
| Compatibility and Responsive | 2 |
| Performance Testing | 1 |
| Retesting and Regression | 2 |
| **Total** | **45** |

---

## 20. Related Test Execution Summary

| Metric | Count |
|---|---:|
| Total Designed Test Cases | 55 |
| Total Test Data Records | 45 |
| Provisional Pass Classifications | 17 |
| Additional Verification Required | 38 |
| Confirmed Passed | Not Established |
| Confirmed Failed | Not Established |
| Confirmed Defects | Not Established |

The provisional classifications are based on expected
standard login behavior, not verified execution evidence.

Test data preparation does not establish that the
corresponding test cases have been executed successfully.

---

## 21. Test Data Handling Guidelines

- Use fictional usernames and dummy passwords.
- Never include production credentials or confidential information.
- Create dedicated test accounts before executing positive login tests.
- Confirm application-specific input validation requirements.
- Verify minimum and maximum input lengths.
- Perform security checks only with explicit authorization.
- Record browser and operating system information.
- Maintain consistent test data across related test cases.
- Capture actual results and supporting evidence.
- Investigate failed results before reporting defects.
- Update test data when application requirements change.
- Maintain traceability between test cases and test data.
- Never classify expected behavior as a confirmed execution result.

---

## 22. Test Data Completion Checklist

- [x] Valid credentials designed
- [x] Invalid credentials designed
- [x] Empty-field test data prepared
- [x] Boundary value test data prepared
- [x] Equivalence partitions identified
- [x] Decision table prepared
- [x] State transition data prepared
- [x] Security test data categories identified
- [x] UI and usability data prepared
- [x] Compatibility test data prepared
- [x] Performance measurement template prepared
- [x] Retesting and regression data prepared
- [x] Test case traceability matrix prepared
- [ ] Application-specific requirements confirmed
- [ ] Dedicated test account confirmed
- [ ] Actual execution results verified
- [ ] Supporting evidence collected

---

## 23. Final Document Status

- **Test Data Preparation:** Completed
- **Total Test Data Records:** 45
- **Related Test Cases:** 55
- **Test Case Mapping:** Completed
- **Application Requirements Verification:** Pending
- **Actual Execution Verification:** Pending
- **Final Test Closure:** Pending

---

## 24. Conclusion

This document provides structured test data for
validating login functionality using functional,
negative, boundary, security, usability, compatibility,
and performance-related testing approaches.

A total of 45 test data records have been prepared
to support the 55 documented manual test cases.

The test data traceability matrix improves coverage,
maintainability, consistency, and test execution planning.

All credentials are fictional examples. Application
requirements and account validity must be confirmed
before execution.

Final test results must be supported by actual
observations and relevant execution evidence.

---

## Author

**Gade Ameesha**

Software Developer | QA Engineer

- GitHub: https://github.com/GadeAmeesha
- LinkedIn: https://www.linkedin.com/in/gade-ameesha/
