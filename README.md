# KZ Cards — Website Starter

A mobile-friendly public collection gallery with a private owner dashboard. Built with React, Vite, and Supabase.

## What works
- Public gallery with search, sport/team/year filters, featured and sale tabs
- Card detail views with stories and Instagram DM link
- Private email/password login; admin-only add/edit/delete cards
- Photo uploads (one primary image per card), stored in Supabase Storage
- Responsive dark design
- Sample entries in preview mode until Supabase is configured

## Setup (a computer is easiest for the first deployment)
1. Create a free project at https://supabase.com . Keep your project URL and **publishable / anon key** handy. **Never use a service-role or secret key in the website.**
2. Under Authentication > Users, create your own email/password user. Disable public sign-ups in Authentication settings if available; do not give visitors accounts.
3. Open Supabase SQL Editor and run `supabase/setup.sql`. Then run the final `insert into public.admins ...` statement after replacing `YOUR_EMAIL_HERE` with your actual admin email. The script assumes a fresh project; if re-run, policies may already exist.
4. On your computer install Node.js LTS (https://nodejs.org). Open this folder in a terminal, run `npm install`.
5. Copy `.env.example` to `.env`, enter `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` (publishable key is fine). Run `npm run dev` and open the displayed local URL.
6. Click Admin and sign in. Upload your first card. To publish, push this folder to a GitHub repository and connect it to Vercel (https://vercel.com). Add the same two `VITE_` environment variables to Vercel's project settings. Deploy.
7. Open your live site, confirm public browsing works in a private browser window, and test admin login, upload, edit, and delete.

## Security and privacy
- Row-level security prevents visitors from modifying cards and photos; public card data and photos are intentionally readable.
- The `admins` table has no public select policy. Only an admin added by the SQL statement can modify the catalog.
- The front-end env key is public by design. Never expose a Supabase secret/service-role key.
- Purchase prices are deliberately NOT stored or displayed in this starter.
- Photos uploaded here are public; do not upload personal documents or photos containing private details.
- Supabase free tier limits and hosting limits may change.

## Future upgrades
Multiple front/back images, bulk CSV import, a card value tracker (private), advanced collection statistics, custom domain, custom logo, and more.
