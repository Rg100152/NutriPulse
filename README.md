# 🍏 NutriPulse – Health & Food Planner App

![NutriPulse Banner](https://images.unsplash.com/photo-1498837167922-ddd27525d352?auto=format&fit=crop&w=1200&q=80)

**NutriPulse** is a fully functional, mobile-first health tracking and personalized meal planning web application. Built as a **single-file HTML/CSS/JS** solution, it helps users log daily vitals, track calories/water/steps, and get AI‑like meal suggestions – all with a premium, modern UI.

---

## ✨ Live Demo

👉 **Try it now:** [NutriPulse on GitHub Pages](https://rg100152.github.io/NutriPulse)  
*(or open `index.html` directly in your browser)*

---

## 🚀 Features

### ✅ Core Functionality (Phase 1)
- **User Authentication** – Onboarding & profile setup (email/phone/Google).
- **Health Vitals Logging** – Record **Blood Pressure**, **Glucose**, **Weight** via modal forms.
- **Daily Dashboard** – Real‑time progress bars for:
  - Calories (target: 2,100 kcal)
  - Water (target: 3.5 L)
  - Steps (target: 10,000)
- **Meal Planner** – Breakfast, Lunch, Dinner with:
  - Macro breakdown (Protein, Carbs, Fat)
  - Log meals with calorie tracking
  - Swap individual meals or generate a new plan
- **Health Score** – Dynamic score (0–100) based on logged calories.
- **Persistent State** – All data saved to `localStorage` (survives page refresh).

### 🎨 UI/UX Highlights
- **Premium Design** – Clean, energetic, trust‑worthy (Bio Emerald, Health Cyan, Calorie Coral).
- **Mobile‑First** – Responsive, touch‑friendly, with smooth animations.
- **Stock Images** – Real food photography (Unsplash) for meals and profile.
- **Accessibility** – Keyboard support (Enter to save, Escape to close), labels for screen readers.
- **Interactive Bottom Nav** – Tab switching with visual feedback.

### 🧠 Smart Features (Demo)
- **Generate New Plan** – Updates all meals with new descriptions (resets logged status).
- **Swap All** – Replaces all meals with macro‑equivalent alternatives.
- **Single Meal Swap** – Toggle between two healthy options per meal.
- **Gamification** – Logging vitals (Glucose/Weight) adds bonus calories.

---

## 📸 Screenshots

| Dashboard | Meal Planner | Quick Check‑up |
|:---:|:---:|:---:|
| ![Dashboard](https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=400&q=80) | ![Meals](https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&w=400&q=80) | ![Vitals](https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?auto=format&fit=crop&w=400&q=80) |

---

## 🛠️ Tech Stack

| Layer          | Technology |
|----------------|------------|
| **Frontend**   | HTML5, CSS3, Vanilla JavaScript |
| **Icons**      | Font Awesome 6 |
| **Fonts**      | Google Fonts (Poppins, Inter) |
| **Images**     | Unsplash (free stock photos) |
| **Persistence**| `localStorage` (no backend required) |
| **Hosting**    | GitHub Pages (or any static host) |

---

## 📁 Project Structure

```
NutriPulse/
├── index.html          # Complete single‑file application
├── README.md           # Project documentation (this file)
└── (optional) assets/  # Custom images / icons
```

> **Note:** The entire app is contained in **one HTML file** – no build tools, no dependencies to install.

---

## 🔧 How to Use

1. **Clone or download** this repository:
   ```bash
   git clone https://github.com/Rg100152/NutriPulse.git
   ```
2. **Open** `index.html` in any modern browser (Chrome, Firefox, Safari, Edge).
3. **Start tracking** – Log your vitals, meals, and watch the dashboard update live.

---

## 🌟 Key Interactions

| Action | What Happens |
|--------|--------------|
| Click **Log BP / Glucose / Weight** | Opens modal; enter value → saves with toast confirmation |
| Click **Log** (on a meal) | Marks meal as eaten; adds calories to dashboard |
| Click **Swap** (on a meal) | Changes meal description; resets logged status |
| Click **Generate new plan** | Refreshes all meals with new suggestions |
| Click **Swap all** | Replaces all meals with macro‑equivalent options |
| Tap bottom nav tabs | Switches active tab (feedback via toast) |

---

## 🧪 Roadmap / Future Enhancements (Phase 2)

- [ ] Real‑time wearable integration (Apple HealthKit / Google Fit)
- [ ] Direct 1‑on‑1 nutritionist video consultation
- [ ] AI‑powered grocery list generator (Blinkit / Instamart API)
- [ ] PDF export of weekly health reports
- [ ] Dark mode support

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- **Unsplash** – For stunning, free food & health photography  
- **Font Awesome** – For beautiful icons  
- **Google Fonts** – For Inter & Poppins typefaces  

---

## 📬 Contact

**Author:** Raj Kumar  
**GitHub:** [@Rg100152](https://github.com/Rg100152)  
**Project Link:** [https://github.com/Rg100152/NutriPulse](https://github.com/Rg100152/NutriPulse)

---

> *"One‑stop health tracking + real‑time dynamic meal recommendations."*  
> *– NutriPulse, built with ❤️ for a healthier you.*
