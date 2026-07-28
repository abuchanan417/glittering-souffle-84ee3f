DockTruth — Netlify deploy package (NOW WITH REAL SHARED DATA)
================================================================

WHAT THIS IS
A single self-contained index.html. No build step, no npm install needed.
Runs entirely in the browser (React loaded from CDN at page load).

AS OF THIS VERSION: this app is wired to a real Supabase database.
Every driver who opens the live link reads and writes to the SAME shared
data now — not their own private browser copy. This is the real thing.

HOW TO GO LIVE / UPDATE THE LIVE SITE
Push index.html (plus favicon.svg, favicon.png, apple-touch-icon.png)
to your GitHub repo, same as you've been doing. Netlify rebuilds
automatically.

WHAT'S SHARED VS. PERSONAL
- Locations and reviews: stored in Supabase, shared by everyone.
- "X stops logged" contribution counter: stays in each device's local
  storage on purpose — it's a personal nicety, not part of the shared
  dataset, and doesn't need a real account system to make sense.

ADDING NEW FIELDS LATER
Locations and reviews are each stored as one flexible JSON blob in the
database (not one column per field). That means most future field
additions — like everything added in past sessions — need ZERO changes
in Supabase. Just push the updated index.html, same as always.

SECURITY NOTE
The Supabase tables currently allow open read/write access to anyone with
the public key (which is meant to be public). This matches the trust
level the app has had this whole time. Tighten this once real driver
accounts exist — restrict edits/deletes to the person who created a row.
