# AutoCare Hub 🚗⚡

> **Tagline:** *"Your Car. Your Care. Your Control."*  
> A smart, centralised, and responsive automobile web application built for vehicle maintenance tracking, fuel consumption economics, and expense management.

---

## 🌟 Table of Contents
1. [Project Overview](#project-overview)
2. [Problem Statement & Solution](#problem-statement--solution)
3. [Technology Stack](#technology-stack)
4. [Key Features](#key-features)
5. [Quick Start & Setup Instructions](#quick-start--setup-instructions)
6. [Hackathon Demo Walkthrough Guide](#hackathon-demo-walkthrough-guide)
7. [Architecture & Important Code Decisions](#architecture--important-code-decisions)
8. [Known Limitations](#known-limitations)
9. [Future Roadmap](#future-roadmap)

---

## 1. Project Overview

**AutoCare Hub** is a modern automotive SaaS web application created for car owners who want to eliminate the guesswork from vehicle maintenance and running costs. It provides real-time service interval calculations, automated reminders based on calendar dates and odometer readings, an interactive fuel and trip-cost calculator with two-vehicle savings comparisons, comprehensive expense analytics, and an explainable rules-based Smart Insights engine.

The application runs **100% locally in the browser**, requiring no external databases, no paid API keys, and no user tracking.

---

## 2. Problem Statement & Solution

* **The Problem:**
  * Car owners often miss critical service intervals (engine oil, brake pads, tyre rotations), resulting in avoidable breakdowns and expensive workshop bills.
  * Tracking fuel fills and running costs across physical paper receipts or messy notes makes it hard to see where money goes.
  * Estimating trip costs or deciding which vehicle in the family fleet is more economical for daily commutes requires tedious mental math.

* **The Solution:**
  * **AutoCare Hub** provides a single, unified command center with reactive reminders, visual expenditure charts, deterministic trip calculations, and instant data persistence using browser `localStorage`.

---

## 3. Technology Stack

* **Frontend Framework:** React 18 with Vite
* **Language:** JavaScript (ES6+ with modern modular syntax)
* **Styling & Design System:** Tailwind CSS (Deep navy `#070c18`, dark charcoal `#0f172a`, electric blue `#2563eb`, and cyan `#06b6d4`)
* **Icons:** Lucide React (`lucide-react`)
* **Data Visualisation:** Recharts (Stacked bar charts and Donut breakdown charts)
* **Routing:** React Router v6 (`react-router-dom`)
* **Date Utilities:** `date-fns`
* **Data Persistence:** Browser `localStorage` with JSON export/import and schema validation

---

## 4. Key Features

### 📊 1. Command Center Dashboard
* Real-time KPI statistics: registered vehicles, scheduled maintenance status, total recorded expenses, and fuel outlay.
* Interactive Recharts monthly expense trend chart (Fuel, Servicing, Upkeep).
* Status summary cards (Overdue, Due within 14 days, Upcoming, Completed).
* Quick-action buttons to instantly add vehicles, log services, or record expenses.

### 🚙 2. My Garage (Vehicle Management)
* Add, edit, and delete vehicles with confirmation dialogs.
* Supports **Petrol, Diesel, Electric, Hybrid, and CNG** with custom badges.
* Stores vehicle nickname, manufacturer, model, year, registration number, current odometer, average mileage, and notes.
* Filter vehicles by fuel type.
* **Privacy Assurance:** Vehicle numbers stay strictly inside the browser sandbox.

### 🔧 3. Maintenance Manager & Service Reminders
* Pre-configured service intervals for 9 categories:
  * Engine Oil (10,000 km / 180 days)
  * Oil Filter (10,000 km / 180 days)
  * Air Filter (15,000 km / 365 days)
  * Tyres & Alignment (10,000 km / 180 days)
  * Brake Pads & Fluid (20,000 km / 365 days)
  * Battery Health (730 days)
  * Coolant Flush (30,000 km / 730 days)
  * General Servicing (10,000 km / 180 days)
  * Other Custom Services
* Automatic status evaluation: **Overdue**, **Due soon** (within 14 days or 500 km), **Upcoming**, and **Completed**.
* Clear, transparent reasons provided for every reminder (e.g. *"Odometer exceeded target by 500 km"* or *"Due in 8 days"*).
* One-click "Mark Completed" action that updates vehicle service dates and odometer baselines.
* In-app Reminder Center accessible from any page via the notification bell.

### ⛽ 4. Fuel & Trip Economics Calculator
* Calculate fuel requirements, total journey cost, and cost per kilometre.
* Supports one-way, return (round trip), and multi-trip multipliers.
* **Exact Verification Match:**
  * Distance: `300 km`
  * Mileage: `15 km/L`
  * Fuel Price: `₹105 / Litre`
  * **Result:** `20 Litres` required, `₹2,100` estimated cost, `₹7.00 / km`.
* Step-by-step formula transparency card explaining the exact arithmetic.

### ⚖️ 5. Two-Vehicle Savings Comparison
* Compare two vehicles (e.g., Honda City Petrol @ 15 km/L vs. Hyundai Creta Diesel @ 18.5 km/L).
* Computes single trip difference, monthly fuel difference, and projected annual savings based on monthly commute frequency.
* Visual comparison bar chart comparing trip costs and monthly outlay.

### 💰 6. Vehicle Expense Tracker
* Log expenses across categories: Fuel, Servicing, Repairs, Insurance, Tyres, Washing, Parking, and Other.
* Interactive Donut / Pie chart displaying category percentage distribution.
* Search transactions by description or category.
* Filter by vehicle and sort by date or amount.
* All figures in Indian Rupees (`₹ INR`).

### 💡 7. Smart Insights Engine
* Fully explainable, deterministic rules engine (no black-box AI APIs or fabricated claims).
* Analyzes fleet data to generate actionable insights:
  * Maintenance urgency warnings (e.g., approaching oil changes or overdue brake checks).
  * Spending distribution alerts (e.g., *"Fuel represents 65% of total recorded expenses"*).
  * Fleet efficiency comparisons highlighting the most economical vehicle for daily commutes.
  * Data completeness guidance (e.g., prompt to update odometer when readings are missing).

### ⚙️ 8. Settings & Data Portability
* Toggle between Deep Navy (Dark) and Light themes with instant persistence.
* Export full application data as a timestamped JSON backup.
* Import and validate previously exported JSON backups.
* One-click "Reset Demo Data" for hackathon judging.
* "Wipe All Data" option with confirmation dialog to start with an empty garage.

---

## 5. Quick Start & Setup Instructions

### Prerequisites
* [Node.js](https://nodejs.org/) (v18.0.0 or higher recommended)
* `npm` or `yarn`

### Installation Steps

1. **Clone or navigate to the project directory:**
   ```bash
   cd Niat-1
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

4. **Open in browser:**
   Open [http://localhost:5173](http://localhost:5173) in your browser.

5. **Build for production (optional):**
   ```bash
   npm run build
   npm run preview
   ```

6. **Run verification test suite:**
   ```bash
   node test/verify_app.mjs
   ```

---

## 6. Hackathon Demo Walkthrough Guide

Follow this 3-minute presentation script during hackathon judging:

1. **The Hook (30s):**
   * Introduce yourself as a First-Year Computer Science and Data Science student.
   * State the problem: *"Vehicle owners constantly overspend or suffer breakdowns because service tracking and fuel budgeting are fragmented across paper receipts and mental notes."*
   * Introduce **AutoCare Hub**: *"Your Car. Your Care. Your Control."*

2. **The Garage & Vehicle Specs (45s):**
   * Navigate to **My Garage**. Show the pre-seeded demo cars:
     * **Honda City (2022 Petrol, 28,500 km, 15 km/L)**
     * **Hyundai Creta (2021 Diesel, 42,000 km, 18.5 km/L)**
   * Point out the local privacy notice: registration numbers stay 100% in local browser sandbox.
   * Click **Add Vehicle** to demonstrate client-side form validation.

3. **Maintenance Manager & Reminder Engine (45s):**
   * Navigate to **Maintenance**.
   * Show the real-time status badges:
     * Overdue: Brake pads inspection (target odometer exceeded).
     * Due Soon: Engine oil & filter change (due in ~8 days).
     * Upcoming: Wheel alignment.
   * Click the **Bell Icon** on the top bar to open the **Reminder Center Modal**.
   * Click **"Mark Completed"** on a task — notice how the status updates, the badge counter decreases, and the vehicle's last service date updates instantly.

4. **Fuel Calculator & Savings Comparison (45s):**
   * Open **Fuel Calculator**.
   * Highlight the sample test: **300 km @ 15 km/L @ ₹105/L = 20L, ₹2,100 (₹7/km)**.
   * Toggle **Return Journey** to show dynamic multiplier calculations.
   * Switch to the **Vehicle Comparison** tab: show how choosing the 18.5 km/L Creta over the 15 km/L City saves **~₹7,946 every month** and **~₹95,352 every year** for daily commuters, backed by a comparative Recharts bar chart.

5. **Smart Insights & Settings (30s):**
   * Navigate to **Smart Insights**. Explain that this is a transparent, explainable rules-based intelligence system with *"Why you see this"* cards.
   * Visit **Settings** to demonstrate the Light/Dark mode toggle, the JSON export/import backup feature, and the "Reset Demo Data" button.

---

## 7. Architecture & Important Code Decisions

### Modular Folder Structure
```text
src/
├── components/          # Reusable UI components
│   ├── ConfirmDialog.jsx       # Modal for destructive actions
│   ├── EmptyState.jsx          # Friendly empty states
│   ├── ExpenseModal.jsx        # Form for logging expenses
│   ├── MaintenanceModal.jsx    # Form for scheduling maintenance
│   ├── ReminderCenterModal.jsx # In-app notification center
│   ├── Sidebar.jsx             # Responsive navigation sidebar
│   ├── StatCard.jsx            # KPI metric cards
│   ├── Toast.jsx               # Floating feedback alerts
│   ├── Topbar.jsx              # Header with reminders and theme toggle
│   └── VehicleCard.jsx         # Card displaying vehicle specs & actions
├── context/
│   └── AppContext.jsx          # Global state management and persistence sync
├── data/
│   └── demoData.js             # Realistic seed dataset for hackathon presentation
├── pages/
│   ├── Dashboard.jsx           # Main KPI metrics and recent activity
│   ├── Expenses.jsx            # Category breakdown and transactions
│   ├── FuelCalculatorPage.jsx  # Trip economics and vehicle comparison
│   ├── Garage.jsx              # Vehicle fleet management
│   ├── Insights.jsx            # Deterministic rules-based insight engine
│   ├── Maintenance.jsx         # Service task scheduling and reminders
│   └── Settings.jsx            # Theme, units, JSON export/import
├── utils/
│   ├── calculations.js         # Pure mathematical functions for fuel and savings
│   ├── formatting.js           # Currency (INR), distance, mileage, and date formatting
│   ├── maintenance.js          # Reminder thresholds and status evaluation
│   ├── storage.js              # Safe localStorage read/write with schema validation
│   └── validation.js           # Form input validation rules
├── App.jsx                     # Route definitions and responsive layout wrapper
├── index.css                   # Tailwind CSS base styles and scrollbar styling
└── main.jsx                    # React 18 DOM mount and context provider
```

### Why Deterministic Rules Instead of Black-Box AI?
For automotive safety and maintenance scheduling, deterministic algorithms are superior to probabilistic LLM text generation. A car owner needs exact mathematical truth regarding whether their brake pads have exceeded their 20,000 km threshold or whether their fuel budget is on track.

### Why Client-Side LocalStorage?
* Enables complete offline functionality with zero infrastructure cost.
* Eliminates server cold starts during live hackathon judging.
* Guarantees total privacy for vehicle registration numbers and personal expenditure.

---

## 8. Known Limitations

* **Single-Browser Storage:** Records exist on the user's specific browser until exported to a JSON backup file.
* **Manual Fuel Prices:** Current fuel prices must be entered manually rather than fetched from live oil corporation APIs.
* **Odometer Updates:** Odometer readings are updated manually when logging service or editing vehicle records, rather than via OBD-II Bluetooth telematics.

---

## 9. Future Roadmap

1. **OBD-II Bluetooth Scanner Integration:** Live telemetry reading for vehicle speed, diagnostic trouble codes (DTC), and real-time odometer sync.
2. **PDF Service Report Generation:** Export formatted service booklets for resale documentation.
3. **Receipt OCR:** Camera-based receipt scanner using client-side WebAssembly to auto-fill fuel refill amounts and workshop bills.
4. **Local Workshop Directory:** Integration with OpenStreetMap to find nearby mechanics and puncture shops.

---

**Developed with ❤️ for the Hackathon**  
*AutoCare Hub — Your Car. Your Care. Your Control.*
