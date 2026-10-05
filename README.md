# Berry Vibes Studio × CCD — V3 Community + Grocery + Cycle Edition

A multi-page HTML/CSS/JavaScript website for GitHub Pages, with an optional included Node.js backend.

## What changed in V3

- **Moving image gallery moved to the very beginning of the Today/home page.** It auto-scrolls, pauses on hover, and its speed can be changed in Settings.
- **Settings page** with full-site themes, motion on/off, gallery speed, default social post privacy, daily grocery recipe recommendations, default post-login start page, JSON export/import, and scoped reset controls.
- **Interactive Period Tracker page** with period ranges, individual cycle-day logging, flow, mood, symptoms, pain level, notes, editable/deletable history, a 42-cell cycle calendar, cycle-day status, and a simple next-period estimate. Period data is stored locally by default.
- **Calendar upgraded into a planner/editor.** Pick any date, add plans, edit/delete logged entries, change calories/macros/burn/date/time/notes, and change water bottles for that day. When the optional Node backend is connected, log edits/deletions sync through the backend.
- **Grocery page** with the built-in CCD pantry as the initial catalog plus custom ingredients. Includes search, category filters, quantity, quality level, descriptions, nutrition details, ingredient-photo uploads, cart, wishlist, saved items, Buy Now/purchase history, recommendations, and rotating daily recipe recommendations.
- **Social page** with posts, image posts, likes, comments, sharing, following, follow requests for private profiles, public/private profiles, profile viewing, feed filters, and profile editing.
  - On plain GitHub Pages, social works as a browser-local multi-account community and includes demo profiles/posts.
  - With the included Node backend connected, the social feed syncs across signed-in backend accounts. Private-profile visibility and follow requests are enforced by the backend bootstrap/sync routes.
- Existing food/drink logging, exercise start→finish duration calculation, fasting, recipes, SOTD, restaurants, Food Battle, Facts, Profile, and authentication remain included.

## Pages

1. `index.html` — Today dashboard + moving gallery first
2. `foods.html` — food + drink logger, uploads, scroll-wheel time
3. `recipes.html` — recipe vault + recipe lab
4. `sotd.html` — SOTD presets
5. `exercise.html` — exercise with START TIME → FINISH TIME auto-duration
6. `fasting.html` — fasting logs
7. `restaurants.html` — restaurant presets + custom restaurant foods
8. `grocery.html` — interactive grocery store/planner
9. `battle.html` — Food Comparison Battle
10. `facts.html` — daily CCD facts
11. `calendar.html` — editable calendar + planner
12. `period.html` — interactive period tracker
13. `social.html` — community/social page
14. `profile.html` — profile editor; height displays like `5'2`
15. `settings.html` — behavior/privacy/data settings
16. `about.html`
17. `login.html`
18. `signup.html`
19. `forgot-password.html`
20. `reset-password.html`
21. `forgot-username.html`

## Grocery checkout note

The Grocery page is a **functional personal grocery-planning storefront**, not a real retailer/payment gateway. “Buy Now” and checkout create purchase records inside Berry Vibes and calculate totals; they do not charge a card or send an order to a supermarket.

## Period tracker note

Cycle estimates are for personal tracking only. They are not medical advice and should not be used as contraception or as a medical prediction tool.

## Authentication + social modes

### GitHub Pages only
The account system falls back to browser-local accounts so the website still works without a server. Data stays in that browser. The Social page can be used by multiple local accounts in the same browser, but separate devices do not share localStorage.

### Included Node backend
Run:

```bash
npm start
```

The backend supports:
- signup / login / logout
- forgot password / reset password / forgot username
- profiles and uploads
- log creation, editing and deletion
- shared social profiles/posts/follows/likes/comments/shares across backend accounts

To use the backend from GitHub Pages, deploy `server.js` to a Node host and put its HTTPS address in `config.js` as `API_BASE`.

## GitHub Pages deployment

Upload all root files and folders to the repository root, then use:

**Settings → Pages → Deploy from a branch → `main` → `/ (root)`**

The top menu stays horizontal and scrollable on smaller screens. Authentication pages intentionally do not show the private menu.

## V3.1 reactive food-selection update
The Food page meal selector now actively filters the 220-entry CCD archive. Choosing BREAKFAST, LUNCH, SNACK, SOTD, or DINNER immediately changes the visible food cards; it no longer leaves breakfast results on screen after selecting Lunch or another meal slot.
