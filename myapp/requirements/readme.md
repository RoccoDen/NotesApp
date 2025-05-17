# LangEx - Personalized language learning app
Welcome to the LangEx project, an app for language students who want to practice with tailor-made exercises, thanks to an AI-based system.

This README file serves as an initial overview of the project and a starting point for the complete documentation.

Note: every time you find //to be expanded//, it indicates that part will be completed later with additional details.

---

## 📚 Index
  📁 Documentation Structure
  🎯 The Idea
  📌 Description
  🤝 Want to Contribute?
  🏁 Preliminary Competitor Analysis
  ⚙️ Technical Settings
  🔧 Features
  🎨 UI guidelines

---

## 📁 Documentation Structure
The project documentation is organized into multiple files and folders to ensure clarity, modularity, and ease of reading. The current file, README.md, serves as a general overview of the project and is the starting point for understanding the app's concept and structure. From here, the rest of the documentation branches out into other files dedicated to specific features of the project.

Each features of the app is described in its own dedicated file, making development, testing, and project collaboration simpler. Explore the different folders and their contents based on the part of the project you want to work on or learn more about.

Below is the main structure of the documentation:
/project/
│
├── README.md ← General project overview
├── README/features/
│ └── Files dedicated to individual app functionalities (e.g., signin, login, exercise generation)
├── README/ui/
│ └── Documentation on the visual design: color palette, styles, screens, and mockups
├── README/technologies/
│ └── Details about the tech stack and app architecture
└── README/mvp/
  └── Files describing the Minimum Viable Product (the core version needed to test the app)

---

## 🎯 The idea
The idea came from a personal need—while learning languages, I often found myself lacking enough exercises to practice and master specific concepts.

---

## 📌 Description  
**LangEx** is a language-learning app that generates tailored language exercises using AI:  
- Users describe their desired exercise type via a customizable form (language, proficiency level, exercise type, topic, and specific grammar/vocabulary focus). The app then generates an AI-ready prompt. *(Future Premium version may auto-generate exercises via external APIs.)*  
- Once the exercise is generated:  
  - The app displays it in an interactive format  
  - Users complete the exercise and receive instant feedback  
  - Saved words/phrases can be used to create flashcards or future exercises  
- The app will progressively expand with additional features to support long-term personalized language learning.  

---

## 🤝 Want to Contribute?  
Interested in contributing to this project as a developer, designer, tester, or have ideas to share? Feel free to open a discussion or send me a message!  

---

## 🏁 Preliminary Competitor Analysis  
While many language-learning apps exist (Duolingo, Babbel, Memrise, Anki, etc.), none appear to specialize in AI-powered, personalized exercise generation.  
Current solutions:  
- Offer pre-made exercises  
- Lack flexibility in content creation  
- Don’t adapt to users’ specific needs  
//to be expanded// 

---

## ⚙️ Technical Settings  
All code must be written in English:   Variable names, Code comments, Documentation strings, Commit messages, Any other code-related text  
*(Consistency in English ensures global collaboration and maintainability.)*  

---
## 🔧 Features  

### Core Features:  
- Navigation menu  
- Signup  
- Login  
- User profile viewing & management  
- Exercise generation  
- Exercises browsing & filtering  
- Interactive exercise display & execution  
- Exercise deletion  
- App settings

### Future Features:  
- User follow system  
- Public exercise publishing  
- Exercise sharing with specific users  
- Public exercise rating system  
- Flashcards  
- Personal statistics & progress tracking  
- Premium version  
- Custom listening exercise generation  
- Custom speaking exercise generation  
- Exercise correction editing  
- Enhanced user progress analytics  
- App usage data statistics  
- Multilingual UI support  

---

### 🎨 UI Guidelines  
LangEx's user interface prioritizes simplicity, clarity, and accessibility to deliver an optimal learning experience:
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



