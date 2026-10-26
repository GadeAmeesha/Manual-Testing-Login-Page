# Login Page Manual Testing — Test Scenarios

**Objective:** To identify the major functional and non-functional testing scenarios for a login page.

## Test Scenarios

**TS001 — Verify login using valid credentials**  
Testing Type: Functional | Priority: High

**TS002 — Verify login using an invalid username**  
Testing Type: Negative | Priority: High

**TS003 — Verify login using an incorrect password**  
Testing Type: Negative | Priority: High

**TS004 — Verify login when both credentials are invalid**  
Testing Type: Negative | Priority: High

**TS005 — Verify login with both fields empty**  
Testing Type: Validation | Priority: High

**TS006 — Verify login with username empty**  
Testing Type: Validation | Priority: High

**TS007 — Verify login with password empty**  
Testing Type: Validation | Priority: High

**TS008 — Verify username whitespace handling**  
Testing Type: Negative | Priority: Medium

**TS009 — Verify username case-sensitivity rules**  
Testing Type: Functional | Priority: Medium

**TS010 — Verify password case sensitivity**  
Testing Type: Functional | Priority: High

**TS011 — Verify Login button functionality**  
Testing Type: Functional | Priority: High

**TS012 — Verify Enter key submission**  
Testing Type: Usability | Priority: Medium

**TS013 — Verify password masking**  
Testing Type: Security/UI | Priority: High

**TS014 — Verify show/hide password control, if available**  
Testing Type: Functional | Priority: Medium

**TS015 — Verify username minimum length**  
Testing Type: Boundary Value Analysis | Priority: Medium

**TS016 — Verify username maximum length**  
Testing Type: Boundary Value Analysis | Priority: Medium

**TS017 — Verify input just below minimum length**  
Testing Type: Boundary Value Analysis | Priority: Medium

**TS018 — Verify input just above maximum length**  
Testing Type: Boundary Value Analysis | Priority: Medium

**TS019 — Verify valid and invalid input partitions**  
Testing Type: Equivalence Partitioning | Priority: High

**TS020 — Verify combinations of valid and invalid credentials**  
Testing Type: Decision Table | Priority: High

**TS021 — Verify successful login state transition**  
Testing Type: State Transition | Priority: High

**TS022 — Verify failed login state transition**  
Testing Type: State Transition | Priority: High

**TS023 — Verify account lockout rules, if supported**  
Testing Type: State Transition/Security | Priority: High

**TS024 — Verify session expiration, if supported**  
Testing Type: State Transition/Security | Priority: High

**TS025 — Verify logout behavior**  
Testing Type: Functional/Security | Priority: High

**TS026 — Verify protected page access without login**  
Testing Type: Security | Priority: High

**TS027 — Verify browser Back behavior after logout**  
Testing Type: Security | Priority: High

**TS028 — Verify long input handling**  
Testing Type: Error Guessing | Priority: Medium

**TS029 — Verify special character handling**  
Testing Type: Negative | Priority: Medium

**TS030 — Verify rapid repeated submissions**  
Testing Type: Error Guessing | Priority: Medium

**TS031 — Verify SQL injection input handling**  
Testing Type: Security | Priority: High

**TS032 — Verify script-like input handling**  
Testing Type: Security | Priority: High

**TS033 — Verify password is not exposed in the URL**  
Testing Type: Security | Priority: High

**TS034 — Verify error messages do not reveal sensitive details**  
Testing Type: Security | Priority: High

**TS035 — Verify keyboard navigation**  
Testing Type: Accessibility | Priority: Medium

**TS036 — Verify labels and validation messages**  
Testing Type: Accessibility | Priority: Medium

**TS037 — Verify login page layout and readability**  
Testing Type: UI/Usability | Priority: Medium

**TS038 — Verify login functionality across supported browsers**  
Testing Type: Compatibility | Priority: Medium

**TS039 — Verify responsive layout on supported screen sizes**  
Testing Type: Compatibility | Priority: Medium

**TS040 — Verify login behavior on supported mobile devices**  
Testing Type: Compatibility | Priority: Medium

**TS041 — Observe login response time**  
Testing Type: Performance | Priority: Medium

**TS042 — Observe login page load time**  
Testing Type: Performance | Priority: Low

**TS043 — Retest a fixed defect**  
Testing Type: Retesting | Priority: High

**TS044 — Run regression tests after a relevant change**  
Testing Type: Regression | Priority: High

## Entry Criteria

- The test environment is available.
- Login page requirements are available.
- Test account credentials are provided where required.
- Supported browsers and devices are identified.

## Exit Criteria

- Planned scenarios are executed, or their blocked status is documented.
- Failed scenarios are investigated.
- Confirmed defects are documented with evidence.
- The test execution summary is updated.
- Remaining risks and limitations are documented.

## Notes

- Validate scenarios against the actual application requirements.
- Test username length boundaries according to the application's specified rules.
- Test account lockout and session expiration only if these features are supported.
- Perform security testing only in an authorized test environment.
- Do not report scenarios as passed or failed until they have actually been executed.

**Current Status:** Test scenarios documented. Execution pending.
