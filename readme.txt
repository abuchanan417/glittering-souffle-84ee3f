MilePost — Netlify deploy package
==================================

WHAT THIS IS
A single self-contained index.html. No build step, no npm install needed.
Runs entirely in the browser (React + Babel loaded from CDN at page load).

HOW TO GO LIVE (takes about a minute, no account required for this first step):
1. Go to https://app.netlify.com/drop in your browser
2. Drag this whole folder (or just index.html) onto the page
3. Netlify gives you a live URL immediately (something like random-name-123.netlify.app)
4. That URL works on any phone, right now, for anyone you send it to

TO KEEP THE SITE / GET A REAL DOMAIN LATER
Sign up for a free Netlify account and "claim" the site — this locks in
the URL permanently and lets you rename it or connect your own domain.

IMPORTANT LIMITATION — READ THIS BEFORE YOU SEND IT TO YOUR TEST GROUP:
This version stores all data in the browser's local storage. That means:
  - Each person who visits sees ONLY their own entries, not everyone else's
  - Data does not sync between devices or people
  - Clearing browser data / cache wipes it out

This is fine for you to test the look, feel, and fields on your own phone.
It is NOT yet the shared, crowdsourced version you actually want for
real testing with drivers and brokers.

NEXT STEP FOR REAL SHARED DATA:
Create a free Supabase project at https://supabase.com (free tier, no
credit card, ~2 minute signup). Once you have a project, grab:
  - Project URL
  - Public "anon" API key
Hand those two values (not your password) back to Claude, and the
loadShared() / saveShared() functions in index.html get swapped to call
Supabase instead of localStorage — same app, same UI, real shared data
across every driver who uses the link.
