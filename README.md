# 3R Warehouse

Inventory, Purchasing and Returns for 3R Plumbing & Mechanical, at `https://ross680.github.io/3r-warehouse/`. Static files, no build step, backed by the Supabase project **3r-tools** (ref `mgjvxoupsrbxvstvmnpw`), the same tables as before.

## Files

- `index.html`: the Inventory page and its sign-in. The menu has Daily work, Items and Setup (Inventory), **Purchasing** (`#po`) and **Returns** (`#ret`).
- `purchasing.js`: Purchase orders, Parts requests, Vendors and ServiceTitan, on `po_orders` / `po_lines`.
- `returns.js`, `returns.css`: the Return Generator screens: Return list, Find items, Closed returns, Vendor spend, Add purchases (admin) and About the data, on `purchase_docs`, `purchase_lines`, `return_lines`, `vendors`, `categories` and `imports`.
- `config.js`: the Supabase URL and publishable key. The key is meant to be public; every table needs a signed-in user on `app_users`.
- `supabase/functions/servicetitan`: source of the deployed `servicetitan` Edge Function that Purchasing calls.
- `docs/`: ServiceTitan setup and the Zapier invoice intake.

## Sign-in

Email and password (Supabase Auth). Only active emails on `app_users` get in. Forgot password sends a reset email that opens this page with a Set your password screen. That only works if `https://ross680.github.io/3r-warehouse/` is under Supabase → Authentication → URL Configuration → Redirect URLs.
