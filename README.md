# ⛩️ ANIME WORLD - Modern Anime Streaming & Discovery Platform

A modern, responsive anime discovery and simulated streaming web application built with pure **HTML5, CSS3, and modern Vanilla JavaScript**. 

Powered by live data from the **Jikan API (v4 MyAnimeList)** with a curated, high-speed offline fallback system.

---

## ✨ Key Features

- **🔥 Hero Spotlight Carousel**:
  - Rotating spotlight showcasing top-tier anime (Solo Leveling, Jujutsu Kaisen, Frieren, Demon Slayer, Chainsaw Man).
  - Quick action buttons: "Watch Trailer", "Stream Ep 1", and "Add to List".
  - Auto-rotates every 7.5 seconds and pauses when hovered.

- **⚡ Live Search with Autocomplete Dropdown**:
  - Real-time debounced search through the public Jikan API.
  - Dropdown previews with poster thumbnails, title, score, type, and season.
  - Keyboard shortcut: Press `Ctrl + K` or `⌘ + K` to immediately jump into search.

- **🎯 Interactive Filters & Sorting**:
  - Dynamic genre pills: Action, Adventure, Comedy, Drama, Fantasy, Mystery, Romance, Sci-Fi, Supernatural.
  - Category views: *Home*, *Top Airing*, *Popular*, and *Most Favorited*.
  - Sort by: Most Popular, Highest Score, Lowest Score, or Title (A–Z).

- **🎬 Full Anime Detail Modal**:
  - High-resolution banners and poster art.
  - Comprehensive metadata: Rank, Score, Studio, Episodes, Airing Status.
  - Full synopsis without clutter.
  - Character & Voice Cast gallery.
  - Interactive episode list grid.

- **📺 Simulated Video Streaming Player**:
  - Embedded player with official trailers / full-screen viewing.
  - Interactive **"Skip Intro (85s) ⏩"** simulation.
  - Episode navigation sidebar allowing instant episode switching.
  - Sub / Dub audio indicators & 1080p HD badge.

- **🔖 Personal Watchlist ("My List")**:
  - Stored persistently in browser `localStorage`.
  - Filter tabs: *All*, *Watching*, *Plan to Watch*, and *Completed*.
  - Change status on the fly or remove titles with a single click.
  - Real-time navbar badge count.

- **🎲 Anime Oracle (Gacha Roll)**:
  - Can't decide what to watch? Hit the dice button in the navbar to let fate recommend a random anime from the collection!

- **🎨 Modern Dark Cyber/Glass Aesthetic**:
  - Glassmorphic navigation bar (`backdrop-filter`).
  - Neon sakura crimson (`#ff2a5f`) and cyan accents.
  - Fully responsive on mobile, tablet, and widescreen desktop monitors.
  - Anime toast notifications for user interactions.

---

## 🚀 How to Run the Website

### Option 1: Double-Click Directly (No Installation Needed!)
Simply navigate to `D:\AntiGravity\` and double-click `index.html` in Windows File Explorer. It will open instantly in your default web browser (Edge, Chrome, Brave, Firefox, etc.).

### Option 2: Run via PowerShell
Open PowerShell in this directory and execute:
```powershell
Start-Process index.html
```

---

## 📁 File Structure

```text
D:\AntiGravity\
├── index.html     # Semantic HTML5 layout and modals
├── styles.css     # Responsive modern CSS, animations, glassmorphism
├── data.js        # Curated rich anime dataset & fallback data (ADD ANIME & EPISODES HERE!)
├── api.js         # Jikan v4 API service with caching and throttling
├── app.js         # Main controller: state, event listeners, player, watchlist
└── README.md      # Documentation
```

---

## 🎬 How to Add Anime & Custom Episode Names

All custom anime, titles, and episode names are defined in **`data.js`**.

### 1. Adding Episodes to an Existing Anime
Open `data.js` and find the anime in `FEATURED_ANIME`. Add or edit the `episode_list` property:

```javascript
{
  id: 1,
  mal_id: 52299,
  title: "Solo Leveling",
  ...
  // 👇 Add your episode titles and video links here:
  episode_list: [
    { 
      number: 1, 
      title: "I'm Used to It", 
      video_url: "https://www.youtube.com/embed/9g_oY_b3XVo" 
    },
    { 
      number: 2, 
      title: "If I Had One More Chance", 
      video_url: "https://www.youtube.com/embed/9g_oY_b3XVo" 
    },
    { 
      number: 3, 
      title: "It's Like a Game", 
      video_url: "https://www.youtube.com/embed/9g_oY_b3XVo" 
    }
  ]
}
```

### 2. Adding a Completely New Anime
Add a new object inside the `FEATURED_ANIME` array in `data.js`:

```javascript
{
  id: 13,
  mal_id: 13,
  title: "Your New Anime Title",
  japanese_title: "新アニメ",
  poster: "https://images.unsplash.com/photo-1578632767115-351597cf2477?w=600",
  banner: "https://images.unsplash.com/photo-1578632767115-351597cf2477?w=1600",
  score: 9.0,
  rank: 10,
  type: "TV",
  episodes: 12,
  status: "Finished Airing",
  season: "Spring 2024",
  studio: "ufotable",
  genres: ["Action", "Fantasy", "Supernatural"],
  synopsis: "An exciting story about...",
  trailer_url: "https://www.youtube.com/embed/VIDEO_ID",
  
  episode_list: [
    { number: 1, title: "Episode 1 Name", video_url: "https://www.youtube.com/embed/VIDEO_ID" },
    { number: 2, title: "Episode 2 Name", video_url: "https://www.youtube.com/embed/VIDEO_ID" }
  ],

  characters: [
    { name: "Character Name", role: "Main Protagonist", avatar: "https://avatar-url.jpg" }
  ]
}
```

> **Tip for Video URLs**: For YouTube videos, make sure to use the embed format:  
> `https://www.youtube.com/embed/VIDEO_ID` (e.g. from `https://www.youtube.com/watch?v=VIDEO_ID`). You can also use any embeddable video iframe URL!

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Ctrl + K` / `⌘ + K` | Focus and open search bar |
| `Escape` | Close any open modal (Details, Video Player, Watchlist, or Gacha) |

---

## 🌐 API Attribution
- Anime metadata provided by [Jikan API](https://jikan.moe/), the unofficial open-source MyAnimeList API.
