# Holders LLC — Website

Static site (plain HTML/CSS, no build step needed). Ready to deploy to Vercel.

## Pages
- `index.html` — Home
- `services.html` — Services
- `concealed-carry.html` — Concealed Carry
- `privacy-policy.html` — Privacy Policy (fill in bracketed placeholders)
- `terms.html` — Terms & Conditions (fill in bracketed placeholders)
- `refund-policy.html` — Refund Policy (fill in bracketed placeholders)
- `shipping-policy.html` — Shipping Policy (fill in bracketed placeholders)

Search each legal page for `[Insert ...]` and replace with your real business
address, email, and effective dates before going live. These are starting
templates, not legal advice — have an attorney review them, especially given
firearms-specific rules around recordkeeping, refunds, and shipping.

## Deploy to Vercel

**Option A — GitHub (recommended, enables auto-deploys on future edits)**
1. Create a new GitHub repo and push this folder to it:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/holders-site.git
   git push -u origin main
   ```
2. Go to vercel.com → **Add New Project** → Import the repo.
3. Framework preset: **Other** (it's static HTML, no build command needed).
4. Deploy.

**Option B — Vercel CLI (fastest, no GitHub needed)**
```bash
npm i -g vercel
cd holders-site
vercel        # follow prompts, creates a preview deployment
vercel --prod # promotes to production
```

## Point holders.llc at this project

Since `portal.holders.llc` is already on Vercel, you're likely already
familiar with this part of your Vercel dashboard:

1. In the new Vercel project → **Settings → Domains** → add `holders.llc`
   (and `www.holders.llc` if you want that too).
2. Vercel will give you DNS records to add (usually an A record for the
   apex domain and/or a CNAME for `www`).
3. Update those records wherever `holders.llc`'s DNS is currently managed
   (likely your GoDaddy account, since that's where the domain/portal
   issue started). If GoDaddy is the domain registrar, you can keep it
   registered there and only change the DNS records/nameservers to point
   to Vercel — no need to transfer the domain itself.
4. Vercel auto-provisions SSL/HTTPS once DNS resolves — this satisfies the
   "secure checkout page / HTTPS" requirement from your payment processor.

`portal.holders.llc` is unaffected by this as long as its own DNS record
stays as-is.
