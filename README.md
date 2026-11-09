# Smart Police Complaint Tracker

A responsive English/Kannada Next.js demo for citizen complaint submission and tracking, officer workflows, supervisor oversight, deadline reminders, escalation, and a clearly labelled fast-forward demo clock. This is an educational prototype, not an official police service.

## Run locally on Windows

1. Install Node.js LTS.
2. Extract `Smart-Police-Complaint-Tracker.zip`.
3. In the extracted project folder run `Copy-Item .env.example .env.local`, then `npm install` and `npm run dev`.
4. Open http://127.0.0.1:3000. Persistent local PGlite storage seeds 20 fictional complaints on first use.

Demo sign-ins (local prototype only): `citizen@demo.local` / `citizen-demo`, `officer@demo.local` / `officer-demo`, and `senior@demo.local` / `senior-demo`.

## Configuration and limits

`.env.example` sets `DEMO_MODE=true` and `SMS_MODE=simulated`. Demo clock advances use separate simulated time and never send live SMS. Real Twilio sending requires server-side credentials, `SMS_MODE=live`, explicit approval, and an approved destination. No live credentials are included.

The current runtime complaint/audit/outbox store is local persistent PGlite. Supabase schema, RLS policies, and seed SQL are supplied inside the source bundle; hosted Supabase complaint storage is not wired. Supabase Auth is optional. Deadline processing is available through a protected endpoint/one-shot script, but no unattended scheduler is configured.

## Verify

Run `npm run typecheck`, `npm run test:demo`, and `npm run build`. See the included project README for the complete demo and deployment notes.

## Files

`Smart-Police-Complaint-Tracker.zip` contains the complete project source, configuration, SQL schema/seed, scripts, and setup guide. It excludes `.env.local`, dependencies, generated builds, and persistent local data.