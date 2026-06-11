# Manual Test Cases & Scenarios - OrangeHRM Login Functionality

This document details the manual test scenarios and test cases designed for validating the OrangeHRM Login Page functionality. Creating this document is an industry-standard practice before writing automation test scripts.

---

## High-Level Test Scenarios

| Scenario ID | Scenario Description | Priority | Test Type |
| :--- | :--- | :--- | :--- |
| **TS_001** | Verify login functionality with valid username and password credentials. | High | Positive |
| **TS_002** | Verify login failure and error messages with invalid login credentials. | High | Negative |
| **TS_003** | Verify form validation messages when login is attempted with blank/empty Username field. | Medium | Negative |
| **TS_004** | Verify form validation messages when login is attempted with blank/empty Password field. | Medium | Negative |

---

## Detailed Test Cases

### TC_001: Valid Login Verification
* **Scenario Link**: TS_001
* **Test Case Description**: Verify that a user is successfully logged in and redirected to the Dashboard page upon entering a valid username and password.
* **Preconditions**: User has navigated to the OrangeHRM Login Page.

**Execution Steps**:
1. Enter `Admin` in the **Username** text field.
2. Enter `admin123` in the **Password** text field.
3. Click the **Login** button.

**Test Data**:
* Username: `Admin`
* Password: `admin123`

**Expected Result**:
* User should be successfully authenticated.
* Page should redirect to the Dashboard page (URL should contain `/dashboard/index`).
* The heading text `"Dashboard"` should be visible at the top left of the navbar.

---

### TC_002: Invalid Login Verification
* **Scenario Link**: TS_002
* **Test Case Description**: Verify that a user is not logged in and sees a proper error message when using invalid username or password credentials.
* **Preconditions**: User has navigated to the OrangeHRM Login Page.

**Execution Steps**:
1. Enter `InvalidUser` in the **Username** text field.
2. Enter `InvalidPassword123` in the **Password** text field.
3. Click the **Login** button.

**Test Data**:
* Username: `InvalidUser`
* Password: `InvalidPassword123`

**Expected Result**:
* Login must fail, and user must remain on the login page.
* An error message pop-up showing `"Invalid credentials"` must be displayed.

---

### TC_003: Empty Username Validation
* **Scenario Link**: TS_003
* **Test Case Description**: Verify that a validation message appears below the Username input box when it is left empty and the user clicks Login.
* **Preconditions**: User has navigated to the OrangeHRM Login Page.

**Execution Steps**:
1. Leave the **Username** text field blank.
2. Enter `admin123` in the **Password** text field.
3. Click the **Login** button.

**Test Data**:
* Username: `""` (Empty)
* Password: `admin123`

**Expected Result**:
* Login must fail.
* A validation message `"Required"` must display directly below the **Username** field in red text.

---

### TC_004: Empty Password Validation
* **Scenario Link**: TS_004
* **Test Case Description**: Verify that a validation message appears below the Password input box when it is left empty and the user clicks Login.
* **Preconditions**: User has navigated to the OrangeHRM Login Page.

**Execution Steps**:
1. Enter `Admin` in the **Username** text field.
2. Leave the **Password** text field blank.
3. Click the **Login** button.

**Test Data**:
* Username: `Admin`
* Password: `""` (Empty)

**Expected Result**:
* Login must fail.
* A validation message `"Required"` must display directly below the **Password** field in red text.
