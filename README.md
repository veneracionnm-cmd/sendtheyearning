# Whisper — anonymous message starter

A simple static website for sending anonymous messages and giving the recipient a private link.

## What you need

- A free GitHub account
- A free Supabase project
- A GitHub Pages site

## 1. Create the database

In Supabase, open **SQL Editor**, paste `supabase.sql`, and run it.

## 2. Get your Supabase credentials

In your Supabase project's API settings, copy:

- Project URL
- Publishable/anon key

Put them in `config.js`:

```js
window.SUPABASE_URL = ["YOUR_SUPABASE_URL";](https://kyeekzgznuxwcfrpnujm.supabase.co)
window.SUPABASE_ANON_KEY = sb_publishable_5CRpFDAeh1qWKgcOEIXa9w_hvHkYanT
```

Never put a `service_role` or secret key in a public website.

## 3. Test locally

You need a local web server because browsers can block some files opened directly with `file://`.

For example, with Python installed:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## 4. Publish with GitHub Pages

Create a GitHub repository, upload all files, then enable:

**Settings → Pages → Deploy from branch → main → /(root)**

GitHub will give you a free `github.io` address.

## Important privacy note

This starter intentionally uses a random private token instead of public name search. The recipient's name is displayed only after the private message URL is opened.

Before launching publicly, add:

- Report/abuse functionality
- Rate limiting / CAPTCHA
- Message deletion or expiration
- Better server-side validation
- A privacy policy and terms
- Moderation controls
- Protection against spam and harassment

The current SQL read policy is deliberately simple for a starter. For a production app, consider moving message reads/writes behind an Edge Function or other server-side layer and tightening abuse controls.
