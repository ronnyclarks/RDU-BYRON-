# Byron Expansion Dashboard

Single-file dashboard tracking Roofing Down Under's relocation to the Northern NSW corridor (Byron Bay → QLD border). Seven pillars: milestones, subbie prospecting, builder pipeline, networking, team recruitment, marketing setup, and social foundations.

## Setup

1. **Paste your Firebase config.** Open `index.html` and replace the `firebaseConfig` block near the top of the `<script>` with the config from your rdudashboard project (same project = same email/password logins work here).
2. **Firestore rules.** Data lives in a `byronExpansion` collection. Make sure your rules allow signed-in users to read/write it, e.g.:
   ```
   match /byronExpansion/{docId} {
     allow read, write: if request.auth != null;
   }
   ```
3. **Deploy via Netlify.** In Netlify: *Add new site → Import an existing project → GitHub → pick this repo*. Leave the build command empty (a `netlify.toml` is included that publishes the repo root — no build step). Every push then auto-deploys.
4. **Authorise the Netlify domain.** In the Firebase console → Authentication → Settings → Authorized domains, add your Netlify site domain (e.g. `your-site.netlify.app`, plus any custom domain) or sign-in will be blocked.

## Notes

- All data persists to Firestore as 7 documents (one per pillar) under `byronExpansion`.
- Every tick/counter saves instantly; text fields save ~0.7s after you stop typing. The dot in the header shows sync state (green = saved, amber = saving, red = error) and a "Saved ✓" toast confirms each write.
- Live-syncs across devices via Firestore snapshots.
