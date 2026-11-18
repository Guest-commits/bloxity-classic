# BLOXITY Classic — v0.1 foundation

A clean, original fan project inspired by the compact 2016–2017 game-portal layout. It is not affiliated with Roblox Corporation and does not include Roblox proprietary code, binaries, branding assets, or game assets.

## Included
- Classic blue navigation, hamburger menu, gray page background and white panels.
- Responsive home, games, catalog, avatar, profile and inventory views.
- Supabase Auth sign-in/sign-up using email and password plus username metadata.
- Reads the existing `profiles`, `catalog_items`, `user_inventory`, and `bloxity_admins` tables.
- Uses the existing RPCs `purchase_catalog_item`, `claim_tix_daily_reward`, and `claim_builders_club_daily_reward`.
- Robux and Tix remain separate currencies.

## Setup
1. Upload the files in this folder to the root of `Guest-commits/bloxity-classic`.
2. Keep `config.js` with the Supabase project URL and publishable key. A publishable/anon key is intended for browser use; never add a `service_role` key or database password.
3. Enable GitHub Pages or deploy the folder to your static hosting provider.
4. In Supabase Auth URL Configuration, add the deployed website URL to Site URL / Redirect URLs.
5. Test with a non-admin test account first.

## Important limitations
- This is a new frontend foundation, not a complete game revival.
- Game cards are clearly marked previews; no multiplayer game servers or game runtime are included.
- The avatar editor currently saves body/shirt/pants colors only; full R6/R15 rendering and clothing/accessory fitting are not implemented.
- Catalog cards display the existing catalog records. Image URLs are not present in the current `catalog_items` schema, so the cards use category illustrations until an asset/image field is added safely.
- The admin view is a protected placeholder. It checks membership in `bloxity_admins` but does not yet perform moderation, bans, economy adjustments, or staff-role management.
- No new SQL migration is required for this frontend foundation. It relies on the existing database schema and RPCs. Do not reset or recreate the existing Supabase project.
- Supabase Row Level Security and server-side authorization must remain enabled. Do not expose privileged keys in browser code.

## Existing Supabase fields used
`profiles`: id, username, player_id, robux_balance, tix_balance, bc_tier, body_color, shirt_color, pants_color.
`catalog_items`: item_id, name, category, price, active, price_currency, bc_tier_required, is_gear.
`user_inventory`: user_id, item_id, purchased_at.
`bloxity_admins`: player_id.
