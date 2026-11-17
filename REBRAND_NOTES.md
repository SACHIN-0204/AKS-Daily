# Rebrand to AKS Daily

Tagline: "Fresh essentials. Every single day." (Hindi: ताज़ा ज़रूरी सामान, हर दिन।)

## Changed
- Store name, tagline, page titles, meta tags, PWA manifest, emails, SMS texts, Razorpay checkout name, About/Terms/Shipping/Register copy (English and Hindi).
- New logo files in `frontend/public/`: `logo-navbar.png`, `logo-icon.svg`, `logo.png`, `logo192.png`, `logo-maskable-192.png`, `logo-maskable-512.png`, `favicon.ico`, `logo-full.png` (social share image), `aks-daily-banner.jpg` (home hero, replaces `kusora-banner.jpg`).
- Navbar logo size adjusted in `navbar.css` for the wider horizontal logo.
- Service worker cache names renamed to `aks-daily-*` so returning visitors get the new logo (test file updated).
- PWA theme color changed to #1B5E3F.

## Deliberately NOT changed (decide before launch)
- Contact email `info@kusora.com` in `frontend/src/config/store.js`, and `info@apnabasket.com` on the About page: change these once you have an AKS Daily email address.
- Seed login emails `admin@apnabasket.com` / `user@apnabasket.com` in `backend/seed.js`.
- Database name `apna-basket`, Cloudinary folder `apna-basket/products` and the Render service name: renaming them would disconnect existing data and images.
- Unused old images still in `frontend/public/`: `apna-basket-banner.jpg`, `2.png`.
- Site-wide page colors (green `#1f8a43`, orange `#f97316`) in the CSS files, which are close to the new logo colors.
