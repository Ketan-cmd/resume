# 📦 Signal Decoder – The Invisible Pattern Game

A React + TypeScript puzzle game that challenges players to decode hidden flashing patterns on a 5×5 grid.

## 📋 Overview

**Signal Decoder** is an interactive grid-based puzzle game where cells flash following hidden mathematical patterns. Players observe the animation, identify the underlying rule, and select the cells they believe were flashing. This project demonstrates proficiency in React, TypeScript, state management, and clean code architecture.

Built as part of a frontend assignment, this project showcases:

- **React + TypeScript** proficiency with functional components and hooks
- **Logical pattern generation** with modular rule definitions
- **UI state management** with phase-based game flow
- **Clean, modular code structure** for maintainability
- **CSS animations** (no external UI libraries)
- **Responsive UI design** for multiple screen sizes
- **Bonus features**: scoring system, theme toggle, and progress bar

## 🎮 How the Game Works

1. A **5×5 grid** is displayed to the player
2. **Flash Phase**: Cells flash for 10 seconds based on the current level's hidden rule
3. **Selection Phase**: After flashing ends, players select cells they believe were flashing
4. **Result Phase**: On submit:
   - ✅ **Correct selections** → highlighted in green
   - ❌ **Incorrect selections** → highlighted in red
   - **Score updates** based on accuracy
5. **Level Progression**: Complete 5 levels with increasing complexity
6. **Final Score**: View total score with option to restart

## 🧩 Levels & Pattern Rules

| Level | Rule | Implementation |
|-------|------|----------------|
| **1** | Even Indices | `index % 2 === 0` |
| **2** | Diagonals | `row === col \|\| row + col === 4` |
| **3** | Prime Numbers | `isPrime(index)` |
| **4** | Cross/Plus | Center cell (12) + 4 adjacent neighbors |
| **5** | Modulo Pattern | `(row + col) % 3 === 0` |

Each rule is implemented in a reusable, modular `levelRules.ts` file for easy maintenance and scalability.

## ⭐ Features

### ✔ Core Features (Required)

- 5×5 grid with dynamic flashing animations
- Pattern generation per level with distinct rules
- 10-second flashing period using timers
- Selection phase with real-time visual feedback
- Evaluation of user selections (correct/incorrect highlighting)
- Level progression system
- Responsive and clean UI

### ✔ Bonus Features (Implemented)

- **Score Counter**: Track points across all levels
- **10-Second Progress Bar**: Visual countdown during flash phase
- **Light/Dark Theme Toggle**: Switch between themes for comfortable viewing
- **Restart Game Functionality**: Reset progress and replay from Level 1

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v16 or higher)
- **npm** or **yarn**

### 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd signal-decoder
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Start Development Server

```bash
npm run dev
```

### 4️⃣ Open the App

Visit [http://localhost:5173](http://localhost:5173) in your browser.

### Build for Production

```bash
# Create production build
npm run build

# Preview production build
npm run preview
```

Build output: `/dist` directory

## 🛠️ Tech Stack

- **React 19** - Modern UI framework with functional components
- **TypeScript** - Type safety and better developer experience
- **Vite** - Lightning-fast build tool and dev server
- **CSS3** - Custom animations and styling (no UI libraries)
- **CSS Variables** - Dynamic theming support
- **ESLint** - Code quality and consistency

## 📁 Project Structure

```
signal-decoder/
├── src/
│   ├── App.tsx           # Main game logic + UI components
│   ├── App.css           # Styling, animations, responsive layout
│   ├── index.css         # Global styles & resets
│   ├── levelRules.ts     # Rule definitions for each level
│   ├── main.tsx          # React root entry point
│   └── assets/           # (Optional) Images or icons
├── public/               # Static public assets
├── index.html            # HTML entry point
├── package.json          # Project dependencies
├── tsconfig.json         # TypeScript configuration
├── tsconfig.app.json     # App-specific TypeScript config
├── tsconfig.node.json    # Node-specific TypeScript config
├── vite.config.ts        # Vite configuration
└── eslint.config.js      # ESLint rules
```

## 📝 Code Highlights

### 🔹 Modular Level Logic

All pattern rules are defined in `levelRules.ts` for easy maintenance and scalability:

```typescript
export const levelRules = {
  1: (index: number) => index % 2 === 0,
  2: (index: number) => {
    const { row, col } = rc(index);
    return row === col || row + col === GRID_SIZE - 1;
  },
  // ... more levels
};
```

### 🔹 Phase-Based UI Flow

The app transitions cleanly between three states:
- **flash**: Cells animate based on pattern
- **select**: User selects cells
- **result**: Show correct/incorrect feedback

### 🔹 Fully Responsive

Grid, buttons, and typography adjust seamlessly for mobile and desktop screens.

### 🔹 Clean, Commented Code

Key logic areas are documented for clarity and maintainability.

## 🎨 Customization

### Adding New Levels

Edit `src/levelRules.ts` to add more level patterns:

```typescript
export const levelRules = {
  // ... existing levels
  6: (index: number) => {
    const { row, col } = rc(index);
    return row === 0 || col === 0; // Border cells
  },
};
```

### Adjusting Flash Duration

Modify the `duration` constant in `App.tsx`:

```typescript
const duration = 10000; // milliseconds (10 seconds)
```

### Theme Customization

Update CSS variables in `src/App.css`:

```css
:root {
  --bg-dark: #050816;
  --bg-light: #f7f7f7;
  --cell-dark: #111827;
  --cell-light: #ffffff;
  --text-dark: #e5e7eb;
  --text-light: #111827;
}
```

## 🌐 Deployment

This project can be easily deployed using:

- **Vercel** (recommended)
- **Netlify**
- **GitHub Pages**

### Deployment Steps

1. **Build the project**:
   ```bash
   npm run build
   ```

2. **Deploy the `/dist` folder** to your hosting platform

3. **Automatic deployments**: Connect your Git repository for CI/CD

## 🎮 Game Mechanics

- **Flash Duration**: 10 seconds with visual progress bar
- **Scoring**: +1 point per correctly identified cell
- **No Penalties**: Incorrect selections don't reduce score
- **Level Progression**: Complete current level to advance to next
- **Restart Option**: Reset to Level 1 at any time

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 👨‍💻 Author

Built with ❤️ for the **Emitrr** project

---

**Enjoy the game and challenge your pattern recognition skills! 🧠✨**
