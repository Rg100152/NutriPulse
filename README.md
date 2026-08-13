
# 🍏 NutriPulse – Complete Health & Food Planner Ecosystem

**Version:** 2.0.0 | **Status:** Production-Ready | **License:** MIT

![NutriPulse Banner](https://images.unsplash.com/photo-1506126613408-eca07ce68773?auto=format&fit=crop&w=1200&q=80)

---

## 📜 Table of Contents

1.  [Project Overview & Mission](#-project-overview--mission)
2.  [Business Requirements Document (BRD)](#-business-requirements-document-brd)
    - 2.1 Project Goals & Objectives
    - 2.2 Target Audience
    - 2.3 Functional Requirements Matrix
    - 2.4 Non-Functional Requirements (Performance, Security, Usability)
3.  [Scope of Work (SOW)](#-scope-of-work-sow)
    - 3.1 In-Scope (Phase 1)
    - 3.2 Out-of-Scope (Phase 2 & Beyond)
4.  [System Architecture & Data Flow Diagrams (DFD)](#-system-architecture--data-flow-diagrams-dfd)
    - 4.1 DFD Level 0 (Context Diagram)
    - 4.2 DFD Level 1 (Process Breakdown)
    - 4.3 Technology Stack Architecture
5.  [Information Architecture & Sitemap](#-information-architecture--sitemap)
6.  [Style Guide & Mood Board](#-style-guide--mood-board)
    - 6.1 Color Palette (Primary, Secondary, Accent)
    - 6.2 Typography (Poppins & Inter)
    - 6.3 Visual Design Language
7.  [UI/UX Design Mockups & Wireframes](#-uiux-design-mockups--wireframes)
    - 7.1 Dashboard Screen
    - 7.2 Food Planner & Meal Suggestions Screen
    - 7.3 Health Check-up Modal
8.  [REST API Specification Document](#-rest-api-specification-document)
    - 8.1 Global Standards & Headers
    - 8.2 Authentication & User Profile Endpoints
    - 8.3 Health Vitals Tracking Endpoints
    - 8.4 Food & Meal Planner Endpoints
    - 8.5 Analytics & Reports Endpoints
    - 8.6 Full HTTP Status Codes Reference
9.  [Database Schema (MySQL / PostgreSQL)](#-database-schema-mysql--postgresql)
    - 9.1 Entity Relationship Diagram (ERD) Description
    - 9.2 SQL Data Definition Language (DDL) Scripts
10. [Frontend Architecture & State Management](#-frontend-architecture--state-management)
    - 10.1 JavaScript Logic Flow (The "State" Object)
    - 10.2 DOM Manipulation & Event Delegation
    - 10.3 Data Persistence (localStorage)
11. [Security, Privacy & Compliance](#-security-privacy--compliance)
    - 11.1 HIPAA-Compliant Data Handling
    - 11.2 AES-256 Encryption Standards
    - 11.3 JWT Token Validation
12. [Deployment & Hosting Guide](#-deployment--hosting-guide)
    - 12.1 GitHub Pages (Static Hosting)
    - 12.2 Vercel / Netlify Deployment
    - 12.3 Docker Containerization (Future)
13. [Testing Strategy & Quality Assurance](#-testing-strategy--quality-assurance)
    - 13.1 Unit Testing (Jest / Vitest)
    - 13.2 Integration Testing
    - 13.3 User Acceptance Testing (UAT)
14. [Development Roadmap & Milestones](#-development-roadmap--milestones)
15. [Contribution Guidelines](#-contribution-guidelines)
16. [License & Acknowledgements](#-license--acknowledgements)
17. [Contact & Support](#-contact--support)

---

## 1. Project Overview & Mission

**NutriPulse** is an intelligent, AI-driven health tracking and personalized meal planning application. It addresses the critical confusion people face when trying to align their diet with specific medical conditions (like Diabetes, Hypertension, or PCOS) and fitness goals.

**Core Mission:** To provide a seamless, one-stop solution where users can log daily vitals (Weight, Blood Pressure, Glucose, BMI) and receive dynamic, macro-accurate meal recommendations that adapt to their real-time health data.

**Key Value Proposition:**
- **Personalization:** Meal suggestions based on calorie targets and medical history.
- **Simplicity:** Minimalist, high-contrast UI suitable for all age groups.
- **Actionable Insights:** Visual weekly/monthly progress reports and a dynamic health score.

---

## 2. Business Requirements Document (BRD)

### 2.1 Project Goals & Objectives
- Provide seamless health vitals tracking (Weight, BP, Glucose, Water, Steps).
- Generate customized daily meal plans based on user health conditions.
- Deliver visual health trends and progress reports (Weekly/Monthly).
- Ensure 99.9% uptime with secure cloud database syncing.

### 2.2 Target Audience
- **Fitness Enthusiasts & Gym-goers** seeking macro tracking.
- **Individuals with Chronic Conditions** (Diabetes, Hypertension, PCOS, High Cholesterol).
- **Busy Professionals** requiring simple, quick diet planning and habit tracking.

### 2.3 Functional Requirements Matrix

| Module | Functional Requirement | Description |
| :--- | :--- | :--- |
| **Authentication** | User Onboarding | Email/Phone/Google Sign-in, Health Profile Creation (Age, Gender, Medical History, Goals). |
| **Health Tracker** | Vital Logging | Daily log for Weight, Blood Pressure, Sugar Levels, Water Intake, Steps. |
| **Diet Planner** | Meal Suggestions | Breakfast, Lunch, Snack, Dinner suggestions based on daily calorie target & macros. |
| **Analytics** | Graphical Reports | Weekly/Monthly health trends, BMI gauge, calorie burn vs intake charts. |
| **Notifications** | Smart Reminders | Water intake reminder, meal time alerts, health check-up log alerts. |

### 2.4 Non-Functional Requirements
- **Performance:** App response time < 2 seconds for UI actions.
- **Security:** HIPAA-compliant data handling; AES-256 encryption for sensitive health logs.
- **Usability:** Minimalist, high contrast UI (accessible for all age groups).
- **Availability:** 99.9% uptime with cloud database syncing.

---

## 3. Scope of Work (SOW)

### 3.1 In-Scope (Phase 1)
- User Authentication & Profile Setup.
- Manual Health Vitals logging (Weight, BP, Water, Calories).
- Calorie & Macro Calculator (BMR/TDEE calculation).
- Automated meal suggestions database (Veg, Non-Veg, Keto, Low Carb).
- Weekly progress charts & PDF export option.

### 3.2 Out-of-Scope (Phase 2 & Beyond)
- Real-time Wearable Integration (Apple HealthKit / Google Fit sync).
- Direct 1-on-1 Nutritionist video consultation.
- AI Grocery List generator with delivery app integration (e.g., Blinkit / Instamart API).

---

## 4. System Architecture & Data Flow Diagrams (DFD)

### 4.1 DFD Level 0 (Context Diagram)

```
                       +-------------------+
                       |    Wearable/Fit   |
                       |    Devices API    |
                       +---------+---------+
                                 | (Health Vitals Data)
                                 v
+--------------+        +-------------------+        +-------------------+
|              |------> |                   |------> |                   |
|     User     |        |   NutriPulse App  |        |    Nutrition &    |
|              |<------ |      System       |------- |   Health Database |
+--------------+        +-------------------+        +-------------------+
  (Inputs Vitals,          (Generates Meal              (Fetch Calorie &
   Meal Logs)               Plans & Analytics)           Recipe Specs)
```

### 4.2 DFD Level 1 (Process Breakdown)

```
                  +-----------------------------------+
                  |  1.0 User Auth & Profile Manager  |
                  +-----------------+-----------------+
                                    |
                                    v
+--------------+  Logs Vitals  +----+------------------+  Generates Plan  +------------------+
|     User     |-------------> |  2.0 Vitals Tracker   |----------------> | 3.0 Meal Engine  |
+--------------+               +----+------------------+                  +--------+---------+
       ^                            |                                              |
       |                            v                                              v
       |                     [ D1: Vitals DB ]                             [ D2: Recipe DB ]
       |                                                                           |
       |                         Pushes Alerts & Reports                           |
       +---------------------------------------------------------------------------+
                                   4.0 Analytics & Alerts
```

### 4.3 Technology Stack Architecture
- **Frontend:** HTML5, CSS3, Vanilla JavaScript (Single File Application).
- **State Management:** In-memory `state` object persisted via `localStorage`.
- **API Integration:** RESTful endpoints (mock or real) consuming JSON.
- **Hosting:** GitHub Pages / Netlify / Vercel.

---

## 5. Information Architecture & Sitemap

```
NutriPulse App
├── 1. Onboarding / Auth
│   ├── Login / Register
│   └── Profile Setup (Age, Weight, Target Goal, Medical Alerts)
├── 2. Dashboard (Home)
│   ├── Daily Vitals Summary (Water, Calories, Steps)
│   ├── Quick Log (+ Meal, + Water, + Vital)
│   └── Today's Meal Plan Preview
├── 3. Health Check-up & Logs
│   ├── Vital Logging (BP, Glucose, Weight)
│   ├── Health Assessment Score
│   └── History & Trend Graphs
├── 4. Food Planner
│   ├── Daily Meal Breakdown (Breakfast, Lunch, Dinner, Snacks)
│   ├── Recipe Detail & Macro Breakdown (Carbs, Protein, Fats)
│   └── Calorie Counter & Water Tracker
└── 5. Profile & Settings
    ├── Personal Goals
    ├── Dietary Preferences (Veg/Vegan/Keto/Jain)
    └── Security & Data Privacy
```

---

## 6. Style Guide & Mood Board

### 6.1 Color Palette
| Category | Color Name | Hex Code | Purpose |
| :--- | :--- | :--- | :--- |
| **Primary** | Bio Emerald | `#00C853` | Brand identity, primary buttons, success states |
| **Secondary** | Health Cyan | `#00B0FF` | Water tracking, metric badges, progress bars |
| **Accent** | Calorie Coral | `#FF6D00` | Food/Meal tags, energetic highlights, notifications |
| **Background Light** | Slate Pure | `#F8FAFC` | App light theme main background |
| **Background Dark** | Midnight Navy | `#0F172A` | App dark theme main background |
| **Text Primary** | Deep Charcoal | `#1E293B` | Main headings, body text (Light mode) |

### 6.2 Typography
- **Primary Font:** `Poppins` (Sans-serif) for Headings.
- **Secondary Font:** `Inter` (Sans-serif) for Body Text.
- **Headings:** Poppins Semi-Bold (H1: 24px, H2: 20px, H3: 16px).
- **Body Text:** Inter Regular (14px, Line height: 1.5).
- **Captions/Badges:** Inter Medium (12px).

### 6.3 Visual Design Language
- **Theme:** Clean, Energetic, Calm, and Trustworthy.
- **Layout:** Minimalist modern layout with curved cards, soft drop-shadows, and bright accent elements for fitness motivation.

---

## 7. UI/UX Design Mockups & Wireframes

### 7.1 Dashboard Screen (ASCII Wireframe)
```
+---------------------------------------------------+
|  [≡]  NutriPulse             [Profile] [🔔]      |
+---------------------------------------------------+
|  Hello Raj! 👋                                    |
|  "Your health score is 85/100 today."              |
|                                                   |
|  +---------------------------------------------+  |
|  | TODAY'S OVERVIEW                            |  |
|  |  Calories: 1,450 / 2,100 kcal [======---]   |  |
|  |  Water:    2.1 L / 3.5 L     [====------]   |  |
|  |  Steps:    6,420 / 10,000   [======----]   |  |
|  +---------------------------------------------+  |
|                                                   |
|  QUICK HEALTH CHECK-UP                            |
|  [ + Log BP ]   [ + Log Glucose ]   [ + Weight ]  |
|                                                   |
|  TODAY'S MEAL RECOMMENDATION                      |
|  +---------------------------------------------+  |
|  | 🥣 Lunch (450 kcal)                         |  |
|  | Grilled Paneer Salad + Oats Chapati          |  |
|  | High Protein | Low Glycemic                  |  |
|  | [ View Recipe ]             [ Mark Eaten ]  |  |
|  +---------------------------------------------+  |
|                                                   |
|  [ Home ]    [ Health ]    [ Diet ]    [ Reports ]|
+---------------------------------------------------+
```

### 7.2 Food Planner & Meal Suggestions Screen (ASCII Wireframe)
```
+---------------------------------------------------+
|  [←]  Food & Diet Planner            [ Calendar ] |
+---------------------------------------------------+
|  Select Preference: [ Veg (Active) ] [ Non-Veg ]  |
|                                                   |
|  MACRO NUTRIENT TARGET                            |
|  Protein: 80g | Carbs: 180g | Fat: 45g           |
|                                                   |
|  MEAL SCHEDULE                                    |
|  +---------------------------------------------+  |
|  | 🌅 Breakfast (8:30 AM)               320 kcal |  |
|  | Sprouts Salad + Almond Milk                 |  |
|  | status: Logged [✓]                          |  |
|  +---------------------------------------------+  |
|  | ☀️ Lunch (1:30 PM)                  550 kcal |  |
|  | Brown Rice, Dal Tadka, Tofu Stir-Fry        |  |
|  | [ + Log Meal ]                              |  |
|  +---------------------------------------------+  |
|  | 🌙 Dinner (8:00 PM)                 400 kcal |  |
|  | Vegetable Soup + Multigrain Toast           |  |
|  | [ + Log Meal ]                              |  |
|  +---------------------------------------------+  |
|                                                   |
|  [ Swap Meal ]            [ Generate New Plan ]   |  |
+---------------------------------------------------+
```

---

## 8. REST API Specification Document

**Base URL:** `https://api.nutripulse.health/api/v1`  
**Data Format:** `application/json`

### 8.1 Global Standards & Headers
- `Content-Type: application/json`
- `Authorization: Bearer <JWT_TOKEN>` (Required for all protected endpoints)

**Standard Success Response:**
```json
{
  "success": true,
  "message": "Operation completed successfully",
  "data": {}
}
```

**Standard Error Response:**
```json
{
  "success": false,
  "error": {
    "code": "INVALID_INPUT",
    "message": "Detailed error message here",
    "details": []
  }
}
```

### 8.2 Authentication & User Profile Endpoints

#### 8.2.1 User Registration
- **Endpoint:** `POST /auth/register`
- **Access:** Public
- **Request Body:**
```json
{
  "name": "Raj Kumar",
  "email": "raj@example.com",
  "password": "SecurePassword123!",
  "gender": "male",
  "dob": "1998-05-15",
  "height_cm": 175,
  "current_weight_kg": 78.5,
  "target_weight_kg": 70.0,
  "health_conditions": ["hypertension", "prediabetes"],
  "dietary_preference": "vegetarian",
  "activity_level": "moderate"
}
```
- **Response (201 Created):**
```json
{
  "success": true,
  "message": "Registration successful",
  "data": {
    "user_id": "usr_987654321",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "bmr": 1720,
    "daily_calorie_target": 2100
  }
}
```

#### 8.2.2 User Login
- **Endpoint:** `POST /auth/login`
- **Access:** Public
- **Request Body:**
```json
{ "email": "raj@example.com", "password": "SecurePassword123!" }
```
- **Response (200 OK):** Returns `user_id`, `name`, and `JWT token`.

#### 8.2.3 Get / Update Profile
- **Endpoint:** `GET /user/profile` | `PUT /user/profile`
- **Access:** Protected (JWT)
- **PUT Request Body:**
```json
{
  "target_weight_kg": 68.0,
  "activity_level": "active",
  "dietary_preference": "keto"
}
```

### 8.3 Health Vitals Tracking Endpoints

#### 8.3.1 Log Daily Vitals
- **Endpoint:** `POST /vitals/log`
- **Access:** Protected (JWT)
- **Request Body:**
```json
{
  "log_date": "2026-08-13",
  "blood_pressure": { "systolic": 120, "diastolic": 80 },
  "blood_sugar_mg_dl": 105,
  "weight_kg": 77.8,
  "water_intake_ml": 2500,
  "step_count": 6420
}
```
- **Response (201 Created):**
```json
{
  "success": true,
  "data": { "vital_log_id": "vtl_10293847", "health_score": 85, "warnings": [] }
}
```

#### 8.3.2 Get Vitals History
- **Endpoint:** `GET /vitals/history?start_date=2026-08-01&end_date=2026-08-13&metric=bp`
- **Access:** Protected (JWT)

### 8.4 Food & Meal Planner Endpoints

#### 8.4.1 Get Daily Meal Plan
- **Endpoint:** `GET /meals/plan?date=2026-08-13`
- **Access:** Protected (JWT)
- **Response (200 OK):** Contains `total_calories`, `target_macros`, and an array of `meals` with `meal_id`, `type`, `time`, `title`, `calories`, `is_logged`.

#### 8.4.2 Log Consumed Meal
- **Endpoint:** `POST /meals/log`
- **Request Body:**
```json
{
  "meal_id": "ml_lunch_02",
  "consumed_time": "2026-08-13T13:45:00Z",
  "portion_factor": 1.0
}
```

#### 8.4.3 Swap Alternative Meal
- **Endpoint:** `POST /meals/swap`
- **Description:** Provides a macro-equivalent option.
- **Request Body:**
```json
{ "meal_id": "ml_lunch_02", "reason": "Out of Tofu" }
```

### 8.5 Analytics & Reports Endpoints

#### 8.5.1 Get Health Summary
- **Endpoint:** `GET /analytics/summary?period=weekly`
- **Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "period": "weekly",
    "avg_daily_calories": 1980,
    "avg_water_intake_ml": 2800,
    "weight_change_kg": -0.7,
    "compliance_rate_percent": 88
  }
}
```

#### 8.5.2 Export PDF Report
- **Endpoint:** `GET /analytics/export-pdf?month=2026-07`
- **Response Header:** `Content-Type: application/pdf`

### 8.6 Full HTTP Status Codes Reference

| Code | Status | Usage Context |
| :--- | :--- | :--- |
| **200** | `OK` | Request Successful (GET, PUT) |
| **201** | `Created` | Resource Successfully Created (POST) |
| **400** | `Bad Request` | Validation Error / Missing required fields |
| **401** | `Unauthorized` | Missing or expired JWT token |
| **403** | `Forbidden` | Accessing unauthorized user resources |
| **404** | `Not Found` | Endpoint/Resource unavailable |
| **500** | `Internal Server Error` | Server database or service failure |

---

## 9. Database Schema (MySQL / PostgreSQL)

### 9.1 Entity Relationship Diagram (ERD) Description

The database consists of 7 core tables:

1.  `users` – Stores authentication and static profile data.
2.  `user_profiles` – Stores dynamic health metrics (height, weight goals, conditions).
3.  `vitals_logs` – Stores daily measurements (BP, Sugar, Water, Steps).
4.  `meals` – Master list of all available meals with nutritional values.
5.  `meal_plans` – Associative table linking users to daily meal schedules.
6.  `meal_logs` – Tracks which meals the user actually consumed.
7.  `health_reports` – Stores generated weekly/monthly summary reports.

### 9.2 SQL Data Definition Language (DDL) Scripts

```sql
-- Table: users
CREATE TABLE users (
    user_id VARCHAR(20) PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    full_name VARCHAR(100),
    phone VARCHAR(20),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Table: user_profiles
CREATE TABLE user_profiles (
    profile_id VARCHAR(20) PRIMARY KEY,
    user_id VARCHAR(20) NOT NULL,
    gender ENUM('male', 'female', 'other'),
    dob DATE,
    height_cm DECIMAL(5,2),
    current_weight_kg DECIMAL(5,2),
    target_weight_kg DECIMAL(5,2),
    dietary_preference VARCHAR(50),
    activity_level VARCHAR(50),
    medical_conditions JSON, -- array of strings
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE
);

-- Table: vitals_logs
CREATE TABLE vitals_logs (
    log_id VARCHAR(20) PRIMARY KEY,
    user_id VARCHAR(20) NOT NULL,
    log_date DATE NOT NULL,
    systolic INT,
    diastolic INT,
    blood_sugar_mg_dl DECIMAL(5,2),
    weight_kg DECIMAL(5,2),
    water_intake_ml INT,
    step_count INT,
    FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE
);

-- Table: meals
CREATE TABLE meals (
    meal_id VARCHAR(20) PRIMARY KEY,
    title VARCHAR(100) NOT NULL,
    description TEXT,
    calories INT NOT NULL,
    protein_g DECIMAL(5,2),
    carbs_g DECIMAL(5,2),
    fat_g DECIMAL(5,2),
    category VARCHAR(50), -- breakfast, lunch, dinner, snack
    dietary_tags JSON -- ['veg', 'keto', 'gluten-free']
);

-- Table: meal_plans
CREATE TABLE meal_plans (
    plan_id VARCHAR(20) PRIMARY KEY,
    user_id VARCHAR(20) NOT NULL,
    plan_date DATE NOT NULL,
    meal_id VARCHAR(20) NOT NULL,
    time_slot VARCHAR(20),
    FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE,
    FOREIGN KEY (meal_id) REFERENCES meals(meal_id)
);

-- Table: meal_logs
CREATE TABLE meal_logs (
    log_id VARCHAR(20) PRIMARY KEY,
    user_id VARCHAR(20) NOT NULL,
    meal_plan_id VARCHAR(20) NOT NULL,
    consumed_at TIMESTAMP,
    portion_factor DECIMAL(3,2) DEFAULT 1.0,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (meal_plan_id) REFERENCES meal_plans(plan_id)
);

-- Table: health_reports
CREATE TABLE health_reports (
    report_id VARCHAR(20) PRIMARY KEY,
    user_id VARCHAR(20) NOT NULL,
    report_period VARCHAR(20), -- 'weekly', 'monthly'
    start_date DATE,
    end_date DATE,
    pdf_path VARCHAR(255),
    generated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## 10. Frontend Architecture & State Management

### 10.1 JavaScript Logic Flow (The `state` Object)

The entire application runs on a single, centralized `state` object:

```javascript
let state = {
  calories: 1450,
  targetCalories: 2100,
  water: 2.1,
  targetWater: 3.5,
  steps: 6420,
  targetSteps: 10000,
  meals: {
    breakfast: { logged: true, desc: 'Sprouts Salad + Almond Milk', calories: 320 },
    lunch: { logged: false, desc: 'Brown Rice, Dal Tadka, Tofu', calories: 550 },
    dinner: { logged: false, desc: 'Veg Soup + Multigrain Toast', calories: 400 }
  },
  healthScore: 85
};
```

**Flow of Operations:**
1.  **User Action (e.g., Log Meal):** Triggers an event listener.
2.  **State Update:** The `logMeal()` function modifies the `state` object (updates `calories` and `meals.logged`).
3.  **UI Re-rendering:** `updateMealUI()` changes button styles and text.
4.  **Dashboard Sync:** `updateDashboard()` recalculates progress bar widths and updates DOM elements (`.textContent`, `.style.width`).
5.  **Persistence:** `localStorage.setItem('nutripulse_state', JSON.stringify(state))` is called to save data.

### 10.2 DOM Manipulation & Event Delegation
- All buttons use `addEventListener` attached directly to specific elements (e.g., `lunchLogBtn`).
- The Modal is dynamically generated using `innerHTML` based on the selected vital type (`bp`, `glucose`, `weight`).
- Input validation ensures positive numeric values (e.g., `parseFloat(val1) < 0` triggers an error toast).

### 10.3 Data Persistence (localStorage)
On app load, the script checks for `localStorage.getItem('nutripulse_state')`. If found, it parses the JSON and merges it with the default state, ensuring the user's progress is not lost between sessions.

---

## 11. Security, Privacy & Compliance

### 11.1 HIPAA-Compliant Data Handling
Although the current prototype runs fully on the client-side, the architectural design follows HIPAA guidelines by ensuring:
- All data transmission happens over HTTPS.
- Data is never stored in plain text within the code.
- Sensitive user inputs (like medical history) are handled strictly on the client side until a secure backend is integrated.

### 11.2 AES-256 Encryption Standards
The specification mandates that all health logs stored in the backend database will be encrypted using AES-256. For the frontend prototype, `localStorage` is used, but production versions will replace this with encrypted cloud storage.

### 11.3 JWT Token Validation
All protected API endpoints (as specified in Section 8) require a valid JWT token passed in the `Authorization` header. The token is generated upon successful login and verified on each request to prevent unauthorized access.

---

## 12. Deployment & Hosting Guide

### 12.1 GitHub Pages (Static Hosting)
1.  Push your code to a GitHub repository (e.g., `https://github.com/Rg100152/NutriPulse`).
2.  Go to the repository **Settings** > **Pages**.
3.  Set the branch to `main` and the folder to `/root`.
4.  Your app will be live at `https://rg100152.github.io/NutriPulse`.

### 12.2 Vercel / Netlify Deployment
1.  Drag and drop the `index.html` file onto the Netlify/Vercel deployment dashboard.
2.  The platform automatically assigns a live HTTPS URL.

### 12.3 Docker Containerization (Future)
A `Dockerfile` and `nginx.conf` will be provided to serve the static file via a lightweight Nginx container for production-grade deployment.

---

## 13. Testing Strategy & Quality Assurance

### 13.1 Unit Testing (Jest / Vitest)
Focus on pure functions like `updateDashboard()`, `logMeal()`, and `swapMeal()`. These functions will be isolated to test state mutations independently.

### 13.2 Integration Testing
Testing the interaction between the DOM and the `state` object. For example, simulating a button click and verifying that the DOM text updates correctly.

### 13.3 User Acceptance Testing (UAT)
- **Test Case 1:** Log a meal and verify the calories increase.
- **Test Case 2:** Swap a meal and verify the description changes.
- **Test Case 3:** Refresh the page and verify the data persists.
- **Test Case 4:** Log negative values in the modal and verify error handling.

---

## 14. Development Roadmap & Milestones

| Milestone | Status | Estimated Completion |
| :--- | :--- | :--- |
| **Phase 1: MVP (Single File HTML)** | ✅ **Complete** | Aug 2026 |
| Phase 2: Backend & Database Integration | 🔜 In Progress | Q4 2026 |
| Phase 3: Advanced Analytics & Charts | 📅 Planned | Q1 2027 |
| Phase 4: Wearable API Sync (Apple/Google) | 📅 Planned | Q2 2027 |
| Phase 5: AI Grocery List & Delivery Integration | 📅 Planned | Q3 2027 |

---

## 15. Contribution Guidelines

We welcome contributions to make NutriPulse better for everyone!

1.  **Fork** the repository.
2.  **Create a feature branch:** `git checkout -b feature/AmazingFeature`.
3.  **Commit your changes:** `git commit -m 'Add some AmazingFeature'`.
4.  **Push to the branch:** `git push origin feature/AmazingFeature`.
5.  **Open a Pull Request** with a clear description of your changes.

**Coding Standards:**
- Use 2 spaces for indentation.
- Keep functions small and focused.
- Comment complex logic (especially DOM manipulation and state updates).

---

## 16. License & Acknowledgements

### License
This project is licensed under the **MIT License**. See the `LICENSE` file for more details.

### Acknowledgements
- **Unsplash** – For providing high-quality, free-to-use stock photography (every image used in this project is sourced from Unsplash and is unique to this release).
- **Font Awesome** – For the extensive icon library.
- **Google Fonts** – For the Inter and Poppins typefaces.
- **Gemini AI** – For assisting in the documentation and architectural design.

---

## 17. Contact & Support

- **Author:** Raj Kumar
- **GitHub:** [@Rg100152](https://github.com/Rg100152)
- **Project Repository:** [https://github.com/Rg100152/NutriPulse](https://github.com/Rg100152/NutriPulse)
- **Live Demo:** [https://rg100152.github.io/NutriPulse](https://rg100152.github.io/NutriPulse)

For any issues, feature requests, or general feedback, please open an issue on the GitHub repository.

---

> *"One‑stop health tracking + real‑time dynamic meal recommendations."*  
> *– NutriPulse, built with ❤️ for a healthier you.*
```

