# Bug Report Samples - OrangeHRM Login Module

This document displays a sample of how QA Engineers report defects in bug tracking systems (like Jira). A professional bug report ensures developers can reproduce the issue easily.

---

## BUG-101: Error message "Invalid credentials" does not disappear after correcting credentials

* **Severity**: Medium
* **Priority**: High
* **Status**: Open
* **Reporter**: QA Tester (Fresher)
* **Environment**: 
  - **URL**: `https://opensource-demo.orangehrmlive.com/web/index.php/auth/login`
  - **Browser**: Google Chrome (v125.0)
  - **OS**: Windows 11

### Description
If a user inputs invalid credentials, the error banner displaying "Invalid credentials" appears correctly. However, if the user modifies the text fields to enter valid credentials, the error banner persists on screen instead of disappearing dynamically on input change.

### Steps to Reproduce
1. Navigate to the OrangeHRM Login Page.
2. Enter username `InvalidAdmin` and password `wrongPassword`.
3. Click the **Login** button.
4. Verify that the "Invalid credentials" error banner is displayed.
5. Without reloading the page, type `Admin` into the Username field and `admin123` in the Password field.
6. Observe the error message banner.

### Expected Result
The "Invalid credentials" error banner should disappear or fade out as soon as the user starts typing/editing inside either the Username or Password input fields.

### Actual Result
The "Invalid credentials" error banner remains visible on screen, even while the user is typing their corrected credentials. It only disappears when the user submits the form again.

---

## BUG-102: Missing validation error message when Username is blank on Edge Browser

* **Severity**: High
* **Priority**: High
* **Status**: Open
* **Reporter**: QA Tester (Fresher)
* **Environment**:
  - **URL**: `https://opensource-demo.orangehrmlive.com/web/index.php/auth/login`
  - **Browser**: Microsoft Edge (v124.0)
  - **OS**: Windows 11

### Description
When submitting the login form with an empty Username field and a valid Password on Microsoft Edge browser, the login fails but the red `"Required"` validation message under the Username field is missing.

### Steps to Reproduce
1. Navigate to the OrangeHRM Login Page using MS Edge.
2. Leave the **Username** field blank.
3. Enter `admin123` in the **Password** field.
4. Click **Login**.

### Expected Result
The page remains on the login screen, and a red validation message `"Required"` is displayed directly below the Username field.

### Actual Result
The page remains on the login screen, but no visual text validation message is displayed to notify the user that the field is required. Only the text box border turns slightly grey.
