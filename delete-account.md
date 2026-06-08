---
layout: page
title: Delete your account & data
permalink: /delete-account/
updated: 8 June 2026
description: How to delete your IGNITE account and all associated data — from inside the app, or by request if you no longer have it installed.
---

This page explains how to delete your **IGNITE** account and all associated data.

## What an IGNITE account is

IGNITE works fully offline by default — **no account is required**. You only have an account if you signed in (with email + password, or with Google) to turn on **Cloud sync**. If you never signed in, there is no server-side account or data to delete; uninstalling the app removes everything (see "If you don't have an account" below).

## Option 1 — Delete from inside the app (fastest)

<ol class="steps">
  <li>Open IGNITE.</li>
  <li>Go to <strong>Settings → Account</strong>.</li>
  <li>Under <strong>Danger zone</strong>, tap <strong>Delete account</strong>.</li>
  <li>Confirm.</li>
</ol>

<div class="callout"><p>The deletion is <strong>immediate and irreversible</strong>. It runs server-side and removes your authentication record; every per-user table cascades, so all of your rows are removed in the same transaction.</p></div>

## Option 2 — Request deletion by email (no app needed)

If you've uninstalled IGNITE, can't sign in, or simply prefer to ask us, email:

**[{{ site.contact_email }}](mailto:{{ site.contact_email }}?subject=Delete%20my%20IGNITE%20account)**

Use the subject line **"Delete my IGNITE account"** and send from the email address associated with your account (or, for Google sign-in, the Google account email) so we can verify the request. We action verified requests within **30 days** — usually far sooner — and confirm by reply once complete.

## What gets deleted

- Your **authentication record** (email address and salted password hash, or the Google account identifier).
- All **cloud-synced records**: refuels, expenses, services and vehicles.
- Your **account identifier** wherever it appears: lookup-usage logs, price-report corrections, in-app feedback, finance contracts, favourites and MOT advisories.

The deletion is **permanent** — none of this data is recoverable afterwards.

## What is *not* deleted by this request

- **Local data on your device.** Records you never synced live only in the app's on-device database. Deleting the app, or tapping each row's delete action, removes them — there is nothing on our servers to delete.
- **Your store-side subscription.** An App Store / Google Play subscription continues until the end of its current billing period. Cancel it in the App Store or Play Store subscription settings (the Account screen deep-links you there). Deleting your account does not refund or cancel an active subscription.

## If you don't have an account

If you never signed in and enabled Cloud sync, all your data is local to your device. **Uninstalling IGNITE deletes it.** We hold nothing server-side for you.

## Questions

Anything about deletion or another data request: [{{ site.contact_email }}](mailto:{{ site.contact_email }}).
