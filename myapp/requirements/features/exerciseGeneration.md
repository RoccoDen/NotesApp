# 📘 Feature Documentation: Exercise Generation

## 🧩 General Description

This feature allows users to generate customized language exercises by filling out a detailed form. Upon clicking the "Copy Prompt" button, the app creates the AI-ready prompt and immediately copies it to the clipboard. The user then pastes it into their AI tool, receives a JSON-formatted exercise, and imports it back into the app for interactive use.

### Use Cases
- **Main scenario**: User completes the form, clicks "Copy Prompt" to generate and copy the prompt, uses an external AI tool to get the exercise, pastes the resulting JSON into the app, and completes the exercise generation.
- **Edge cases**:
  - Incomplete form (fields missing or invalid)
  - Copy failure due to system clipboard access issues
  - Incorrect or malformed JSON input
  - Navigation away before pasting the result. the screen which allows the user to paste the JSON (taken from the AI tool) can also be reached without having pre-filled the form to create the exercise (i.e. with a special button or from the general menu of the app where all functions will be present).

---

## 🖥️ Screens Involved

### 1. `CreateExerciseScreen`
- **Fields**:
  - `sourceLanguage` (Full-screen modal with scrollable list and top search bar, required, default from profile)
  - `targetLanguage` (Full-screen modal with scrollable list and top search bar, required, default from profile or manually selected)
  - `numQuestions` (Segmented Control - horizontal, required, from value 1 to 20, default value 10)
  - `userLevel` (Segmented Control - horizontal, required, A1.1–C2.2, default from profile)
  - `difficulty` (Segmented Control - horizontal, required; values: "Easy", "Medium" (default), "Hard". Used to define the complexity of the AI prompt)
  - `exerciseType` (Full-screen modal with scrollable list and top search bar, required; e.g., Multiple Choice, Character Selection, Free Text)
  - `topicDescription` (Text input, required, min 3, max 500 characters)
  - `theme` (Text input, optional)
- **Button**:
  - `Copy Prompt` (Disabled until all required fields are valid. On click, triggers prompt generation and copies it to clipboard)
- **Messages**:
  - Success: "Prompt generated and copied to clipboard. Paste it into your AI tool."
  - Error: "Please complete all required fields."

### 2. `PasteExerciseJSONScreen`
- **Element**:
  - JSON textarea (multiline input, required)
  - `Create Exercise` button (enabled if valid JSON structure)
- **Messages**:
  - Success: "Exercise loaded successfully."
  - Error: "Invalid format. Please check the JSON."

---

## 🧠 Logics and Validations

- All required fields must be filled and valid before enabling the `Copy Prompt` button
- `topicDescription`: min 3 characters, max 500
- `difficulty`: must be one of predefined values ("Easy", "Medium", "Hard")
- On "Copy Prompt":
  - Validate fields
  - Generate prompt using internal template
  - Copy to clipboard
  - Show confirmation message
- JSON pasted into the app must conform to the expected structure
- If JSON is valid:
  - Parse, store, and render the exercise interactively
  - Redirect user to the exercise screen
- If invalid:
  - Block submission and show error message

---

## 🎨 UI

- Must follow project’s ui docs
- Suggested components:
  - Full-screen modals for dropdown-like selections
  - Segmented controls for level and difficulty
  - Multiline input for topic and theme
  - Primary action button with loading indicator
  - Snackbar or toast messages for feedback

---

## 🔌 Addictions and Integrations

- External AI tools used manually by user (outside the app)
- Internal prompt template system
- Each exerciseType will contain the related info and also the required prompt to create that kind of exercise. The first 3 exerciseTypes you can find in the file 'exerciseTypes.json' 
- MongoDB backend interaction:
  - Once the JSON is pasted and validated, the parsed exercise is saved in the database
  - Data includes metadata (e.g., language, type, topic, difficulty) and full exercise content
- Backend endpoint required to:
  - Persist the exercise
  - Associate it with the authenticated user
  - Ensure availability for later review and practice

---

## ✅ Test to be Performed

- Form field validation: required, formats, boundaries
- Button state: "Copy Prompt" disabled until form is valid
- Prompt generation correctness based on input
- Clipboard copy success handling
- Error handling on invalid/malformed JSON input
- Success flow from prompt creation to JSON import
- Message and feedback accuracy in all stages

---

## 🛠 Technical Background

- Must comply with project’s `readme.md` and ui docs
- Use shared components and logic from the core UI kit
- Clipboard API must be used securely and fallback gracefully if access fails
