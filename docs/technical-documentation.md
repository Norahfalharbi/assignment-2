# Technical Documentation 

This document explains the technical implementation of my **Portfolio Project**, what I accomplished, and areas for improvement.

---

## 1.Code Overview

### **HTML (index.html)**
- **Header & Navigation**
  - A `<header>` contains a `<nav>` with the site logo (**Portfolio**) and navigation links (**About**, **Projects**, **Contact**).
  - Anchor links use `href="#id"` for smooth scrolling.

- **Introduction Section**
  - Displays: “Hi I am Norah Alharbi.”
  - Connected to JavaScript for a **time-based greeting** (Good Morning, Afternoon, or Evening).

- **About Section**
  - Includes a short bio paragraph and tagline list.
  - Uses semantic tags (`<section>`, `<h2>`, `<p>`, `<ul>`).

- **Projects Section**
  - Projects shown as responsive cards using a **masonry layout**.
  - Each `.card` includes:
    1. `.card-media` → image/logo.  
    2. `.card-body` → title & description.  
    3. `.card-actions` → “Details” button (expand/collapse description).  
  - Added **filter buttons** and a **live search** bar to dynamically show/hide projects.

- **Favorite Books Section**
  - Fetches Arabic or programming books dynamically from the **Google Books API**.
  - Displays book covers, titles, and authors; skips books with missing images.
  - Shows fallback/error messages if API fails.

- **Contact Section**
  - A contact form with Name, Email, and Message.
  - Uses native validation with custom messages (e.g., “Email is required”).
  - Displays success confirmation after valid submission.

- **Footer**
  - Includes a “Back to Top” link and displays the current year (auto-updated via JS).

---

### **CSS (css/styles.css)**
- **Theme Variables**
  - Declared with `:root` and support both **light** and **dark themes**.
  - Uses `[data-theme="light"]` and `[data-theme="dark"]` attributes.

- **Layout**
  - `.section` → consistent padding and max width.
  - `.nav` → Flexbox layout with space-between for logo and links.
  - `.projects-grid` → column-count layout for masonry cards.
  - `.card` → hover lift effect and box shadow.

- **Filter & Search**
  - `.filter` → flex layout for filter buttons and search input.
  - `.btn.active` → outlined to indicate selected filter.

- **Forms**
  - `.grid-2` → two-column layout on desktop.
  - Inputs and textareas styled with padding, rounded corners, and visible focus states.
  - Inline error messages styled in red; success messages in green.

- **Books Section**
  - `.books-grid` → responsive grid for API-loaded book cards.
  - `.book-card` → consistent image size, centered content, hover animation.

---

### **JavaScript (js/script.js)**
- **Greeting**
  - Uses `new Date()` to decide and alert a time-based greeting.
  - Saves visitor’s name in `localStorage`.

- **Filter & Search**
  - Filters projects by category or keyword.
  - Displays empty state when no matches found.

- **Card Details**
  - Toggles extra project info on button click.

- **Theme Switcher**
  - Two buttons (Light / Dark) update `data-theme` attribute.
  - Saves theme preference in `localStorage`.

- **Books Fetch**
  - Uses the **Google Books API** to display book data.
  - Handles loading, missing images, and errors gracefully.

- **Contact Form**
  - Adds native HTML5 validation with custom error messages.
  - Displays a success message and clears the form after valid submission.

---

## 2. Current Strengths
- Semantic, accessible HTML structure.  
- Fully responsive layout.  
- Dark/light theme with persistent user setting.  
- Dynamic filtering, searching, and API integration.  
- Native validation with inline feedback.  

---

## 3. Future Improvements
- **Projects**
  - Link “Details” buttons to GitHub repos or live demos.
  - Add more project cards with consistent design.

- **Contact Form**
  - Connect to backend (Formspree, EmailJS, or Node.js) for real submissions.
  - Add loading animation and spam protection.

- **Greeting**
  - Move greeting from `alert()` to visible page text.

- **Navigation**
  - Highlight active section in navbar during scroll.
  - Add mobile menu button for smaller screens.

- **Accessibility**
  - Add more `aria-label`s and test color contrast.
  - Improve keyboard focus styles.


---

## 4.  Known Issues
- Greeting alert interrupts initial user experience.  
- Contact form not connected to backend.  
- Needs more accessibility testing.  
- Some books from API have missing images (skipped gracefully).  

---
