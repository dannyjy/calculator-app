# Calculator App

A modern calculator built with React, TypeScript, Vite, and Tailwind CSS.

It supports common arithmetic operations with a reducer-based state model and a clean, responsive button layout.

## Features

- Basic arithmetic: addition (`+`), subtraction (`-`), multiplication (`×`), and division (`÷`)
- Decimal number input (`.`) with duplicate decimal prevention
- Sign toggle (`+/-`) for the current input
- Percentage conversion (`%`) for the current input
- Delete button to remove one character at a time
- All clear (`AC`) to reset the calculator state
- Chained operation behavior (evaluate current expression and continue)

## Tech Stack

- React 19
- TypeScript
- Vite 8
- Tailwind CSS 4

## Project Structure

```text
src/
  App.tsx
  main.tsx
  index.css
  components/
    layout/
      main.tsx          # Calculator layout and button grid
    ui/
      CalculatorButton.tsx
      OperationButton.tsx
  utils/
    reducer.ts          # Calculator state transitions
    evaluate.ts         # Operation evaluation logic
  types/
    types.tsx           # Shared action/state types
```

## How It Works

The calculator uses `useReducer` for predictable state updates:

- `currentOperand`: currently typed value
- `prevOperand`: stored previous value for binary operations
- `operation`: selected operation (`+`, `-`, `×`, `÷`)

Actions handled by the reducer include:

- `Add Digit`
- `Operation`
- `Evaluate`
- `Delete Digit`
- `Percentage`
- `PositiveToggle`
- `Clear`

The `evaluate` utility converts both operands to numbers and returns the computed result as a string.

## Prerequisites

- Node.js 18+ (recommended: latest LTS)
- npm (comes with Node.js)

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/dannyjy/calculator-app.git
cd calculator-app
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
npm run dev
```

4. Open the local URL shown in terminal (usually `http://localhost:5173`).

## Available Scripts

- `npm run dev`: start Vite development server
- `npm run build`: type-check and create production build
- `npm run preview`: preview the production build locally
- `npm run lint`: run ESLint

## Build for Production

```bash
npm run build
```

Build output is generated in the `dist/` directory.

To preview the production build:

```bash
npm run preview
```

## Notes and Limitations

- Division by zero follows JavaScript behavior (for example, `Infinity`).
- Results are stringified from numeric operations and may include floating-point precision behavior.

## Future Improvements

- Add keyboard support
- Add expression history
- Add unit tests for reducer and evaluate logic
- Improve accessibility labels and focus states
