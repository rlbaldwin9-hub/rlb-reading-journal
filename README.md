# RLB Designs Reading Journal

A beautiful, interactive reading journal for [rlbdesigns.com](https://rlbdesigns.com) — built as a free static site hosted on GitHub Pages.

## What's included

| File | Purpose |
|------|---------|
| `index.html` | The full reading journal app |
| `rlb-catalog.json` | Your live book catalog — edit this to add new titles |

## Live site

Once deployed, your journal will be live at:
`https://rlbaldwin9-hub.github.io/rlb-reading-journal/`

Or at your custom domain if configured.

---

## Adding a new book to the catalog

Open `rlb-catalog.json` and copy/paste one of the existing blocks:

```json
{
  "title": "Your New Book Title",
  "author": "R.L. Baldwin",
  "genre": "Genre Here",
  "asin": "B0XXXXXXXXX",
  "desc": "A short, warm description of the book (1–2 sentences).",
  "color": "#7a9e87",
  "tags": ["keyword1", "keyword2"]
}
```

**Finding your ASIN:** On any Amazon product page, look at the URL — it contains `/dp/B0XXXXXXXXX`. That 10-character code after `/dp/` is your ASIN.

**Spine colors (your brand palette):**
- Sage: `#7a9e87`
- Blush: `#d4a5a0`
- Gold: `#c9a84c`
- Soft Blue: `#8ba3c4`
- Lavender: `#c4a8d4`
- Warm Tan: `#d4c4a8`

---

### Step 5 — (Optional) Connect your custom domain
If you want `journal.rlbdesigns.com` instead of the GitHub URL:

1. In repo Settings → Pages → **Custom domain**, enter: `journal.rlbdesigns.com`
2. Click Save (this creates a `CNAME` file automatically)
3. In your domain registrar's DNS settings, add a CNAME record:
   - **Name:** `journal`
   - **Points to:** `YOUR-USERNAME.github.io`
4. Wait up to 24 hours for DNS to propagate
5. Check **Enforce HTTPS** once it's ready

### Step 6 — Enable AI Recommendations
1. Get a free API key at [console.anthropic.com](https://console.anthropic.com)
2. Open the journal on your site
3. Click the gold notice bar at the top and paste your key
4. Done — Claude will now power live book recommendations

---

## Updating your catalog (after initial setup)

1. Go to your GitHub repository
2. Click `rlb-catalog.json`
3. Click the **pencil icon** (Edit)
4. Add your new book block to the JSON array
5. Click **Commit changes**
6. Your live site updates within seconds — no code skills needed

---

## Linking from Google Sites

In Google Sites, add an **Embed** element and paste your GitHub Pages URL:
```
https://YOUR-USERNAME.github.io/rlb-reading-journal/
```
Or link to it from your navigation menu as an external page.

---

*Built for RLB Designs by Claude · rlbdesigns.com*
