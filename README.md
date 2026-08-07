# LifeSignal
> **Spot the small shifts before they become big problems.**

LifeSignal is a personal early-warning system powered by client-side explainable intelligence. It accepts messy, unstructured daily logs (expenses, sleep patterns, study hours, health symptoms, mood checks) and instantly structures them, computes rolling statistical baselines, detects multi-category anomalies, and provides human-friendly explanations with gentle preventive suggestions.

---

## 🚀 Quick Start Guide

### Setup & Run Locally

```bash
# 1. Navigate to the project directory
cd lifesignal

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```

Open `http://localhost:5173` in your browser. The application will load automatically with **40 days of pre-seeded realistic demo data** ready for evaluation.

---

## 🎬 60–90 Second Hackathon Demo Script for Judges

1. **Step 1: Land on Dashboard & View Life Stability Index (0–15s)**
   - Notice the top header with **Life Stability Index (74/100)** and **"Storm Watch Signal"** Risk Weather badge.
   - Look at the **Hero Summary Strip** showing 3 nights of accumulated low sleep debt.

2. **Step 2: Free-Text Smart Ingestion (15–30s)**
   - Click the **"+ Quick Log"** button in the navbar (or press key `N`).
   - Paste or click the sample chip: `"spent 680 on swiggy lunch + ice cream"`.
   - Observe the **Smart Parser Confirmation Card** extract: Category: *Expenses*, Amount: *₹680*, Subcategory: *Food Delivery*, Confidence: *92%*.
   - Click **Confirm & Analyze**. See instant toast notification: *"Logged & analyzed in 0.1s ✨"*.

3. **Step 3: Multi-Category Anomaly Detection (30–45s)**
   - Navigate to **Insights & Anomalies** (or click **"Demo Story"** in the top navbar).
   - Review the Critical Multi-Signal card: **"Sleep Debt → Spend Spike → Focus Slump"**.
   - Click **"View Data Evidence & Statistics"** to inspect exact bullet points showing short sleep streak (4.5h avg vs 7.4h baseline), ₹1,860 food delivery surge, and -60% study drop.
   - Toggle **"Explain like I'm busy" (Short Mode)** to show quick judge overview.

4. **Step 4: Patterns & Correlations Lab (45–60s)**
   - Go to **Patterns & Correlations**.
   - View the **Personal Baseline Passport** displaying 30-day normal bounds.
   - Review discovered lag correlations: *"When sleep is <6.0h, next-day food delivery spend increases by 140%"*.

5. **Step 5: Printable Weekly Digest & Counselor Share (60–90s)**
   - Navigate to **Reports & Export**.
   - Toggle between **7-day** and **30-day** digests.
   - Click **"Share Summary"** to see the privacy-safe mentor/counselor summary copy tool.
   - Click **"Print PDF"** to test the clean `@media print` layout.

---

## ✨ Core Implemented Features Mapped to Problem Statement

| Problem Requirement | Implementation Details |
| :--- | :--- |
| **Unstructured Data Ingestion** | Free-text NLP smart parser with regex & keyword extraction + confidence scores + Structured Form + Bulk Paste. |
| **Anomaly Detection Engine** | 7/14/30-day rolling mean, median, standard deviation calculation + multi-category cross-correlation rules. |
| **Plain-Language Explanations** | Human-friendly text templates explaining what changed, compared to baseline, why it matters, and preventive actions. |
| **Life Stability Index (0-100)** | Composite weighted index reflecting sleep debt, spend variance, focus consistency, and active anomalies. |
| **Risk Weather Metaphor** | Clear / Cloudy / Storm Watch states with contextual indicators. |
| **Category Explorer** | Subcategory pie/bar charts, sleep debt estimator, focus burnout detector, 30-day Mood Heatmap Calendar. |
| **Preventive Action Playbooks** | Step-by-step actionable advice mapped to sleep debt, impulse spending, study burnout, and recurring headache triggers. |
| **Private & Offline-First** | 100% client-side execution using browser `localStorage` — no login, auth, cloud DB, or tracking scripts required. |
| **Settings & Controls** | Adjustable anomaly sensitivity (Relaxed, Balanced, Strict), export/import JSON backups, and demo data reload tools. |

---

## 🏗️ Technical Architecture & Design Principles

```
src/
├── components/
│   ├── common/         # StatCard, SeverityBadge, ProgressRing, Toast, Modal, EmptyState
│   ├── layout/         # Navbar, Sidebar, MobileNav, DemoStoryBanner
│   ├── dashboard/      # HeroStrip, NeedsAttention, CategoryHealthCards, SparklineSection, RecentTimeline
│   ├── forms/          # SmartInputModal, QuickAddChips, StructuredForm, BulkPasteForm
│   ├── insights/       # AnomalyCard
│   ├── categories/     # CategoryExplorer, MoodHeatmap
│   ├── patterns/       # PatternsPage, BaselinePassport
│   ├── alerts/         # AlertsWatchlist
│   ├── reports/        # ReportsPage, ShareModal
│   └── settings/       # SettingsPage
├── context/
│   └── LifeSignalContext.jsx   # Central React state provider & hooks
├── data/
│   ├── demoData.js             # 40 days of realistic sample logs relative to current date
│   ├── thresholds.js           # Sensible default thresholds & category metadata
│   └── tipLibrary.js           # Preventive action playbooks library
├── features/
│   ├── parser/smartParser.js           # Free-text NLP & regex parser
│   ├── anomalyEngine/engine.js         # Rolling baselines & anomaly rules engine
│   ├── reports/reportGenerator.js      # Weekly/Monthly report compiler & privacy summary
│   └── storage/localStorage.js         # Browser persistence & JSON backup validator
├── pages/              # SPA route page views
├── App.jsx             # Main router & global keyboard shortcuts
└── index.css           # Tailwind CSS v4 setup & custom utilities
```

### Key Technical Decisions
1. **React Functional Components + Hooks (JavaScript)**: Built strictly without TypeScript as requested.
2. **Local Browser Persistence**: State automatically syncs with `localStorage` (`lifesignal_app_data_v1`).
3. **Tailwind CSS v4 + Recharts**: Modern glassmorphism dark theme UI with sleek responsive charts and micro-animations.
4. **Offline Capability**: Operates fully offline after load.

---

## 🛡️ Privacy & Societal Impact Statement

Early self-awareness can dramatically reduce burnout, financial stress, and delayed medical attention. LifeSignal puts user privacy first: **all processing happens client-side**. Data never leaves the browser.
