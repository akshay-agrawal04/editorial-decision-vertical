
# 📘 Editorial Decision Dashboard — Developer Specification

## 📌 Overview

This dashboard is designed to help editors assess reviewer recommendations and make publication decisions in a structured, user-friendly, and efficient manner. It is split into two primary panes:
- **Left Pane**: Submission information and review versions
- **Right Pane**: Decision-making tools and feedback interface

This spec outlines the functionality, layout, and interactivity discussed and implemented during prototyping.

---

## ✅ Functional Requirements

### 🧾 1. **Submission Details Section**
- Title: _“Assess editorial recommendation”_
- Includes:
  - **Submission title** with realistic placeholder
  - **Authors** (five plausible academic names)
  - **Date submitted**
  - **Abstract** (visually highlighted, expanded for clarity)
  - **Files/attachments** with icons and download links

```
📄 manuscript_v3.pdf  
📄 figures_v3.zip  
📄 supplementary_material.xlsx  
```

---

### 📚 2. **Version Tabs**
- Versions are shown in a **tabbed layout** (`Version 1`, `Version 2`, `Version 3`, etc.).
- Clicking a tab shows only the relevant version's reviewer/editor feedback.
- Only **one version pane is visible** at a time.
- Reviewer boxes include:
  - **Name** (realistic)
  - **Date**
  - **Decision**
  - **Expandable section** ("View full report") with:
    - Confidential feedback to editor
    - Recommendation (e.g., Revise)
    - Checklist of evaluation criteria
    - Confidential editor comments
    - Feedback for authors

---

### 🧠 3. **Split View Layout**
- The page is divided into **left (60%)** and **right (40%)** panes.
- Both panes are **independently scrollable**.

---

### 🎯 4. **Decision Section (Right Pane)**
- Header: _“Ready for a decision?”_
- **Radio options**: Yes / No
  - If **"No"**:
    - Show buttons: _“Snooze”_, _“Invite more reviewers”_
  - If **"Yes"**:
    - Show actionable **buttons**: _“Accept”_, _“Revise”_, _“Reject”_
    - Selecting a button auto-fills an **email template**
    - If the user has edited the text before choosing another option, a **confirmation modal** is shown before overwriting

#### ✉ Email Template Logic:
- Accept: “Thank you for submitting your manuscript...”
- Revise: “We would like to request that you revise...”
- Reject: “We regret to inform you that we will not...”

---

## 🧩 UI/UX Requirements

### 🎨 Abstract Styling
- Slightly larger text
- Soft background color
- Padded and readable

### 📂 Attachment Styling
- List-style removed
- Aligned icons
- Hover/clickable styling for files

### 👁 Expand/Collapse for Full Reports
- "View full report" is a styled **text link**
- Clicking toggles visibility of the full review content

### ⚠ Overwrite Confirmation
- Only appears **if** user has changed the email text
- Triggered before replacing content via decision button

---

## 🧪 Testing Requirements

- [ ] Switching version tabs updates visible content
- [ ] Clicking "Accept", "Revise", or "Reject" fills the feedback textarea
- [ ] Confirmation modal only appears if textarea content has changed
- [ ] “Snooze” and “Invite more reviewers” only appear when "No" is selected
- [ ] "View full report" toggles expanded review content correctly
- [ ] Page looks and functions properly on screen sizes >1024px
- [ ] Scrollbars are limited to each pane — no page-wide scrolling

---

## 🔧 Technologies

- **HTML5**, **CSS3**, and **Vanilla JS**
- No external libraries (unless explicitly added later)
- Modular and extendable for integration with backend decision workflows

---

## 🧱 Suggested Folder Structure

```
/editorial-dashboard/
│
├── index.html
├── style.css
├── script.js
└── assets/
    └── icons/
```

## 📄 License

MIT License. This project is built for internal editorial workflow prototyping and may be extended to production usage upon validation.
