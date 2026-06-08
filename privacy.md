---
layout: page
title: Privacy Policy
permalink: /privacy/
updated: 8 June 2026
description: How IGNITE collects, stores and lets you delete your data. Offline by default, no ads, anonymous analytics you can switch off.
---

**Effective date:** 8 June 2026
{: .updated}

**Data controller:** Total Debug, United Kingdom. **Contact:** [{{ site.contact_email }}](mailto:{{ site.contact_email }})

This page explains what IGNITE collects, why, where it's stored, and how to delete it.

## TL;DR

- **IGNITE works fully offline by default.** No account is required. Your refuels, expenses, services and vehicle records are stored only in the app's local database on your device.
- **Cloud sync is opt-in.** Creating an IGNITE account and turning on Cloud sync (a Pro feature) uploads your records to our backend so they're available on your other devices.
- **No advertising. No data is ever sold or shared with advertisers, brokers or marketing platforms.** We use one privacy-preserving analytics tool (PostHog) to see which features are used and to catch broken flows — it is anonymous, EU-hosted, masks every text field and image, and you can switch it off in Settings (see §7).
- **Camera and on-device OCR** (odometer, fuel pump, receipt scanning) run entirely on your device. The recognised text never leaves the phone unless you choose to save the result (with Cloud sync on).
- **You can delete your account and every byte of cloud-side data at any time** — see [Delete your account]({{ '/delete-account/' | relative_url }}). The deletion is immediate.

## What we collect, when, and why

### 1. Local-only data (no account required, never leaves your device)

These live only in the app's local database and the platform's secure preferences store. They do not leave your device unless you opt into Cloud sync (see §2):

- Vehicles you add: registration, make/model/year, photo, mileage history, finance contract, insurance details, MOT/tax expiry.
- Refuel records: date, fuel grade, litres, price, odometer, station, notes.
- Expenses: date, cost, category, odometer, optional receipt photo, notes.
- Service records: date, mileage, work performed, cost, notes.
- Reminders, favourites, and your unit / theme preferences.

You can delete any of these at any time by tapping the row.

### 2. Cloud sync data (Pro subscription, opt-in)

If you create an account and enable Cloud sync, the data in §1 is uploaded to our backend (hosted on Supabase, in the EU/UK region). It is:

- **Encrypted in transit** via HTTPS / TLS.
- **Isolated per user** by row-level security — your account can only ever read and write its own rows.
- **Mirrored, not migrated.** The local database remains the source of truth on each device; the cloud is a replication target.

The cloud also stores:

- The **identifier from your chosen sign-in method** — your email address and a salted password hash (managed by Supabase Auth, we never see the plaintext), **or**, if you sign in with **Google**, the account identifier Google returns. Signing in with Google shares your basic profile (email address) with us for the sole purpose of creating and identifying your account; we do not access your Google contacts, Drive or any other Google data.
- Your **subscription tier** (`free` / `pro`), set by RevenueCat's webhook after a successful purchase.

### 3. In-app purchase data (only when you subscribe)

If you purchase a Pro subscription, the purchase is processed by Apple or Google under that platform's policy. We use **RevenueCat** to receive purchase notifications and reconcile entitlements. RevenueCat receives:

- Your IGNITE account identifier (so the entitlement attaches to your account, not the device).
- Purchase metadata from the App Store / Play Store (product ID, expiry, renewal status, country).

RevenueCat's own privacy policy applies to the data it stores — see [revenuecat.com/privacy](https://www.revenuecat.com/privacy).

We do **not** receive your payment card details, your Apple ID, or your Google account password — only the store-provided purchase receipt.

### 4. Vehicle lookup (DVLA + DVSA)

When you add a vehicle by registration, the registration is sent to our lookup service, which queries the **UK DVLA Vehicle Enquiry Service** and the **DVSA MOT History Service** on your behalf. The result (make, model, fuel type, CO₂, MOT history) is returned to the app and stored locally.

We log lookups for rate-limiting and abuse prevention. The log row contains your account identifier (or, for unauthenticated lookups, a hashed device identifier), the queried registration, and a timestamp. It is retained for **30 days**, then purged.

### 5. Fuel-price corrections (optional, Pro + sync only)

If you submit a correction to a fuel station's listed price, the correction is uploaded with your account identifier, the station ID, fuel grade, observed price and timestamp. Other users may benefit from the corrected price; your identity is **never** disclosed to them — only the aggregate value.

### 6. Feedback (optional)

If you send feedback via the in-app form, the message text and your account identifier (if signed in) are uploaded to our feedback service. We use this to fix bugs and prioritise features. We do not respond unless you include contact details in the message.

### 7. Usage analytics (PostHog)

To understand which features are used and to find crashes and broken flows, IGNITE includes **PostHog** product analytics. This is the only third-party analytics in the app, and it is engineered to carry no personal data:

- **Anonymous.** Events are keyed to a random per-install identifier. We never link them to your identity, so your email, account ID, registration plates, notes and location are **never** attached to analytics.
- **What's recorded:** screen views and taps, plus a few named actions used for funnels — a refuel, expense, service or vehicle was added; a station price was flagged or submitted. Event details are limited to flags, categories and counts, never free text or identifiers.
- **Session replay** is enabled with **every text input and image masked**, so odometer photos, receipts, registration plates and sign-in fields never leave your device.
- **EU-hosted** for UK/EU data residency.
- **You can turn it off.** Settings → "Share usage analytics" flips consent and is remembered across launches. Analytics is currently **on by default**.

PostHog's own privacy policy applies to the data it processes — see [posthog.com/privacy](https://posthog.com/privacy).

### 8. Permissions IGNITE asks for

| Permission | Why | Data leaves device? |
| --- | --- | --- |
| **Camera** | OCR your odometer, fuel pump display or receipt to auto-fill fields. Recognition runs **on-device** via Google ML Kit. | No. |
| **Photo library** | Attach a vehicle, service or receipt image. Uploaded to cloud storage only if Cloud sync is on. | Only with Cloud sync. |
| **Location (foreground only)** | Show fuel prices at stations near you. A radius search against our station database; we do not log your coordinates. | Used in-memory; not retained. |
| **Notifications** | Service / MOT / tax reminders you set yourself. Scheduled locally; no push tokens are uploaded. | No. |

We do **not** ask for: contacts, microphone, background location, motion or calendar.

### 9. Children

IGNITE is not directed at children under 13. We do not knowingly collect data from anyone under the UK age of digital consent (13). If you believe a child has created an account, [contact us](mailto:{{ site.contact_email }}) and we will delete it.

## How long we keep your data

- **Local data**: until you delete it or uninstall the app.
- **Cloud-synced data**: until you turn Cloud sync off (which removes it from the server) or delete your account (which removes everything).
- **Lookup log rows**: 30 days.
- **RevenueCat purchase history**: per RevenueCat's retention; we have no control over this.
- **Analytics events (PostHog)**: per PostHog's retention; they contain no personal data and cannot be tied back to you.
- **Auth records**: until you delete your account.

## How to delete your data

- **Locally**: uninstall the app, or use the in-app Reset feature in Settings → Danger zone.
- **In the cloud / your account**: see the dedicated [Delete your account]({{ '/delete-account/' | relative_url }}) page. The deletion is **immediate and irreversible**.
- **Your store-side subscription** continues until its current billing period ends. Manage cancellation in the App Store / Play Store subscription page (the Account screen deep-links you there).

## International transfers

Our backend is hosted in the EU/UK region. If you use IGNITE from outside that region, your data crosses borders to reach the server. We rely on standard contractual clauses for international transfers under UK GDPR Articles 46–49.

## Your rights (UK / EU GDPR)

You have the right to access your data, correct it, delete it, restrict processing, port it to another service, and object to processing. Most of these are exercisable directly in the app (the data is visible, editable and deletable on screen). For a formal request, email [{{ site.contact_email }}](mailto:{{ site.contact_email }}).

We are not required to appoint a Data Protection Officer (our processing volume is below the GDPR threshold), but the contact above receives privacy requests directly.

## Changes to this policy

Material changes are announced in the in-app "What's New" on first launch after the update. The latest version is always available at this URL.
