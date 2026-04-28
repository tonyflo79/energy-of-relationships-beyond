# Energy of Relationships — WordPress Install Guide

A self-contained landing page for WordPress (works on GHL's WordPress Hosting or any standard WordPress install). Estimated install time: **10 minutes**.

## What's in this folder

```
wordpress-build/
├── index.html                    ← The full page (CSS inlined, ready to paste)
├── images/                       ← 11 images to upload to WP Media Library
│   ├── eor-asprey-headshot.png
│   ├── eor-dr-barry.jpg
│   ├── eor-hands.jpg
│   ├── eor-heart.png
│   ├── eor-gut.png
│   ├── eor-spine.png
│   ├── eor-fail-01-networking.jpg
│   ├── eor-fail-02-communication.jpg
│   ├── eor-fail-03-selfhelp.jpg
│   ├── eor-fail-04-therapy.jpg
│   └── eor-fail-05-willpower.jpg
└── WORDPRESS-INSTALL.md          ← This file
```

## Install steps

### 1. Upload images to Media Library

- WP admin → **Media → Add New**
- Drag all 11 files from `images/` into the uploader at once
- After upload, click any image → copy the **File URL**. It will look like:
  `https://yourdomain.com/wp-content/uploads/2026/04/eor-hands.jpg`
- The **base path** (everything before the filename) is what you'll use:
  `https://yourdomain.com/wp-content/uploads/2026/04`

> ⚠️ If a file already exists with the same name in your Media Library, WP will rename to `eor-hands-1.jpg` etc. To avoid this, upload to a fresh month or empty the trash first.

### 2. Find-and-replace placeholders in `index.html`

Open `index.html` in any text editor and do **two** find-and-replace passes:

| Find | Replace with |
|---|---|
| `[WP_MEDIA_BASE]` | The base URL from step 1 (e.g. `https://yourdomain.com/wp-content/uploads/2026/04`) — **no trailing slash** |
| `[CHECKOUT_URL]` | Your GHL checkout URL with the $200 coupon embedded (so the customer lands on a $197 checkout) |

Save the file.

### 3. Create the WordPress page

- WP admin → **Pages → Add New**
- Title: `Energy of Relationships` (or whatever — affects only the URL slug)
- **Page Attributes → Template:** choose **Blank Canvas** / **Full Width No Sidebar** / **Elementor Canvas**, depending on your theme. (If your theme has no blank template, install the free *Page Builder Framework* or *Hello Elementor* theme — both ship with one.)
- In the editor, click `+` to add a new block → search for and add a **Custom HTML** block
- Open the modified `index.html` from step 2, copy **everything between `<body>` and `</body>`** (don't include the `<head>` — that goes in step 4)
- Paste into the Custom HTML block
- Click **Preview** to verify before publishing

### 4. Add the page-level styles + Google Fonts to `<head>`

The page needs the inline `<style>` block and Google Fonts link in `<head>`. Two options:

**Option A — Page-level (preferred):** Use a plugin like *Insert Headers and Footers* (by WPCode) or *Header Footer Code Manager*. Install → activate → on the page edit screen there's now a "Per-page custom code" section. Paste:

- Everything between `<head>` and `</head>` from `index.html` (the Google Fonts `<link>` lines + the entire `<style id="eor-inline-styles">...</style>` block)

**Option B — Site-wide:** WP admin → **Appearance → Customize → Additional CSS**. Paste only the contents inside `<style>...</style>` (without the tags). For Google Fonts, use the same Insert Headers and Footers plugin's site-wide section. Less ideal because the styles will load on every page, but works.

### 5. Publish + verify

- Click **Publish**
- View the page. Check on mobile.
- Verify the **Enroll Now** button on the pricing card hits your GHL checkout (and that the coupon auto-applies, dropping price to $197).
- Verify all 11 images load (no broken icons).

## GHL-specific add-ons (optional)

Once the page works, layer on:

- **GHL tracking pixel** — paste the GHL site script into the same Insert Headers and Footers plugin (header section)
- **Facebook / Google Ads pixels** — same place
- **Heatmap / scroll depth** (Hotjar, Microsoft Clarity) — same place

## Editing later

Two paths:

1. **Quick text edits:** WP page editor → click the Custom HTML block → edit. WP doesn't lint HTML, so be careful with closing tags.
2. **Visual / structural changes:** edit `index.html` locally, re-paste the body into the Custom HTML block. Source of truth lives in your local file or the GitHub repo (`tonyflo79/energy-of-relationships`).

## Troubleshooting

| Problem | Fix |
|---|---|
| Page is constrained to a narrow column | Theme is wrapping content in a max-width container. Switch to a Blank Canvas / Full Width template (step 3). |
| Fonts look wrong (default serif) | The Google Fonts `<link>` didn't make it into `<head>` — see step 4. |
| Mandala SVG missing in hero | Custom HTML block stripped it. Try the *Custom HTML* block (Gutenberg core), not a "Code" or "Shortcode" block. |
| Mobile menu / theme header showing on top | Blank Canvas template should hide them. If it doesn't, use a "no-header" template variant. |
| Images load slowly | First load only — WP Rocket / WP Super Cache will fix. |

## What's NOT in this build

- No forms (all CTAs link straight to `[CHECKOUT_URL]` — no GHL form integration needed)
- No sticky timer bar (intentionally removed in the BEYOND edition)
- No A/B testing wiring (add via GHL or Convert.com if needed)

## File checksums (for your records)

Run `shasum -a 256 images/*` to verify the 11 images haven't been tampered with after handoff.
