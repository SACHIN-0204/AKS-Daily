# Delivery area (PIN code check)

Shop: Ambamoliya, Indore, Madhya Pradesh. Delivery: PIN code **452001** only.

## How it works
- `backend/config/settings.js` reads `SERVICE_PINCODES` (default `452001`).
- Checkout page: when the customer types a 6-digit PIN it calls `GET /api/store/pincode/<pin>` and shows
  "Delivery available" or "Sorry, we don't deliver to this PIN code". The Place order button is disabled for PINs outside the area.
- Server: `POST /api/orders` now rejects any order whose PIN is not in the list (HTTP 400, "we do not deliver to PIN code ..."),
  so the rule cannot be bypassed from the browser.

## Add more PIN codes later
Set the environment variable (backend/.env locally, or Render > Environment) and restart:

    SERVICE_PINCODES=452001,452002,452003

Also update `servicePincodes` in `frontend/src/config/store.js` so the messages on the site list the same PIN codes.

## Quick check
    curl https://<your-domain>/api/store/pincode/452001   ->  {"pincode":"452001","serviceable":true}
    curl https://<your-domain>/api/store/pincode/110001   ->  {"pincode":"110001","serviceable":false}
