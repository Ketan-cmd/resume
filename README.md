# 🎮 Signal Decoder – Invisible Pattern Game

A memory and pattern recognition game built with React, TypeScript, and Vite. Test your visual memory by identifying hidden patterns that flash briefly on a 5×5 grid!

## 🎯 Game Overview

**Signal Decoder** challenges players to memorize and reproduce patterns displayed on a grid. Each level presents a unique pattern rule that determines which cells flash. After the pattern disappears, you must select the correct cells from memory.

### Features

- **5 Progressive Levels** with increasing difficulty
- **Pattern Rules**: Even indices, diagonals, prime numbers, cross patterns, and mathematical sequences
- **10-Second Flash Timer** with visual progress bar
- **Score Tracking System** that rewards accuracy
- **Dark/Light Theme Toggle** for comfortable gameplay
- **Responsive Design** that works on different screen sizes
- **Visual Feedback** showing correct/incorrect selections

## 🕹️ How to Play

1. **Watch Phase** (10 seconds): Cells matching the current level's pattern will flash blue
2. **Select Phase**: Click on the cells you remember seeing flash
3. **Result Phase**: 
   - Green cells = Correct pattern cells
   - Red cells = Incorrectly selected cells
   - Blue cells = Your selections
4. **Score**: Earn 1 point for each correctly identified cell
5. **Progress**: Complete all 5 levels to master the game!

## 📐 Level Patterns

| Level | Pattern Rule | Description |
|-------|-------------|-------------|
| **1** | Even Indices | Cells at even positions (0, 2, 4, 6...) |
| **2** | Diagonals | Main diagonal and anti-diagonal cells |
| **3** | Prime Numbers | Cells at prime index positions (2, 3, 5, 7, 11...) |
| **4** | Cross/Plus | Center cell and 4 adjacent cells forming a plus |
| **5** | Modulo Pattern | Cells where (row + col) % 3 === 0 |

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Installation

```bash
# Clone the repository
git clone <repository-url>

# Navigate to project directory
cd signal-decoder

# Install dependencies
npm install
```

### Development

```bash
# Start development server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Build

```bash
# Create production build
npm run build

# Preview production build
npm run preview
```

## 🛠️ Tech Stack

- **React 19** - UI framework
- **TypeScript** - Type safety
- **Vite** - Build tool and dev server
- **CSS3** - Styling with CSS variables for theming
- **ESLint** - Code linting

## 📁 Project Structure

```
signal-decoder/
├── src/
│   ├── App.tsx           # Main game component
│   ├── App.css           # Styling and themes
│   ├── levelRules.ts     # Pattern logic for each level
│   ├── main.tsx          # React entry point
│   └── assets/           # Static assets
├── public/               # Public assets
├── index.html            # HTML entry point
├── package.json          # Dependencies
├── tsconfig.json         # TypeScript config
└── vite.config.ts        # Vite configuration
```

## 🎨 Customization

### Adding New Levels

Edit `src/levelRules.ts` to add more level patterns:

```typescript
export const levelRules = {
  // ... existing levels
  6: (index: number) => {
    // Your custom pattern logic
    return /* boolean condition */;
  },
};
```

### Adjusting Timer Duration

Modify the `duration` variable in `App.tsx`:

```typescript
const duration = 10000; // milliseconds (currently 10 seconds)
```

### Theme Colors

Update CSS variables in `src/App.css`:

```css
:root {
  --bg-dark: #050816;
  --bg-light: #f7f7f7;
  /* ... other theme variables */
}
```

## 🎮 Game Mechanics

- **Flash Duration**: 10 seconds with progress bar
- **Scoring**: +1 point per correctly identified cell
- **No Penalties**: Incorrect selections don't reduce score
- **Level Progression**: Must complete level before advancing
- **Restart Option**: Reset to Level 1 at any time

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 👨‍💻 Author

Built with ❤️ for the Emitrr project

---

**Enjoy the game and challenge your memory! 🧠✨**
