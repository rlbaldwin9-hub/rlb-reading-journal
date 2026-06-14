# RLB Designs — My Reading Journal
## Interactive reading tracker for rlbdesigns.com readers

**Repo:** `rlbaldwin9-hub/rlb-reading-journal`  
**GitHub Pages URL:** https://rlbaldwin9-hub.github.io/rlb-reading-journal/  
**Live Custom URL:** http://readingjournal.rlbdesigns.com/  
**DNS:** Cloudflare CNAME `readingjournal` → `rlbaldwin9-hub.github.io` (grey cloud / DNS only)

---

## Files in This Repo

| File | Purpose | How often edited |
|------|---------|-----------------|
| `index.html` | The entire app — HTML, CSS, JavaScript | Rarely (bug fixes only) |
| `rlb-catalog.json` | All book data — drives catalog tab AND recommendations | Every new book published |
| `README.md` | This file — for Rachel only, not visible to visitors | As needed |
| `CNAME` | Auto-created by GitHub when custom domain was set | Never touch |

---

## ⚠️ ADDING NEW PUBLISHED BOOKS

**Edit `rlb-catalog.json` only — do NOT edit `index.html`.**

Copy this block, fill in the details, and paste it inside the `[...]` array.  
Add a comma after the closing `}` of the previous entry.

```json
{
  "category": "Cookbooks",
  "subcategory": "",
  "series": "",
  "title": "Your Book Title Here",
  "author": "Rachel Baldwin-RLBdesigns",
  "asin": "B0XXXXXXXXX",
  "siteUrl": "https://www.rlbdesigns.com/books/[path]",
  "desc": "A one or two sentence description that captures the heart of the book — this is what the recommendation engine reads.",
  "color": "#7a9e87",
  "tags": ["clean eating", "alpha-gal", "dairy-free", "gluten-free", "wellness"]
}
```

### Steps to add a book on GitHub:
1. Go to https://github.com/rlbaldwin9-hub/rlb-reading-journal
2. Click `rlb-catalog.json`
3. Click the **pencil ✏️** icon
4. Add the new book block (with comma after the previous entry)
5. Validate your JSON at **https://jsonlint.com** before saving
6. Click **Commit changes** — live site updates within 60 seconds

### Valid `category` values (must match exactly):
`Cookbooks` · `Children's Books` · `Children's Coloring Books` · `Children's Activity Books` · `Adult Coloring Books` · `Journals` · `Notebooks`

### Valid `subcategory` values:
- Children's Books → `PreK–Age 9` or `Pre-Teen Age 9–13`
- Coloring/Activity → `Holiday`
- All others → leave `""`

### Finding your ASIN:
Amazon URL: `https://www.amazon.com/dp/B0XXXXXXXXX` — the ASIN is the 10-character code after `/dp/`

### Spine color palette:
| Hex | Use for |
|-----|---------|
| `#7a9e87` | Cookbooks, wellness, nature (Sage) |
| `#d4a5a0` | Picture books, romance (Blush) |
| `#c9a84c` | Adventure, special titles (Gold) |
| `#8ba3c4` | Sci-fi, space, boys (Soft Blue) |
| `#c4a8d4` | Fantasy, magic, girls (Lavender) |
| `#d4c4a8` | Comfort reads, journals (Warm Tan) |
| `#a8c4c4` | Seafood cookbooks, water (Teal) |
| `#b8c49a` | Nature, garden, homestead (Green) |
| `#3a3028` | Mystery, journals, sophisticated (Dark) |

---

## Features

- **My Shelf** — Log any book with title, author, genre, status, star rating, spine color, notes, dates
- **Log a Book** — Full entry form with color picker and star rating
- **Reading Goals** — Yearly goal with animated ring tracker and milestone badges
- **Recommendations** — Smart local scoring engine + Open Library API. No API key needed. Your catalog books show first.
- **My Catalog** — Full RLB catalog with Category / Sub-category / Series dropdowns + search. Links to rlbdesigns.com and Amazon.
- **Share My List** — Canvas book spine image + shareable URL. Personal notes excluded for privacy.

---

## Updating the App (index.html)

Only needed for bug fixes or new features:
1. Get the **complete updated `index.html`** from Claude — never partial snippets
2. Ask Claude to **validate JavaScript syntax** before delivering
3. Test locally (open in Chrome → F12 → Console — no red errors)
4. Upload to GitHub to replace existing `index.html`
5. Wait 2 minutes → hard-refresh: Ctrl+Shift+R

---

## Tech Notes

- **Data storage:** All reader data in browser `localStorage` — no server needed
- **JSON path:** Must be `./rlb-catalog.json` (relative path) — full domain URL causes CORS error
- **Recommendation engine:** JS scoring with synonym expansion + tag matching + Open Library fallback
- **Buttons in dynamic HTML:** Use `data-*` attributes + event delegation (not inline onclick) to avoid quote-escaping bugs
- **Modal overlay:** `pointer-events: none` when hidden prevents click-blocking

---

## Bug History

| Bug | Cause | Fix Applied |
|-----|-------|-------------|
| Nothing clickable on launch | Unescaped apostrophe `'It's'` in JS string crashed entire script | Escaped as `'It\'s'` |
| All buttons blocked | Modal overlay intercepting pointer events when hidden | Added `pointer-events:none` to hidden modal |
| Add to Journal broken in recs/catalog | Inline `onclick` with `encodeURIComponent` inside template literals caused encoding conflict | Switched to `data-*` attributes + event delegation |
| CORS error loading catalog | Full domain URL used for JSON fetch | Changed to relative `./rlb-catalog.json` |
| Broken links | Missing `www` prefix | Always use `https://www.rlbdesigns.com` |

---

## Backlog / Coming Soon

- [ ] Fill in ASIN fields as books go live on Amazon
- [ ] Enable HTTPS: GitHub Pages → Settings → Pages → Enforce HTTPS (once Cloudflare DNS propagates)
- [ ] Add Notebooks category when ready
- [ ] Add The Enchanted Storyteller's Studio when published
- [ ] Add The Galactic Storyteller's Studio when published
- [ ] Add Micro-Biology Graphic Novel Series when published
- [ ] Add Taco Territory Book 2 when published

---

*© 2025 RLB Designs · Rachel Baldwin · rlbdesigns.com*
