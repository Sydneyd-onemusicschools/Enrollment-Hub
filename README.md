# Enrollment Hub (Static Prototype)

This folder contains a working static prototype of your Enrollment Hub. No build tools required — just upload these files to GitHub.

## Files
- `index.html` — Home dashboard (wired to Admin via localStorage)
- `admin.html` — Admin dashboard (edit Announcements, Today, This Week, Quota, Team; exports & inbox)
- `studios/danbury.html` — Studio info page (Danbury, CT)
- `assets/logo.png` — Header logo (white/transparent)

## How it works
- Admin saves data to `localStorage` keys:
  - `announcements`, `today`, `thisWeek`, `quota`, `teamMembers`
- Home **reads** those values and renders Announcements, Today, Training, Quota, and the **name dropdown**.
- Home → Comments & Concerns go to `inbox` (shown on Admin).
- Home → Daily Check‑Ins go to `checkins` (shown on Admin).
- Opening **Admin** sets `inboxLastViewed` so the Home page badge shows **unread** counts.

> All persistence is **browser-local** (localStorage). For shared team data across computers, migrate keys to a shared backend later (Firebase, Supabase, Google Apps Script).

## Deploy on GitHub Pages
1. Create a new GitHub repo (e.g., `enrollment-hub`).
2. Upload the contents of this folder (drag & drop in the GitHub web UI).
3. Go to **Settings → Pages**.
4. **Source**: choose **Deploy from a branch**.
5. **Branch**: `main` (or `master`) and **/root** folder.
6. Click **Save**. After ~1 minute, your site is live at:
   `https://<your-username>.github.io/<repo-name>/`

## Open the pages
- Home: `/index.html`
- Admin (new tab): `/admin.html`
- Studio example: `/studios/danbury.html`

## Customizing
- Replace `assets/logo.png` with your final transparent logo (same filename).
- Add more studios by duplicating `studios/danbury.html` and updating content.
- To change the top pills or links, edit the corresponding sections in `index.html`.
- To reset demo data, open DevTools → Application → Local Storage → clear keys (or run `localStorage.clear()` in console).

---

If you want a Firebase-backed version next, we can swap localStorage calls for Firestore reads/writes with minimal code changes.