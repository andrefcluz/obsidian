---
created: 2025-10-27T09:00
updated: 2025-10-27T14:06
---
## 📚 PickMate — Random Discovery App (Books, Future Expansion)

### Concept

**PickMate** is a lightweight, cross-platform mobile app that helps users discover new content in a fun, effortless way.  
Starting with books, users select a **category** (e.g., Fantasy, Romance, Mystery) and are presented with a **random, highly-rated title** — complete with cover, description, rating, and a link to buy on **Amazon (affiliate link)**.

The core appeal: **eliminate choice fatigue**, make discovery playful, and reward users with surprises — one random pick at a time.

**Long-term vision:** expand beyond books to movies, TV shows, podcasts, and other content types using the same random-selection mechanic.

---

### Core Features (MVP)

1. **Category Selection**
    - Pick a genre/category or use “Surprise Me” to explore randomly.
2. **Random Content Generator**
    - Fetch a list of items from an external API (initially Google Books API, later Hardcover API).
    - Filter by minimum rating (e.g., ≥ 3.8★) and optionally number of reviews.
    - Randomly select one and display it.
3. **Detail View**
    - Display cover image, title, author, rating, description.
    - Button: **View on Amazon** (affiliate link).
    - Button: **Another Spin** (get a new random pick).
4. **Favorites (optional MVP+)**
    - Users can save favorites locally.
5. **Daily Pick (future)**
    - Optional daily notification with one random selection.

---

### Content Types

- **Books:**
- **Movies:**
- **TV Shows:**
- **Podcasts:**
- **Games:**
- **Food Types:**
- **Recipes:**
- **Articles:**
- **Custom User Lists:**

---

### Monetization

#### Coin-Based System

- **Spin Mechanics:** Each spin consumes **1 coin**.
- **Ways to Earn Coins:**
    1. **Daily login:** earn 3 free coins (expire at end of the day).
    2. **Streak Bonus:** earn 1 bonus coin per consecutive week (of daily spins), up to 7 (expire at the end of the day)
    3. **Video Ads:** earn 1 coin by watching a video ad (expire at the end of the day) 
    4. **Coin Packs (in-app purchases):**
        - 10 coins - 1€
        - 25 coins (+5 bonus) - 2€
        - 40 coins (+10 bonus) - 3€
        - 55 coins (+15 bonus) - 4€
        - 70 coins (+20 bonus) - 5€
        - 150 coins (+50 bonus) - 10€
    5. **Subscription:** unlimited coins - 5€/month or 50€/year.

**Psychology:**
- Scarcity and expiring coins drive daily engagement.
- Random rewards create anticipation and habit formation.
- Multiple monetization paths cover casual, paying, and highly engaged users.

#### Affiliate Links
- **Books:** Amazon
- **Movies and TV:** Amazon, Apple, Rakuten
- **Podcasts:** Spotify, Apple Podcasts, Audible
- **Games:** Steam


---

### Engagement / Event Ideas

- Seasonal or themed events to maintain retention:
    - Valentine’s: “Build a complete date plan randomly”
    - Halloween: spooky books & movies combo
    - Christmas: holiday feel-good picks
    - New Year: self-improvement books + motivational quotes
- Surprise bonuses: “Double Coin Weekend” or “Extra Spin Day”
- Optional streak bonuses for consecutive daily logins

---

### Data Source / API

- **MVP:** Google Books API — free, reliable, supports categories, includes ratings.
- **Phase 2:** Hardcover API — richer metadata, structured genres, community ratings.

**Example filtering:**
- Only pick books with rating ≥ 3.8 and reviews count ≥ 20 to ensure quality.

---

### Technical Implementation Plan (MVP)

**Stack:**
- **Frontend:** React Native (Expo) for cross-platform deployment
- **UI Framework:** React Native Paper / NativeBase
- **Backend:** None required initially; can add server later for caching, analytics, or multi-category logic
- **Data Storage:** AsyncStorage for favorites, coin balance, and cached results

**MVP Flow:**
1. User selects category → app fetches books from API.
2. Filter by rating → randomly select one book.
3. Display book detail with **spin cost = 1 coin**.
4. Buttons: “Another Spin” or “Add to Favorites.”
5. Daily login grants 3 free coins; coin packs or subscription unlock additional spins.

---

### Future Expansion
- Add more content types: movies, TV shows, podcasts, games, recipes, etc.
- Upgrade to Hardcover API for books, TMDb for movies/TV, Listen Notes for podcasts.
- Add gamification features: streaks, achievements, leaderboards, community features.
- Seasonal and themed events to drive engagement and retention.