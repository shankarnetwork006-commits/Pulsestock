# PulseStock Firebase MVP

This is a real backend-ready community voting MVP. It does not contain market-price feeds or broker-wide trades. Votes are app-user sentiment only.

## Setup
1. Create a Firebase project at https://console.firebase.google.com.
2. Add a Web App and The provided Firebase config has been added to `public/index.html` (`firebaseConfig`).
3. Enable **Authentication → Sign-in method → Email/Password**.
4. Create a **Cloud Firestore** database.
5. Install Node.js 20 and Firebase CLI (`npm install -g firebase-tools`), then run `firebase login` and `firebase use --add` in this folder.
6. From this folder run `firebase deploy --only firestore:rules,functions,hosting`.
7. Open the Hosting URL Firebase prints.

## Included
- Email/password Firebase authentication (user-created accounts)
- Cloud Functions validate ticker/vote and write securely
- One current vote per authenticated user, ticker and India calendar day; changing a vote adjusts counts
- Unique daily views per user and ticker
- Firestore listeners update totals live
- Top BUY, Top SELL, Most Viewed lists

## Important
- The sample watchlist is six symbols and is not a live market feed.
- Views count a user's first visit to each stock per India calendar day, not every page refresh.
- Email/password accounts can sign in across devices. Add email verification, password reset, App Check, abuse controls and a privacy policy before public launch.
- Configure Firebase App Check, budgets, alerts, monitoring, and stronger abuse prevention before public launch. Review privacy policy and applicable Indian data-protection requirements.
- Do not expose service-account keys or deploy with unrestricted database rules.
