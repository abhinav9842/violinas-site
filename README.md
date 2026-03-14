# Violinas — Website

Landing page for [violinas.com](https://violinas.com) — a modern demi-fine jewellery brand.

---

## 🚀 Deploying to GitHub Pages

### Step 1 — Create a GitHub repo

1. Go to [github.com/new](https://github.com/new)
2. Name the repo `violinas-site` (or `<yourusername>.github.io` for a user site)
3. Set it to **Public**
4. Click **Create repository**

### Step 2 — Push the site files

```bash
cd violinas/site
git init
git add .
git commit -m "Initial launch — Violinas landing page"
git branch -M main
git remote add origin https://github.com/<yourusername>/violinas-site.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)`
4. Click **Save**
5. GitHub will give you a URL like `https://<yourusername>.github.io/violinas-site`

### Step 4 — Add Custom Domain

1. In **Settings → Pages → Custom domain**, enter: `violinas.com`
2. Click **Save** — GitHub will create/verify the CNAME file
3. Tick **Enforce HTTPS** once DNS propagates (can take up to 48h)

---

## 🌐 GoDaddy DNS Configuration

Log into GoDaddy → **My Products** → **violinas.com** → **DNS** → **Manage DNS**

**Delete any existing A records for `@`, then add these:**

| Type  | Name | Value               | TTL  |
|-------|------|---------------------|------|
| A     | @    | 185.199.108.153     | 1hr  |
| A     | @    | 185.199.109.153     | 1hr  |
| A     | @    | 185.199.110.153     | 1hr  |
| A     | @    | 185.199.111.153     | 1hr  |
| CNAME | www  | `<yourusername>.github.io` | 1hr |

> Replace `<yourusername>` with your actual GitHub username.

**DNS propagation takes 15 min – 48 hours.** You can check progress at [dnschecker.org](https://dnschecker.org).

---

## 🖼 Swapping in Real Product Images

Replace the gradient placeholders in the product cards and Instagram grid with real product images:

```html
<!-- In index.html, find each product-placeholder div and add a style: -->
<div class="product-placeholder p1" style="background-image: url('assets/ring.jpg'); background-size: cover; background-position: center;"></div>
```

Or via CSS in `style.css`:
```css
.p1 { background-image: url('assets/heirloom-ring.jpg'); background-size: cover; background-position: center; }
```

Place images in `violinas/site/assets/`.

---

## 📸 Instagram Feed

The Instagram tiles are currently static placeholders linking to [@violinas__](https://www.instagram.com/violinas__/).

To embed real Instagram posts, you can:
- Use [Behold.so](https://behold.so) (free tier available) — generates a `<script>` embed widget
- Or manually add screenshot images of your posts as the tile backgrounds

---

## 🎨 Brand Colours

| Name | Hex |
|---|---|
| Dusty Mauve | `#C4B0B8` |
| Deep Violet | `#3C1F5C` |
| Soft Lavender | `#C9A8E0` |
| Warm White | `#FAF6FF` |
| Black | `#0D0D0D` |

Fonts: **Cormorant Garamond** (headings) + **DM Sans** (body) via Google Fonts.
# violinas-site
