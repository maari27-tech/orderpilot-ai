# OrderPilot AI public website

Responsive React + Vite marketing website for distributors and wholesalers. Includes Home, Features, How it works, Pricing, About, Contact, Demo request, Free-trial signup and Login hand-off pages. English and Tamil language switching is included.

## Run locally
1. Install Node.js 18.18+ (Node 20 LTS recommended).
2. Run `npm install`.
3. Copy `.env.example` to `.env`; set `VITE_API_BASE_URL` to your Node.js API origin.
4. Run `npm run dev` and open the Vite URL.

Build for production with `npm run build`; deploy the generated `dist/` folder.

## Backend integration
The website sends JSON POST requests to:
- `/api/auth/register` — trial registration
- `/api/public/demo-requests` — demo requests
- `/api/public/leads` — contact enquiries

Set `VITE_API_BASE_URL` in `.env`. Expected response: any successful 2xx response; optional JSON `{ "message": "..." }`. If the API base URL is blank, forms display a preview-mode message and do not persist submissions.

Registration payload fields: name, businessName, email, phone, password, preferredLanguage, source, plan.
Demo/contact payload fields: name, businessName, email, phone, message, preferredLanguage, source.

Implement server-side validation, rate limiting, spam protection, consent handling and password hashing. Never store passwords in plain text. Connect `/login` to your authenticated app before launch.

## Pricing
Starter ₹999/month and Growth ₹2,499/month are editable launch suggestions, not confirmed prices. The 14-day free trial is also a proposed default. Update `src/main.jsx` before publishing. Your backend must remain authoritative for plan entitlements, trial eligibility and billing.

## Before publishing
Confirm prices, taxes, terms, privacy policy, support details and Tamil translations. Add HTTPS, domain, social preview assets, analytics consent and anti-spam controls. AI order extraction should create reviewable drafts only; authorised humans must approve orders and inventory changes.
