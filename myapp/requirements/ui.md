# 🧭 LangEx UI Style Guide

This document describes the main UI structure, style rules, and user flows for the LangEx app. Use this as a reference for creating new HTML pages to ensure a consistent and modern user experience.

---

#### 🎨 1. Design Principles
- **Dark theme**: The app uses a dark background with light text for high contrast and modern look.
- **Minimal and fluid layout**: No central card or device simulation. Content is full-width and adapts to both mobile and desktop.
- **Bright accent colors**: Use vibrant colors (cyan, yellow, green, purple, pink) for highlights, buttons, and status indicators.
- **Highly rounded corners**: All inputs, buttons, and cards have large border-radius for a soft, modern feel.
- **Soft shadows and glow**: Buttons and interactive elements have subtle shadows and glow effects.
- **Large, readable fonts**: Prioritize clarity and accessibility.
- **Generous spacing**: Use ample padding and margin for a clean, airy interface.
- **Smooth animations**: Use fade-in and hover transitions for a polished experience.
- **Design Priorities**:
  - Clean, distraction-free interfaces
  - Quick access to essential features
  - Exercise-centric experience
  - Accessibility and inclusivity (WCAG AA compliant)
  - Support for RTL languages and dynamic content lengths
  - Clean, distraction-free layouts  
  - Key functionality accessible in few clicks  
  - Calming focus colors (blues, greens, whites)  
  - Vibrant accents for interactive elements (buttons, notifications)  
  - Attention about choosing the Primary font
  - Clear hierarchy: Headers , Subheaders, Body text 
  - WCAG AA contrast compliance  
  - App complitely in Dark mode and dark theme  
  - Screen reader compatibility  
  - Scalable text 
  - Persistent navigation menu  
  - Progress indicators/breadcrumbs  
  - Micro-interactions for user actions  
  - Toast notifications for system feedback  
  - 8px grid system  
  - Reusable component library  
  - Exercise-centric layouts  
  - Minimal UI during active exercises  
  - Mobile-first approach  
  - Adaptive breakpoints: Mobile: <768px , Tablet: 768-1024px , Desktop: ≥1024px  
  - Multilingual Support: RTL language compatibility and Dynamic UI expansion for text length variations  

---

#### 🎨 2. Color Palette
- **Background**: `#181A20` (very dark)
- **Surface**: `#23262F` (dark, for inputs and light cards)
- **Primary (Accent)**: `#7DE2FC` (cyan)
- **Primary Hover**: `#4FC3F7` (cyan, darker)
- **Accent**: `#FFE066` (yellow)
- **Success**: `#6FFFB0` (green)
- **Warning**: `#FFE066` (yellow)
- **Info**: `#B39DFF` (purple)
- **Danger**: `#FFB6B9` (pink)
- **Text Main**: `#F9FAFB` (white)
- **Text Light**: `#D1D5DB` (light gray)
- **Text Muted**: `#9CA3AF` (muted gray)
- **Text on Buttons**: `#23262F` (dark)

---

#### 🧩 3. UI Components
Typography
- Use the 'Inter' font family, sans-serif.
- Main headings: bold, large, with gradient accent if needed.
- Body text: regular or medium, always high contrast.
- Text is scalable and responsive.

Layout
- Use a `.container` class for main page sections.
- The layout is always full-width and height, with content centered vertically and horizontally.
- No fixed-width cards for the main layout.

Buttons
- Use the `.btn` and `.btn-primary` classes.
- Large, rounded, with a bright background and dark text.
- Glow and shadow on hover.

Forms & Inputs
- Use `.form-group`, `.form-label`, and `.form-input` classes.
- Inputs are highly rounded, with dark backgrounds and light text.
- Focus state: colored glow.
- Placeholder text is muted gray.

Links
- Use the primary accent color for links.
- On hover, use the hover accent color.

Checkbox
- Modern, rounded, with accent color.

Animations
- Use `.fade-in` for main content transitions.
- Buttons and links have smooth hover transitions.

---

#### 📱 4. Responsive Design
- Mobile-first: all elements scale down gracefully on small screens.
- Use media queries to adjust padding, font size, and spacing for screens < 640px.
- The UI should always feel natural and uncluttered on both mobile and desktop.

---

#### 📚 5. How to Extend
- When creating new pages, always use the color palette and component classes defined above.
- Maintain the dark, minimal, and modern look.
- Use generous spacing and large, readable text.
- Prefer accent colors for actions and highlights.
- Keep the UI uncluttered and accessible.
- always use the styles.css file as a reference. the components and UI of the app must always be consistent with each other and reuse the basic styles already defined in the css. the css must always be kept clean without unnecessary duplicates, it must be well reusable

---

