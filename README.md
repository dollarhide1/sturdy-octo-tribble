# RN at 50 — The Confidence & Action Companion (landing / sales site)

This is the **public sales page** for the companion. It's a single self-contained
HTML page — no build step, no dependencies — that tells the story and sends visitors
to your Payhip checkout (payments processed by Stripe).

> The paid product itself (the interactive companion) is **not** in this folder, and
> should **not** be hosted publicly — otherwise anyone could use it without buying.
> It's delivered to customers through Payhip. See "The product file" below.

---

## Files in this folder (deploy these to Netlify)

| File | Purpose |
|------|---------|
| `index.html` | The landing / sales page |
| `social-cover.jpg` | Preview image when the link is shared (1200×630) |
| `favicon.svg` | Browser tab icon |
| `404.html` | Friendly "page not found" page |
| `netlify.toml` | Netlify settings (publish folder + headers) |
| `robots.txt`, `.gitignore` | Housekeeping |

---

## Before you publish — 2 things to edit in `index.html`

Open `index.html` in any text editor and:

1. **Set your price.** Find `$19` (in the offer card) and change it to your real price.
2. **Add your Payhip link.** Find every occurrence of
   `https://payhip.com/b/XXXXXX` and replace it with your product's Payhip URL
   (it looks like `https://payhip.com/b/AbCdE`). There are two — the offer card
   button and the final call-to-action button.

That's it. (Tip: most editors have Find & Replace — replace `https://payhip.com/b/XXXXXX`
everywhere in one go.)

---

## The product file (upload this to Payhip)

In the separate **`payhip-product`** folder you'll find:

- `RN-at-50-The-Confidence-and-Action-Companion.html` — the actual companion
- `Open Me First.txt` — a short welcome/instructions note for buyers

Set Payhip up like this:

1. Create a free account at <https://payhip.com> and click **Add new product →
   Digital product**.
2. **Upload the file(s)** from `payhip-product` (you can upload both, or the provided
   zip). Payhip delivers them to customers automatically after purchase.
3. Set your **price**, title, description, and cover image (you can reuse
   `social-cover.jpg`).
4. **Connect Stripe** under Payhip **Account Settings → Payment methods** so payouts
   go to your Stripe account.
5. Publish, then copy the product's link (e.g. `https://payhip.com/b/AbCdE`) and paste
   it into `index.html` as described above.

### Optional: in-page checkout overlay
If you'd rather buyers check out without leaving your page, Payhip provides a "buy
button" embed snippet in your product's **Share / Embed** tab. Copy that exact snippet
from your dashboard and swap it in for the buttons — it opens the checkout in an
overlay. (The simple link above works perfectly well too.)

---

## Deploy the sales page to Netlify

**Fastest:** go to <https://app.netlify.com/drop> and drag this folder onto the page.

**Recommended (auto-updates):** push this folder to a GitHub repo, then in Netlify
choose **Add new site → Import an existing project → GitHub**. Leave the build command
empty; the publish directory is `.` (already set in `netlify.toml`).

### Custom domain & share previews (optional)
Add a custom domain in Netlify (free HTTPS). Once you know your address, you can set the
`og:image` / `twitter:image` tags near the top of `index.html` to the full URL,
e.g. `https://yourdomain.com/social-cover.jpg`, so link previews are bulletproof.

---

## Optional email signup
The page includes a "Keep me posted" form wired for **Netlify Forms** — once hosted on
Netlify, submissions appear under **Forms** in your dashboard automatically (great for
people who aren't ready to buy yet). Delete the `<div class="email-card">…</div>` block
in `index.html` if you don't want it.
