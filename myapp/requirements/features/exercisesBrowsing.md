## 📘 Feature: Exercises Browsing & Filtering

### General Description
Allows users to efficiently browse, filter, sort, and manage their created exercises from the **"My Exercises"** screen.

- **Purpose**: Simplify access and organization of generated exercises, especially when the list becomes extensive (100+).
- **Use Cases**:
  - View list of generated exercises
  - Filter by `language`, `exerciseType`, `status`
  - Sort by `language`, `exerciseType`, `difficulty`, `createdAt`
  - Expand exercise for full preview
  - Access specific exercise with a tap
  - Multi-select + delete exercises with soft-delete behavior (trash with 5-day undo)
- **Edge Cases**:
  - Empty exercise list
  - Long text in `topicDescription` or `exerciseType` fields
  - Attempting to delete with nothing selected (delete button is not available if nothing is selected)
  - Restoring from trash after 5 days (using a flag on the exercise data)

---

### Screens Involved

#### 📱 My Exercises Screen
- **Displays**: Scrollable, compact list of exercises with:
  - `topicDescription` (ellipsis if too long)
  - `exerciseType` (ellipsis if too long)
  - `targetLanguage` (e.g., "EN", "IT", small flag icon)
  - `userLevel` (e.g., B1.2)
  - `difficulty` (visual: 1–3 dots, filled = difficulty level)
  - `status` (visual: progress bar or 3-step pill indicator: Not Started / In Progress / Completed)

#### 🧭 Interactions
- **Tap on exercise** → open exercise
- **Hold** → expands list item (shows full `topicDescription`, other details inline)
- **Slide right** → selects item (highlighted)
- **Tap after slide** → toggle select
- **Other buttons**:
  after at leseast one item is selected show:
  - `Select All`/`Deselect All`
  - `Delete` (moves to trash)
- **Trash View**: Toggle to show exercises in trash (label: "Deleted", time remaining before purge)

---

### Logics and Validations

- **Filtering Options**:
  in frindly mobile versions, these options should not be constantly visible by constantly occupying part of the screen, but there should be a menu that expands and retracts to
  - `targetLanguage`: dropdown (multi or single)
  - `exerciseType`: dropdown
  - `status`: segmented control (To Start, In Progress, Completed)

- **Sorting Options**:
  in frindly mobile versions, these options should not be constantly visible by constantly occupying part of the screen, but there should be a menu that expands and retracts to
  - Dropdown or icon-triggered modal
  - Default: `createdAt` descending
  - Others: `language`, `exerciseType`, `difficulty`

- **Soft Delete**:
  - Exercises marked as `deletedAt`
  - Automatically purged after 5 days
  - Visual label: “In Trash – X days left”

- **Expand/Collapse logic**:
  - On hold → toggles expanded mode in-list
  - Only one expanded at a time 

---

### UI

- Must **conform to global project UI documentation**
- List must be **compact**, scrollable, mobile-first design
- Key UI components:
  - Expandable card for exercise
  - Icons for status, language
  - Visual difficulty dots (`● ● ○` style)
  - Inline selection with soft highlight
- Trash toggle: Tab or segmented toggle
- All interactions optimized for thumb navigation (no hidden options)

---

### Addictions and Integrations

- **Backend API**:
  - `GET /exercises` → supports query params for filters/sorting
  - `DELETE /exercises/:id` → marks as deleted (soft delete)
  - `GET /exercises?deleted=true` → fetch trash
  - `POST /exercises/restore/:id` → restore from trash

---

### Test to be Performed

- [ ] Exercise list loads correctly with >100 items
- [ ] Filters by language/type/status work as expected
- [ ] Sorting behaves correctly and defaults to createdAt
- [ ] Long `topicDescription` is truncated with `...`
- [ ] Exercise expands on hold and collapses on second hold
- [ ] Tap opens the selected exercise
- [ ] Swipe right + tap selects/deselects
- [ ] Delete selected moves items to trash
- [ ] Trash items show correct countdown
- [ ] Items permanently deleted after 5 days
- [ ] Responsive UI on different mobile sizes

---

### 🌐 Technical Background

- All components and styles **must conform to**:
  - Project’s global **UI documentation**
  - **README.md** setup and conventions
  - Language codes, status codes, and difficulty values must align with constants defined in shared types/interfaces

---
