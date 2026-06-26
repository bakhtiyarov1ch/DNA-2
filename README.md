# DNA Comparison Platform

A full-stack web application for comparing DNA sequences with dynamic programming alignment algorithms, authorization, admin panel, Supabase database support, and cloud-ready deployment settings.

## Features
- User registration and login
- Admin dashboard with user and alignment history
- Sequence alignment using Needleman-Wunsch and Smith-Waterman
- Reactive interface with animated cards and transitions
- Supabase backend for persistence
- Docker, GitHub Actions, and deployment instructions

## Local setup

1. Create environment variables:
   ```bash
   cp .env.example .env.local
   ```
2. Set Supabase variables in `.env.local`:
   ```env
   SUPABASE_URL=https://your-project.supabase.co
   SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
   SUPABASE_KEY=your-service-role-key
   SUPABASE_ANON_KEY=your-anon-key
   JWT_SECRET=your_super_secret_key
   ADMIN_EMAIL=admin@example.com
   ADMIN_PASSWORD=admin123
   ```
3. Create Supabase tables using `supabase-schema.sql` or via SQL editor.
4. Install dependencies:
   ```bash
   npm install
   ```
5. Run in development mode:
   ```bash
   npm run dev
   ```
6. Open http://localhost:3000

## Deployment

### GitHub
1. Initialize repo:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<username>/<repository>.git
   git push -u origin main
   ```

### Cloud deploy
- Vercel: connect the repo and set `JWT_SECRET`, `ADMIN_EMAIL`, `ADMIN_PASSWORD` in project settings.
- Docker: build with `docker build -t dna-alignment-platform .` and run with `docker run -p 3000:3000 dna-alignment-platform`.

## Environment variables
- `SUPABASE_URL` - your Supabase project URL
- `SUPABASE_SERVICE_ROLE_KEY` - Supabase service role key for server-side access
- `SUPABASE_KEY` - fallback Supabase key for server-side queries if service role is unavailable
- `SUPABASE_ANON_KEY` - optional Supabase anonymous key
- `JWT_SECRET` - secret key for token signing
- `ADMIN_EMAIL` - admin account email
- `ADMIN_PASSWORD` - admin account password

## Notes
- The application uses Supabase for persistence and no longer stores data in `data/database.sqlite`.
- The admin account will be created automatically when environment variables are set.
