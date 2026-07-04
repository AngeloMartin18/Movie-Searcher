<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&amp;color=gradient&amp;customColorList=6,11,20&amp;height=200&amp;section=header&amp;text=Movie%20Tutorial&amp;fontSize=60&amp;fontColor=fff&amp;animation=twinkling&amp;fontAlignY=35&amp;desc=React%20%2B%20Vite%20Movie%20Search%20%26%20Favorites%20App&amp;descAlignY=55&amp;descSize=18" width="100%"/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&amp;size=22&amp;pause=1000&amp;color=7C3AED&amp;center=true&amp;vCenter=true&amp;multiline=true&amp;width=700&amp;height=100&amp;lines=🎬+Search.+Save.+Watch+Later.;⚛️+React+19+%2B+Vite+8;❤️+Favorites+Powered+by+Context+API)](https://git.io/typing-svg)

---

![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-7-CA4245?style=for-the-badge&logo=reactrouter&logoColor=white)
![TMDB](https://img.shields.io/badge/TMDB_API-01D277?style=for-the-badge&logo=themoviedatabase&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-9-4B32C3?style=for-the-badge&logo=eslint&logoColor=white)
![License](https://img.shields.io/badge/License-ISC-7C3AED?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-0.0.0-4F46E5?style=for-the-badge)

</div>

---

## 🧭 About

**Movie Tutorial** is a browser-based movie discovery app built with **React 19** and **Vite**, powered by **The Movie Database (TMDB) API**. Users can browse trending movies, search the full TMDB catalog, and save titles to a personal favorites list that persists across sessions.

The project demonstrates core modern React fundamentals: functional components, hooks (`useState`, `useEffect`, `useContext`), global state via the Context API, client-side routing with React Router, and API integration with async/await — all wired together through a fast Vite dev server.

**Open To** — Contributions, feature extensions (movie detail pages, genre filters, pagination), and forks for educational purposes.

---

## 🛠 Tech Stack

<div align="center">

[![Skills](https://skillicons.dev/icons?i=react,vite,javascript,html,css,git,vscode&theme=dark)](https://skillicons.dev)

</div>

| Layer | Technology |
|---|---|
| **Library** | React 19 (Functional Components + Hooks) |
| **Bundler / Dev Server** | Vite 8 |
| **Routing** | React Router DOM 7 |
| **State Management** | React Context API (`MovieContext`) |
| **Data Source** | TMDB (The Movie Database) REST API |
| **Persistence** | Browser `localStorage` |
| **Styling** | CSS3 (per-component stylesheets) |
| **Linting** | ESLint 9 + `eslint-plugin-react-hooks` |
| **Version Control** | Git |

---

## 🎬 App Architecture

| Concern | Details |
|---|---|
| **Routing** | Two routes — `/` (Home) and `/favorites` (Favorites) — rendered via `react-router-dom` |
| **Movie Data** | `getPopularMovies()` fetches trending titles on mount; `searchPopularMovies(query)` hits the TMDB search endpoint on form submit |
| **Global State** | `MovieProvider` context exposes `favorites`, `addToFavorites`, `removeFromFavorites`, and `isFavorite` to any component |
| **Persistence** | Favorites are synced to `localStorage` on every change and rehydrated on load |
| **Favoriting** | `MovieCard` renders a heart button that toggles a title in/out of favorites without navigating away |
| **Loading & Errors** | `Home` tracks `loading`/`error` state around each async fetch to render spinners or error messages |
| **Empty State** | `Favorites` renders a friendly empty-state message when no movies have been saved yet |

---

## ⭐ Featured Project

<details>
<summary><strong>Movie Tutorial — React Movie Search &amp; Favorites App</strong></summary>

<br>

A complete movie discovery experience built as a React learning project. Users land on a grid of currently popular movies, can search TMDB's full catalog by title, and can favorite any poster with a single click — favorites persist even after closing the browser.

| Attribute | Detail |
|---|---|
| **Stack** | React 19, Vite 8, React Router DOM 7, TMDB REST API |
| **Pages** | Home (`/`), Favorites (`/favorites`) |
| **State** | Local component state (search, loading, error) + global Context (favorites) |
| **Persistence** | `localStorage` — favorites survive page reloads |
| **API Calls** | `GET /movie/popular`, `GET /search/movie` (TMDB v3) |
| **Dev Server** | Vite with instant HMR |
| **Repository** | [movie-tutorial/](./movie-tutorial/) |

**How it works:**

1. On load, `Home` calls `getPopularMovies()` and renders the results as a responsive `movies-grid` of `MovieCard` components.
2. Typing a title into the search bar and submitting calls `searchPopularMovies(query)`, swapping the grid to matching results.
3. Each `MovieCard` displays a TMDB poster image and a heart-shaped favorite toggle powered by `useMovieContext()`.
4. Favoriting a movie updates the shared `favorites` array in `MovieContext`, which is written to `localStorage` on every change.
5. The `/favorites` route reads directly from context and renders either the saved movies grid or an empty-state message.

</details>

---

## 📁 Project Structure

```
movie-tutorial/
├── public/
│   ├── favicon.svg
│   └── icons.svg
├── src/
│   ├── components/
│   │   ├── MovieCard.jsx      # Poster, title, year, favorite toggle
│   │   └── NavBar.jsx         # Top navigation between Home and Favorites
│   ├── contexts/
│   │   └── MovieContext.jsx   # Global favorites state + localStorage sync
│   ├── pages/
│   │   ├── Home.jsx           # Popular movies + search
│   │   └── Favorites.jsx      # Saved movies list / empty state
│   ├── services/
│   │   └── api.js             # TMDB fetch helpers
│   ├── css/                   # Per-component stylesheets
│   ├── App.jsx                # Routes + MovieProvider wrapper
│   └── main.jsx                # React root / entry point
├── index.html
├── vite.config.js
├── eslint.config.js
└── package.json
```

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone <your-repo-url>
cd movie-tutorial

# Install dependencies
npm install

# Add your TMDB API key
# Create a .env file and set VITE_TMDB_API_KEY=your_key_here
# then update src/services/api.js to read import.meta.env.VITE_TMDB_API_KEY

# Start the development server
npm run dev

# Build for production
npm run build

# Preview the production build
npm run preview
```

> The dev server runs at `http://localhost:5173` by default with instant hot module reload via Vite.

> ⚠️ **Note:** This project currently has a TMDB API key hardcoded in `src/services/api.js`. Before pushing to a public repository, move it into a `.env` file and add `.env` to `.gitignore` to avoid leaking credentials.

---

## 🎯 How to Use

```yaml
browsing:
  - Land on the Home page to see currently popular movies
  - Type a title into the search bar and press Search
  - Click the heart icon on any poster to save it as a favorite

favorites:
  - Navigate to the Favorites tab in the nav bar
  - View all saved movies in a grid
  - Click the heart again on any card to remove it

persistence:
  - Favorites are saved to localStorage automatically
  - Reloading or reopening the browser keeps your saved list intact
```

---

## 🎞️ Core Features

| Feature | Description |
|---|---|
| Popular Movies | Fetches and displays trending titles from TMDB on load |
| Live Search | Search the full TMDB catalog by movie title |
| Favorites | One-click add/remove, backed by React Context |
| Persistent Storage | Favorites survive page reloads via `localStorage` |
| Client-Side Routing | Instant navigation between Home and Favorites with React Router |
| Responsive Grid | CSS grid layout adapts poster cards to screen size |

---

## 🔮 Roadmap

```yaml
planned:
  - Movie detail pages (cast, overview, ratings)
  - Genre and year filters
  - Infinite scroll / pagination for search results
  - Debounced search input
  - Loading skeletons instead of plain text
  - Move TMDB API key to environment variables

exploring:
  - Server-side favorites (accounts + database)
  - TypeScript migration
  - Unit tests with Vitest + React Testing Library
  - Dark/light theme toggle
```

---

## 🤝 Contributing

Contributions are welcome. Fork the repo, create a feature branch, and open a pull request.

```bash
git checkout -b feature/movie-detail-page
git commit -m "feat: add movie detail page with cast info"
git push origin feature/movie-detail-page
```

---

<div align="center">

*"Every great story starts with someone hitting search."*

<img src="https://capsule-render.vercel.app/api?type=waving&amp;color=gradient&amp;customColorList=6,11,20&amp;height=120&amp;section=footer&amp;animation=twinkling" width="100%"/>

</div>
