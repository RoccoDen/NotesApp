# 📌 Feature: Signup (Two-Step Process)

## 🧩 General Description
Functionality that allows users to create an account to access LangEx through a two-step registration process:
1. Credential input (email, password, password confirmation)
2. Email verification and language profile completion

**Main use cases:**
- User enters email and password → receives verification email → clicks link → completes profile with languages and levels → account successfully created → redirect to main screen.
- Edge/error cases: already registered email, weak password, invalid or expired verification link, incomplete information in second step.

---

## 📱 Screens Involved

### 1. Signup - Step 1 (Credentials)
**Input fields:**
- `email`: text, mandatory, valid format
- `password`: password, mandatory, minimum 8 characters, max 20, use only few special chars _-!#
- `confirmPassword`: password, mandatory, must match `password`

**Available actions:**
- 'Signup' button → only active if all fields are valid
- "Go to Login" button → always active to switch to login screen
- 'Resend email' button → only visible when registration is completed and the message "Check your email to continue registration" is displayed. This button can be pressed a maximum of 5 times per email (after that an alert is displaied to the user).

**User flow:**
1. User opens Signup screen
2. Enters email, password and confirms password
3. Clicks Signup
4. If validation OK → verification email is sent
5. On-screen message: "Check your email to continue registration"

---

### 2. Email Verification
- Email sent to provided address with unique link
- Clicking link → opens "Completing profile" screen
- If link is invalid or expired → error message with option to resend

---

### 3. Signup - Step 2 (Language Profile Completion)
**Input fields:**
- `username`: text, mandatory (unique, alphanumeric only, case sensitive, allowed special characters: . _ -)
- `native languages[]`: multi-select popup with language search, **mandatory** 
- `languages[]`: multi-select popup with search, **mandatory**
- `levels[]`: popup for each selected language, **mandatory**, range `A1.1 - C2.2`

**Available actions:**
- "Complete Registration" button → only active if all mandatory fields are valid
- "X" icon to remove selected languages

**User flow:**
1. User accesses screen via verified email link
2. Selects native languages (at least one)
3. Selects languages to learn and corresponding levels
4. Clicks "Complete Registration"
5. If success → redirect to Home
6. If error → inline or popup message

---

## ✅ Logics and Validations

### Step 1
- Email: valid format, not already registered
- Password: minimum 8 characters, max 20, use only few special chars _-!#
- Confirm Password: must match Password
- Signup button disabled if fields are invalid
- Verification email sent via API → status and feedback handling

### Step 2
- At least one target language selected
- For each language, a level assigned
- Button disabled if data is incomplete or invalid
- Client and server-side validations
- Handling of expired/invalid links with dedicated message

---

## 🎨 UI

- Must follow UI guidelines defined in project documentation
- Suggestions:
  - Step indicator (e.g. 1/2, 2/2) in UI for process clarity
  - Accessible dropdowns and popups with keyboard and mobile support
  - Password input with visibility toggle (👁️)
  - Clear toast or alert after email sending
  - Loading icon during async requests

---

## 🔌 Addictions and Integrations

### Backend API:
- `POST /api/signup/request-verification`
  - Body: `{ email, password }`
  - Responses: `200 OK`, `409 Conflict`, `400 Bad Request`

- `GET /api/signup/verify?token=XYZ`
  - Verifies token and grants access to completion page

- `POST /api/signup/complete-profile`
  - Body: `{ token, username, nativeLanguages[], targetLanguages: [{ id, level }] }`
  - Responses: `201 Created`, `400 Bad Request`, `410 Link Expired`

---

## 🧪 Test to be Performed

### Step 1
- Valid input → verification email sent
- Invalid input → errors displayed correctly
- Already registered email → handled error

### Step 2
- Correct email link → opens completion screen
- Expired/invalid email link → error message
- Language and level selection → successful completion
- Data saving → redirect to Home

---

## 🌐 Technical Background

The feature must comply with:
- Technical and style details defined in project UI documentation
- Rules and conventions specified in project `README.md`