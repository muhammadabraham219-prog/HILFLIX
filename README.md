# HILFLIX starter

This is a Firebase-connected web/PWA starter that can be installed from a supported Android browser after HTTPS hosting. It is **not a signed APK** and is not yet published.

## Included
- Email/password registration and login
- Video upload to Firebase Storage (200 MB starter limit)
- Firestore video records submitted as `pending`
- Approved-video playback for signed-in users
- Firebase security rules
- The supplied Firebase Web configuration and Android `google-services.json`

## Required Firebase setup
1. In Firebase Console, enable Authentication > Email/Password.
2. Create a Firestore database.
3. Enable Firebase Storage.
4. Deploy the rules in `firebase/` to your Firebase project.
5. Host the contents of `public/` on an HTTPS host (Firebase Hosting is one option).

## Founder admin setup
After creating the founder account, copy that account's Firebase Authentication UID. In Firestore, create a document in collection `admins` whose document ID is exactly that UID. The document can contain `{ "role": "admin" }`. Do this only for the founder account. The starter rules use this record to authorize moderation operations, but a moderation dashboard is not included in this minimal package.

## Important limitations
- No automatic nudity, copyright, or harmful-content detection is included.
- Uploads remain pending until an admin approves them in Firestore.
- This starter does not yet include an admin dashboard, payments, subscriptions, recommendations, or reporting UI.
- Configure Firebase billing/quotas and review security rules before public launch.
- The Firebase Web API key is intended for client configuration; never put service-account private keys in a client app.
