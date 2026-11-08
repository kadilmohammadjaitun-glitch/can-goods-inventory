# Canned Goods Inventory Management System – UI Upgrade

## Hosting and architecture
- Frontend: single-page `index.html` (HTML, CSS and JavaScript)
- Hosting: GitHub Pages
- Backend services: Supabase Auth, Database, Storage and RPC functions
- Barcode library: ZXing browser library

## Deploy the upgraded UI
1. Keep a backup of the current GitHub repository before replacing files.
2. Extract this ZIP.
3. Open the repository folder and replace the existing `index.html` with the upgraded `index.html` from this package.
4. Keep your existing Supabase project and database unchanged.
5. Commit and push the updated file to the same GitHub repository/branch currently used by GitHub Pages.
6. Wait for GitHub Pages deployment, then hard-refresh the website (Ctrl+F5).

## What changed
- Updated the visual design to a modern green-and-white interface.
- Added a desktop sidebar navigation layout and mobile horizontal navigation layout.
- Restyled dashboard cards, forms, scanner, product records, stock history, reports, role management and modals.
- Preserved the existing page IDs, inline event handlers, JavaScript logic, Supabase client setup, ZXing script reference, and current database/RPC calls to avoid breaking existing workflows.

## Important safety notes
- This package does not include database migrations and does not change Supabase tables, policies, users, storage buckets or records.
- Before deploying, make a copy of the current repository and test with a non-critical account if possible.
- The Supabase publishable/anon key is intended for browser use, but access must be protected by correct Row Level Security (RLS) policies and secure RPC function permissions. Never put a Supabase service-role key in browser code.
- This is a UI-focused upgrade. It does not add expiration-date fields or new database functionality yet.

## Existing backend dependencies referenced by the app
- `products` table
- `user_roles` table
- `user_activity` view/table
- `stock_history` view/table
- RPC: `update_my_activity`
- RPC: `set_my_offline`
- RPC: `adjust_stock`
- RPC: `admin_set_user_role`
- Supabase Storage bucket: `product-images`

If any of these names differ in your live Supabase project, do not change them blindly; review the current schema first.
