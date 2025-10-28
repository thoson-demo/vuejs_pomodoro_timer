# 🍅 Pomodoro Timer

A Pomodoro Timer application built with Vue 3 and Vite, helping you manage your work time effectively using the Pomodoro Technique.

## 🌟 Demo

View live demo at: [GitHub Pages](https://thoson-demo.github.io/vuejs_pomodoro_timer/)

## ✨ Features

- ⏰ Countdown timer with circular progress interface
- 🎯 Pomodoro cycles (25 minutes work, 5 minutes break)
- 🎨 Beautiful and responsive UI
- 🔊 Notifications when time is up
- ⏸️ Pause and resume functionality

## 🚀 Installation Guide

### System Requirements

- Node.js >= 16.0.0
- npm or yarn

### Setup

1. **Clone repository:**
   ```bash
   git clone https://github.com/thoson-demo/vuejs_pomodoro_timer.git
   cd vuejs_pomodoro_timer
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run development server:**
   ```bash
   npm run dev
   ```

4. **Open browser and navigate to:**
   ```
   http://localhost:5173
   ```

## 🔧 Basic Scripts

### Development
```bash
npm run dev          # Start dev server with hot-reload
```

### Production Build
```bash
npm run build        # Build for production
npm run preview      # Preview production build
```

### Code Quality
```bash
npm run lint         # Check code with ESLint
```

## 🛠️ Technologies Used

- **Vue 3** - Progressive JavaScript Framework
- **Vite** - Fast build tool
- **JavaScript/ES6+** - Programming language
- **CSS3** - Styling and animations

## 📁 Project Structure

```
src/
├── components/          # Vue components
│   ├── PomodoroTimer.vue   # Main timer component
│   ├── TimerCircle.vue     # Circle progress indicator
│   ├── TimerControl.vue    # Control buttons
│   └── TimerDisplay.vue    # Time display
├── models/             # Type definitions
│   └── Status.ts       # Timer status types
├── assets/             # CSS and assets
└── App.vue            # Root component
```

## 🤝 Contributing

All contributions are welcome! Please create an issue or pull request.

## 📄 License

MIT License
