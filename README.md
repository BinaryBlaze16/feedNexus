# FeedNexus – Personalized Content Dashboard

[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=black)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Redux Toolkit](https://img.shields.io/badge/Redux%20Toolkit-2.8-764ABC?logo=redux&logoColor=white)](https://redux-toolkit.js.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.4-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)

An interactive, responsive **Personalized Content Dashboard** built for users to track, customize, and interact with curated content feeds (News, Recommendations, and Social Media) in a dynamic interface.

---

## 📑 Documentation

A comprehensive, detailed PDF report covering the full system architecture, API resilience strategies, state flow, testing matrix, and evaluation criteria is available in the repository:
- **[Personalized_Content_Dashboard_Documentation.pdf](./Personalized_Content_Dashboard_Documentation.pdf)**

---

## 🚀 Key Features

### 📰 1. Multi-Source Personalized Content Feed
- **Multi-API Ingestion:** Real-time news via **NewsAPI**, movie/media recommendations (TMDB format), and social media streams.
- **Dynamic Category Filtering:** Customize feeds by selecting favorite topics (Technology, Finance, Sports, Science, Environment, Entertainment).
- **Graceful Degradation:** Automatic fallback to high-fidelity mock datasets if external API rate limits are reached.

### 🃏 2. Interactive Content Cards
- **Rich Media & Metadata:** Source indicators, dynamic category badges, and relative timestamps (*"Just now"*, *"2h ago"*, *"Yesterday"*).
- **Interactive States:** Favorite/bookmark toggle with instant UI feedback and direct CTA buttons (*"Read More"*).
- **Image Lazy Loading:** Progressive loading with shimmer skeleton placeholders to prevent layout shift.

### 🧩 3. Dashboard Layout & Navigation
- **Responsive Navigation Sidebar:** Easy switching between **Feed**, **Trending**, and **Favorites** views.
- **Top Navigation Header:** Quick search input, dark mode toggle, notification indicator, and user profile management.
- **View Toggle:** Seamlessly switch between **Grid** and **List** layout modes.

### 🔍 4. Optimized Real-Time Search
- **Debounced Search Engine:** 300ms debounce prevents redundant requests and optimizes client/server performance.
- **Quick Discovery:** Surfaces recent searches and trending tags for fast navigation.

### 🖐️ 5. Drag-and-Drop Feed Organization
- Integrated with `@dnd-kit/sortable` for smooth card reordering.
- Hardware-accelerated transitions and automatic Redux state synchronization.

### 🧠 6. State Management & Persistence
- **Redux Toolkit Architecture:** Centralized state across `contentSlice`, `userPreferencesSlice`, and `uiSlice`.
- **LocalStorage Sync:** Saves dark mode, user categories, layout, and favorited items across page reloads.

### 🌙 7. Dark Mode & Accessibility
- Instant theme toggle with CSS custom properties and Tailwind dark classes.
- High-contrast color tokens and accessible ARIA components built on Radix UI.

---

## 🛠️ Tech Stack

- **Frontend Core:** React 18, TypeScript, Vite
- **State Management:** Redux Toolkit, Redux Persist (via LocalStorage)
- **Styling & UI:** Tailwind CSS, Radix UI Primitives, Lucide Icons, Class Variance Authority
- **Interactivity:** `@dnd-kit/core`, `@dnd-kit/sortable`
- **APIs:** NewsAPI (`/v2/top-headlines`), RESTful data layer

---

## 📂 Project Structure

```
personal-feed-nexus/
├── public/                     # Static assets and favicons
├── src/
│   ├── assets/                 # Images and media assets
│   ├── components/             # React UI components
│   │   ├── ui/                 # Reusable Radix / Tailwind UI primitives
│   │   ├── ContentCard.tsx     # Card component with interactive actions
│   │   ├── ContentFeed.tsx     # Aggregated personalized feed
│   │   ├── ContentSkeleton.tsx # Shimmer loading placeholder
│   │   ├── Dashboard.tsx       # Main dashboard layout wrapper
│   │   ├── DragDropProvider.tsx# @dnd-kit drag-and-drop context
│   │   ├── FavoritesSection.tsx# Saved / favorited content view
│   │   ├── Header.tsx          # Top navigation bar
│   │   ├── SearchModal.tsx     # Debounced search dialog
│   │   ├── SettingsModal.tsx   # User preference configuration modal
│   │   ├── Sidebar.tsx         # Responsive navigation sidebar
│   │   └── TrendingSection.tsx # High-velocity trending content view
│   ├── hooks/                  # Custom typed Redux & UI hooks
│   ├── services/               # API clients & mock data providers
│   ├── store/                  # Redux Toolkit store & slice definitions
│   │   ├── slices/             # contentSlice, userPreferencesSlice, uiSlice
│   │   └── store.ts            # Configured Redux store
│   ├── App.tsx                 # Root application component
│   ├── index.css               # Design system tokens & CSS variables
│   └── main.tsx                # Application entry point
├── package.json
├── tsconfig.json
└── vite.config.ts
```

---

## ⚡ Getting Started

### 1. Prerequisites
- **Node.js:** v18.0.0 or higher
- **npm:** v9.0.0 or higher

### 2. Clone and Install

```bash
# Clone the repository
git clone https://github.com/BinaryBlaze16/feedNexus.git

# Navigate into the project folder
cd feedNexus/personal-feed-nexus

# Install dependencies
npm install
```

### 3. Run Development Server

```bash
npm run dev
```
Open [http://localhost:5173](http://localhost:5173) in your browser to view the application.

### 4. Build for Production

```bash
npm run build
npm run preview
```

---

## 🧪 Testing & Quality Assurance

- **Unit Tests:** Validates Redux reducers, selectors, date formatters, and utility helpers.
- **Integration Tests:** Verifies API fetching, category filtering, and favorite state persistence.
- **E2E Testing:** Simulates critical user flows (Live search, drag-and-drop card reordering, theme toggle).

---

## 👤 Author

**Anant Srivastava**
- GitHub: [@BinaryBlaze16](https://github.com/BinaryBlaze16)
- Repository: [feedNexus](https://github.com/BinaryBlaze16/feedNexus)
