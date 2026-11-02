# Bundle Up Care Foundation Website

A single-page website for **Bundle Up Care Foundation**, a charity that collects clothes, shoes and toys from well-wishers and distributes them to families raising children aged 0-5.

**Founder & Owner:** Maureen Chebet

---

## What's in the project

```
bundle-up-care-foundation.html    The entire website (one file)
README.md                         This file
```

It's one self-contained HTML file. There is no build step, no dependencies to install and no server needed. The logo is embedded inside the file, so nothing else has to travel with it.

The only external resource is Google Fonts (Fraunces, Karla and Petit Formal Script). If a visitor is offline, the site falls back to Georgia and system sans-serif and still looks fine.

## Page sections

| Section | Purpose |
|---|---|
| Hero | Headline, short mission, "Donate via WhatsApp" and "Get involved" buttons |
| Who we help | Why the foundation exists, and the 0-5 age range it serves |
| What we accept | Clothes, shoes and toys, with no condition requirements |
| How it works | Give, collect, sort, deliver |
| Our story | Why the foundation started, signed by Maureen Chebet |
| Get involved | Donate, help with shipping, sort and pack, spread the word |
| Contact | WhatsApp and Email buttons |
| Footer | Quick links and WhatsApp |

## How visitors contact the foundation

There is no backend, so the site never collects or stores anything. Every contact button hands the visitor off to an app on their own device:

- **WhatsApp:** opens a chat with a pre-filled message ("Hi Bundle Up Care, I'd like to donate.")
- **Email:** `mailto:` link that opens the visitor's email app

Maureen receives messages directly in her own WhatsApp and inbox. This is deliberate, because a form on a static page can't send anything to anyone without a backend service.

## Things to update before going live

1. **Email address.** `hello@bundleupcare.org` is a placeholder. Search the file for it and replace it with the real address (it appears in the contact section).
2. **WhatsApp message.** To change the pre-filled text, find `wa.me/` followed by the number, then `?text=`, and edit the URL-encoded text after it.
3. **WhatsApp number.** The number is not shown on the page, but it is inside the WhatsApp links (`wa.me/...`). Search for `wa.me` to change it.
4. **Story wording.** The "Our story" text is a draft. Maureen should edit it into her own words.
5. **Social links.** None are included yet. Add Instagram, Facebook or TikTok links to the footer once the accounts exist.

## Colours and fonts

The palette is taken from the foundation's logo and set as CSS variables at the top of the `<style>` block.

| Variable | Colour | Used for |
|---|---|---|
| `--cream` | `#FBF4EC` | Page background |
| `--ink` | `#3E1E16` | Text, dark contact band |
| `--rose-deep` | `#C46B78` | Buttons, highlights |
| `--gold` | `#C79A44` | Step numbers, accents |

Change a value once and it updates everywhere. A dark theme is included and follows the visitor's device setting automatically.

**Fonts:** Fraunces for headings, Karla for body text, Petit Formal Script for the single script accent word.

## Hosting and domain

The site is hosted on **Vercel**, which provides the default `bundle-up-care-foundation.vercel.app` address. The custom domain `bundleupfoundation.org` (and `www.bundleupfoundation.org`) was bought from **Namecheap** and connected to the Vercel project. Any static host would also work, since the site is one plain HTML file.

Vercel does not host email. For a `hello@bundleupfoundation.org` address, Namecheap offers email forwarding with the domain (to Maureen's Gmail, for example), or a mailbox can be added through Zoho Mail or Google Workspace. Where the forwarding is set up depends on whether the domain's DNS is managed at Namecheap or at Vercel.

## Making changes later

Because everything lives in one file, edits are simple text changes. The one exception is the logo, which is stored as a long base64 string inside the `<img src="data:image/jpeg;base64,...">` tags. To swap the logo, convert the new image to base64 and replace that string in all three places (nav, hero, footer), or ask Claude to rebuild the file with the new logo.

## Current status

- **Live site:** https://www.bundleupfoundation.org (the root domain `bundleupfoundation.org` redirects here)
- **Backup address:** https://bundle-up-care-foundation.vercel.app
- **Hosting:** Vercel. The `vercel.app` address is the only link Vercel provided
- **Domain:** `bundleupfoundation.org` was bought from Namecheap and connected to the Vercel project
- Links, logo, fonts and WhatsApp button tested and working
- Placeholder email (`hello@bundleupcare.org`) still needs replacing with a real address
- No donor-tracking or payment features yet. Contact is by WhatsApp and email only

## Redeploying after a change

1. Edit the HTML file (rename it to `index.html` if it isn't already).
2. Upload or push it to the Vercel project, or the GitHub repo connected to it.
3. Vercel redeploys automatically and the live site updates within a minute or so.
