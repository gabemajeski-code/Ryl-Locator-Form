# Ryl Locator Form (Ready to Deploy)

This project is the complete tool we discussed:
- Minimalist, modern single-input form
- CLEAR + CHECK buttons
- Instant validation against your provided dataset
- Human-error tolerance (typos, formatting differences, state name vs abbreviation)
- Address auto-suggestions (max 5)
- Store list rendered cleanly (non-overwhelming)
- Unlimited repeat submissions

## What’s inside

```
ryl-locator-form/
  index.html
  api/
    check.js
    suggest.js
    stores.js
  data/
    addresses.json
    stores.json
  package.json
  vercel.json
```

## Deploy (No coding required)

### Option A (Recommended): Vercel + GitHub (fast & free)
1. Create a free Vercel account.
2. Create a GitHub account (if you don’t have one).
3. Create a new GitHub repository (any name).
4. Upload the **contents** of the `ryl-locator-form` folder into that repo.
5. In Vercel, click **New Project** → Import that repository → Deploy.

That’s it. Vercel will give you a live URL you can send to people.

### Option B: Drag-and-drop deploy (also works)
If you prefer not to use GitHub:
1. Install the Vercel desktop / CLI (Vercel provides steps)
2. Deploy the folder

(If you'd like, tell me which route you prefer and I’ll tailor the clicks exactly to your screen.)

## How matching works (your requirements implemented)

- The tool extracts ZIP if present (5 digits).
- If ZIP is present, it uses ZIP as the primary filter (most reliable).
- Then it checks Street / City / State with fuzzy similarity.
- A match is confirmed if:
  - ZIP matches (when provided), AND
  - at least **2 of 3** fields (Street/City/State) are close enough.

If there’s no match, the form shows the exact message you requested:
> “Please try another location or ensure correct spelling”

## Updating your dataset later

This build uses your current Excel dataset converted into JSON files:
- `data/addresses.json`
- `data/stores.json`

If you later want to update the dataset, the simplest workflow is:
1. Replace the JSON files with updated ones
2. Redeploy on Vercel (it redeploys automatically when you update GitHub)

If you want, I can also provide a one-click “converter” script for your computer to regenerate JSON from a new Excel file.

---

You can now share the deployed URL and users can submit as many checks as they want, instantly.
