# BLOXITY Classic — November 2017-inspired refresh

This is an original frontend refresh for the existing BLOXITY Classic repository. The visual direction takes inspiration from compact 2016–2017 game portals and the CodePen remake shared by the project owner. It does not copy Roblox proprietary source code or import Roblox-owned game assets.

## Files
- `index.html` — classic navigation and page structure.
- `style.css` — compact blue navigation, gray background, square panels, classic buttons and responsive layout.
- `app.js` — existing frontend flows for Supabase Auth, profiles, balances, catalog, inventory, daily rewards and protected admin-link visibility.
- `config.js` — existing Supabase project URL and browser-safe publishable key.

## Install
1. Download and extract the ZIP.
2. In `Guest-commits/bloxity-classic`, replace the five root files with the five files in this folder.
3. Commit the changes to `main`.
4. If GitHub Pages is enabled, wait for the deployment and reload the site.

## Important
- This is a visual/frontend update, not a complete Roblox revival or game engine.
- Game tiles remain preview cards; there are no multiplayer servers or game runtime.
- The avatar editor currently saves body, shirt and pants colors only.
- The admin page remains a protected placeholder; no moderation or economy administration tools are implemented.
- No database migration is included or required for this visual refresh. It uses the existing Supabase project and existing schema/RPCs.
- Keep Row Level Security enabled. Never place a Supabase `service_role` key or database password in browser files.
