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
`http://readingjournal.rlbdesigns.com/`
---

## Adding a new book to the catalog

Open `rlb-catalog.json` and copy/paste one of the existing blocks:

```json
{
  "title": "Your New Book Title",
  "author": "R.L. Baldwin-RLBdesigns",
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
- White: `#ffffff`
- black: `#000000`
---

## Setup instructions

### Step 1 — Create a GitHub account
github account rlbaldwin9-hub

### Step 2 — Create a new repository
1. Click the **+** icon → **New repository**
2. Name it: `rlb-reading-journal`
3. Set to **Public**
4. Click **Create repository**

### Step 3 — Upload your files
1. Click **uploading an existing file** (or drag-and-drop)
2. Upload both `index.html` and `rlb-catalog.json`
3. Click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to your repo → **Settings** → **Pages** (left sidebar)
2. Under **Source**, select **Deploy from a branch**
3. Branch: `main` | Folder: `/ (root)`
4. Click **Save**
5. Wait ~2 minutes, then visit the URL shown

### Step 5 — (Optional) Connect your custom domain
If you want `readingjournal.rlbdesigns.com` instead of the GitHub URL:

1. In repo Settings → Pages → **Custom domain**, enter: `journal.rlbdesigns.com`
2. Click Save (this creates a `CNAME` file automatically)
3. In your domain registrar's DNS settings, add a CNAME record:
   - **Name:** `readingjournal`
   - **Points to:** `rlbaldwin9-hub.github.io`
4. Wait up to 24 hours for DNS to propagate
5. Check **Enforce HTTPS** once it's read
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
https://rlbaldwin9-hub.github.io/rlb-reading-journal/
```
Or link to it from your navigation menu as an external page.

---

*Built for RLB Designs by Claude · rlbdesigns.com*
