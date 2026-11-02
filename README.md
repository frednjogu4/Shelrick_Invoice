# Shelrick Technology Invoice App

A lightweight, offline-capable Progressive Web App (PWA) for creating Shelrick Technology invoices. It has no third-party libraries or server-side data collection.

## What's included

- Editable business profile, contact details, logo, automatic invoice-number sequence, currency, VAT, payment details and footer text.
- Client book: add, edit, search, load and delete client records.
- Editable invoice fields, line items, payment instructions, VAT and amount-paid tracking.
- Direct one-page PDF download, browser print layout, saved invoice history and email/WhatsApp sharing tools.
- PWA manifest, service worker and app icons for mobile installation and offline use.

## Automatic invoice numbers

The supplied **A046** invoice template is added to the device's history as a reference-only record (without client details). A fresh installation starts a new blank invoice at **A047**. Use **New** for each subsequent invoice; it advances the configured prefix/sequence and skips numbers already in this device's saved history. The number field is read-only to prevent accidental duplicates; change the prefix or next sequence in **Settings** if needed.

## Install on a phone

The app must be served from a secure **HTTPS** address (or localhost during development) for installation and offline caching. Opening `index.html` directly from Files is useful for testing, but does not enable PWA installation.

1. Deploy the contents of this folder to a static HTTPS host. The included `vercel.json` is ready for a Vercel static deployment; other static hosts also work if they serve `sw.js` from the app root.
2. Open the deployed URL on the phone.
3. **Android / Chrome:** tap **Install app** in the app toolbar, or use Chrome's menu → **Install app** / **Add to Home screen**.
4. **iPhone / Safari:** tap Share → **Add to Home Screen**.
5. Open the installed icon. After the first successful load, the app shell can be used offline.

Settings, clients and invoice history are saved locally in that browser/app installation. They do not sync to another phone and may be removed if browser storage is cleared, so keep exported PDFs for records.

## WhatsApp and email

The business WhatsApp contact is preset to **+254 721 752 212** and can be changed in Settings. The recipient/client phone is entered in the Bill To details. **Share PDF** uses the phone's share sheet so you can select WhatsApp and the client. If the browser does not support sharing a file, the app downloads the PDF and opens a WhatsApp chat with a prepared message; attach the downloaded PDF before sending. Email opens a prepared draft addressed to the client and downloads the PDF; attach it before pressing Send. The email signature uses **shelricktech@gmail.com**, but the actual From address is controlled by the mail account selected on the phone—choose that Gmail account in your mail app. Browsers do not allow a website to silently send a message, force a From account, or attach a local file to a `mailto:` draft.

## One-page output

The PDF export always creates a single A4 page and scales the complete invoice to fit. Browser printing uses a compact A4 layout and reduces the invoice to fit one page. Very long invoices can become small when many rows or lengthy notes are entered.
