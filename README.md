# sidekick-web

Marketing landing page for [Sidekick](https://yoursidekick.ca) — your proactive AI life coach.

Hosted on GitHub Pages, served at **https://yoursidekick.ca**.

## Stack

- Static HTML / CSS — no build step
- Inter via Google Fonts
- Sentinel design system (matches the mobile app palette + typography)

## Local preview

Just open `index.html` in a browser. Or:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## Deploy

Pushes to `main` auto-deploy via GitHub Pages (Settings → Pages → Source: `main` / root).

## DNS setup (`yoursidekick.ca`)

At your domain registrar, set:

```
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
AAAA  @     2606:50c0:8000::153
AAAA  @     2606:50c0:8001::153
AAAA  @     2606:50c0:8002::153
AAAA  @     2606:50c0:8003::153
CNAME www   soaapp.github.io.
```

The `CNAME` file in this repo's root tells GitHub Pages which custom domain to serve. Don't delete it.

After DNS propagates (5-30 min), GitHub auto-provisions SSL.

## Waitlist form

The waitlist form in `index.html` posts to `https://submit-form.com/REPLACE_ME`. Before going live, replace the action URL with a real form endpoint. Recommended providers:

- **[Formspark](https://formspark.io)** — paid (~$1/mo), simple POST endpoint
- **[Tally](https://tally.so)** — free tier, embed iframe or POST to API
- **[Buttondown](https://buttondown.email)** — paid, also handles email newsletters

## Files

- `index.html` — single-page landing
- `style.css` — Sentinel design system, light + dark mode
- `CNAME` — custom domain binding for GitHub Pages
- `privacy.html` — privacy policy (TODO: customize for production)
- `terms.html` — terms of service (TODO: customize for production)
- `favicon.svg` — Sidekick lightning-bolt favicon
