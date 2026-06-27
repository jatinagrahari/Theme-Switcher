# 🌗 Theme Switcher

> **A React-based Theme Switcher using Context API and Tailwind CSS — toggle between dark and light mode globally across components without prop drilling**

[![React](https://img.shields.io/badge/Library-React-%2361DAFB?logo=react&logoColor=black)](https://reactjs.org/)
[![JavaScript](https://img.shields.io/badge/Language-JavaScript-%23F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Vite](https://img.shields.io/badge/Build-Vite-%23646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/Styling-Tailwind-%2306B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)

🐛 **[Report Bug](https://github.com/jatinagrahari/Theme-Switcher/issues)** • ⭐ **[GitHub](https://github.com/jatinagrahari/Theme-Switcher)**

---

## ✨ Features

- 🌙 **Dark / Light Toggle** — Switch between themes instantly using a clean toggle button
- 🌍 **Global State** — Theme state managed via Context API, accessible in any component
- 🎨 **Tailwind Dark Mode** — Uses Tailwind's `class` strategy for dark mode styling
- ⚡ **Real-time Switch** — DOM updates instantly on toggle with no flicker
- 🧩 **Reusable Context** — ThemeProvider can wrap any React app out of the box

---

## 🛠️ Tech Stack

| Layer                | Technology        |
| -------------------- | ----------------- |
| **UI Library**       | React             |
| **Language**         | JavaScript        |
| **Build Tool**       | Vite              |
| **Styling**          | Tailwind CSS      |
| **State Management** | React Context API |

---

## ⚙️ React Concepts Used

- `createContext` — Creating the global theme context
- `useContext` — Consuming theme state in child components
- `useState` — Managing `"light"` / `"dark"` theme state
- `useEffect` — Syncing theme state to the `<html>` element's class list

---

## 🚀 Quick Start

### Prerequisites

- Node.js installed
- VS Code (recommended)

### Installation

```bash
# Clone the repository
git clone https://github.com/jatinagrahari/Theme-Switcher.git

# Navigate to project directory
cd Theme-Switcher

# Install dependencies
npm install

# Start development server
npm run dev
```

---

## 📁 Project Structure

```bash
Theme-Switcher/
├── src/
│   ├── components/
│   │   ├── Card.jsx           # Product card with dark/light styles
│   │   └── ThemeButton.jsx    # Toggle switch component
│   ├── contexts/
│   │   └── theme.js           # Context creation + ThemeProvider
│   ├── App.jsx                # Root component — theme logic
│   ├── App.css
│   └── main.jsx               # Entry point
├── public/
├── index.html
└── README.md
```

---

## 🎯 How It Works

1. **ThemeProvider wraps the app** — Context is available globally
2. **Toggle the switch** — Calls `lightTheme()` or `darkTheme()` from context
3. **useEffect fires** — Removes old class and adds new one to `<html>`
4. **Tailwind reacts** — All `dark:` utility classes activate/deactivate instantly

---

## 🧠 Key Implementation

### Theme Sync via useEffect

```javascript
useEffect(() => {
  document.querySelector("html").classList.remove("light", "dark");
  document.querySelector("html").classList.add(themeMode);
}, [themeMode]);
```

### Context Setup

```javascript
// contexts/theme.js
import { createContext, useContext } from "react";

export const ThemeContext = createContext({
  themeMode: "light",
  darkTheme: () => {},
  lightTheme: () => {},
});

export const ThemeProvider = ThemeContext.Provider;

export default function useTheme() {
  return useContext(ThemeContext);
}
```

---

## 📸 Screenshots

<details>
<summary><b>Click to expand screenshots</b></summary>

### Light Mode

![Light Mode](./src/assets/ss1.png)

### Dark Mode

![Dark Mode](./src/assets/ss2.png)

</details>

---

## 🚧 Current Status

Actively improving:

- Add more components to demonstrate theme propagation
- Persist theme preference in localStorage
- Smoother transition animations

---

## 📝 Future Improvements

- 💾 Save theme preference to localStorage
- 🎨 Multiple theme options beyond dark/light
- 📱 Better mobile layout
- ✨ CSS transition animations on switch

---

## 🙏 Acknowledgments

- Built with ❤️ using React + Vite + Tailwind CSS

---

## ⭐ Show your support

Give a ⭐️ if this helped you understand React Context API!
