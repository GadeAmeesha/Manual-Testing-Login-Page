# Login Page Manual Testing — Test Data

## 1. Objective

The objective of this document is to define sample test data for validating login page functionality, input validation, negative scenarios, boundary values, and security-related behavior.

## 2. Test Data Table

### A. Functional and Negative Testing

**TD001 — Valid Credentials**

- Username: `ameesha_test`
- Password: `ValidPass@123`
- Expected Result: Login should succeed when these credentials belong to a valid test account.

**TD002 — Invalid Username**

- Username: `invalid_user_999`
- Password: `ValidPass@123`
- Expected Result: Login should fail with an appropriate error message.

**TD003 — Incorrect Password**

- Username: `ameesha_test`
- Password: `WrongPass@123`
- Expected Result: Login should fail.

**TD004 — Both Credentials Invalid**

- Username: `unknown_user`
- Password: `WrongPass@456`
- Expected Result: Login should fail.

**TD005 — Both Fields Empty**

- Username: Leave empty
- Password: Leave empty
- Expected Result: Required-field validation should appear, according to the application requirements.

**TD006 — Username Empty**

- Username: Leave empty
- Password: `ValidPass@123`
- Expected Result: Username validation should appear.

**TD007 — Password Empty**

- Username: `ameesha_test`
- Password: Leave empty
- Expected Result: Password validation should appear.

### B. Input Validation Testing

**TD008 — Username With Leading or Trailing Spaces**

- Username: `  ameesha_test  `
- Password: `ValidPass@123`
- Expected Result: Whitespace should be handled according to the specified requirements.

**TD009 — Username With Different Letter Case**

- Username: `AMEESHA_TEST`
- Password: `ValidPass@123`
- Expected Result: The result should follow the application's username case-sensitivity rules.

**TD010 — Password With Different Letter Case**

- Username: `ameesha_test`
- Password: `validpass@123`
- Expected Result: Login should fail if the password is case-sensitive and the supplied password does not match.

**TD011 — Username With Special Characters**

- Username: `ameesha@#$`
- Password: `ValidPass@123`
- Expected Result: The application should handle the input according to its validation rules without crashing.

**TD012 — Username With Numeric Characters**

- Username: `ameesha123`
- Password: `ValidPass@123`
- Expected Result: The application should accept or reject the username according to its defined rules.

**TD013 — Very Long Username**

- Username: A string containing 500 characters
- Password: `ValidPass@123`
- Expected Result: The application should handle long input safely and follow its length limits.

### C. Boundary Value Analysis

**Assumption:** These examples use a hypothetical username length of 8–20 characters. Replace these limits with the actual application requirements before execution.

**TD014 — Minimum Valid Length**

- Username: `user1234` (8 characters)
- Expected Result: Should satisfy the assumed minimum length rule.

**TD015 — Below Minimum Length**

- Username: `user123` (7 characters)
- Expected Result: Should be rejected if the minimum length rule applies at the login stage.

**TD016 — Maximum Valid Length**

- Username: `user12345678901234` (18 characters)
- Expected Result: Valid length under the assumed 8–20 character range.

**TD017 — Above Maximum Length**

- Username: `user1234567890123456789` (23 characters)
- Expected Result: Should be handled according to the application's maximum length rule.

### D. Security Testing Inputs

Use these inputs only in an application or test environment you are authorized to test.

**TD018 — SQL Injection Test String**

- Username: `' OR '1'='1`
- Password: `TestPass@123`
- Expected Result: Login must not be bypassed; input should be handled safely.

**TD019 — Script-Like Input**

- Username: `<script>alert(1)</script>`
- Password: `TestPass@123`
- Expected Result: Input should not execute as a script.

**TD020 — Password URL Exposure Check**

- Action: Submit login credentials and inspect the resulting URL.
- Expected Result: The password must not appear in the URL.

**TD021 — Repeated Invalid Login Attempts**

- Username: `ameesha_test`
- Password: `WrongPass@123`
- Action: Repeat failed login attempts within the permitted test environment.
- Expected Result: Behavior should match the application's documented security and lockout rules, if supported.

### E. Usability Testing Data

**TD022 — Keyboard Navigation**

- Action: Navigate between username, password, and Login controls using the keyboard.
- Expected Result: Controls should be reachable and usable in a logical order.

**TD023 — Password Masking**

- Action: Enter `ValidPass@123` into the password field.
- Expected Result: Password characters should be masked by default, unless the requirements specify otherwise.

**TD024 — Empty Input Error Messages**

- Username: Leave empty
- Password: Leave empty
- Expected Result: Validation messages should be understandable and associated with the relevant fields.

## 3. Test Data Handling Guidelines

- Use fictional usernames and dummy passwords in documentation.
- Never include real user passwords, production credentials, or confidential data.
- Use valid credentials only when a dedicated test account has been created.
- Confirm application-specific validation rules before execution.
- Do not mark a test as Passed or Failed until it has been executed.
- Record actual results and defects separately.

## 4. Execution Status

**Document Status:** Test data prepared.

**Execution Status:** Not Executed.

**Note:** The sample credentials in this document are illustrative only. They are not confirmed accounts and may not work in any real application.
