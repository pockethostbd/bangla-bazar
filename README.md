# BanglaBazar — Final v5

## Included
- GitHub REST API product publishing; token is never hardcoded.
- Firebase Authentication + Firestore for user profiles, cart, wishlist and private orders.
- User profile image is compressed and stored as Base64 text in Firestore.
- Product reviews: one review per signed-in user per product, up to 3 compressed images.
- WhatsApp Buy Now / cart checkout to **01949737370** with product links and customer information pre-filled. The user must press Send in WhatsApp.
- Website customization is published to `data/site.json` from Admin.
- Logo URL preview + local crop editor; cropped logo can be published as Base64 text.
- SVG icons; mobile-first UI.

## Firebase setup (important)
The Firebase config is already included in `js/config.js`. In Firebase Console, enable **Authentication → Sign-in method → Email/Password**. If this is disabled, account creation will correctly report that Email/Password authentication is not enabled. Create/enable a Firestore database and publish `firebase.rules`.

## GitHub Admin
Open `admin.html`, enter GitHub username, repository, branch and a Personal Access Token with repository contents write permission. The token is kept only in sessionStorage and is not published into GitHub files.

## Product URL
Use a stable English slug such as `islamic-history-1-5`. Product page: `products/islamic-history-1-5.html`.

## Images
Profile and review images are compressed in the browser before Base64 storage. Firestore has document size limits, so keep review images reasonable; the code caps each review at 3 images and compresses them.
