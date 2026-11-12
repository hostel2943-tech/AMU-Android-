AMU ANDROID-OPTIMISED WEBSITE — GITHUB REPOSITORY

CONTENTS
- index.html: complete AMU application (existing Supabase and email bridge connections preserved)
- manifest.webmanifest: installable Android PWA settings
- service-worker.js: caches only the application shell; does not cache API responses or financial records
- amu-icon.svg, amu-icon-192.png, amu-icon-512.png: app icons

UPLOAD
1. Create a new GitHub repository.
2. Upload all package files directly into the repository root (not inside another folder).
3. Open Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch.
5. Choose branch main and folder /(root), then Save.
6. Wait for GitHub Pages to publish the site. Open the published HTTPS URL in Chrome on Android.
7. Chrome menu → Add to Home screen / Install app.

IMPORTANT
- This is the Android-first, installable PWA website package. It is not yet a signed APK/AAB. A later step can wrap the published PWA as an Android app using a Trusted Web Activity or another suitable wrapper.
- Internet is required for Supabase authentication, database operations, reports and email actions.
- The existing Supabase project and Edge Functions are used. Do not change database tables, secrets, Apps Script deployments, or scheduled 8 PM email triggers for this website package.
- Download Current Balances starts a CSV download directly; Print Current Balances opens the Android/browser print interface. The phone must have an available print service or Save as PDF destination.
- Direct file downloads depend on Android browser support and download permissions. Use Chrome for the most reliable behaviour. Pop-up panels retain their existing size, position, margins and Back-button behaviour. The dashboard tiles and icons have been spaced out, and the lower 3 × 3 section expands to use available phone-screen height more effectively.
- Backup validation checks the seven required data sections. The Restore Backup control is visible but intentionally disabled: a secure transactional server-side restore has not yet been implemented or tested. Do not treat validation as a restore.
- Keep this repository private if you prefer not to expose the application source. The publishable Supabase key is intended for browser use; never add service-role keys or AMU_EMAIL_SECRET to the repository.


Final layout update: dashboard tiles retain their roomy phone layout. Pop-up panels now size to their content instead of stretching down the screen; long history content grows as records load and scrolls inside the panel only when needed. Existing panel navigation and Android Back-button stack behaviour are preserved.
