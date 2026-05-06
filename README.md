# Quick and Secure Note - Landing Page Setup

## Setup Cepat (5 Langkah)

### Langkah 1: Buat Repository GitHub
1. Go ke https://github.com/new
2. Repository name: `note` (atau bebas)
3. Make it **Public**
4. Click "Create repository"

### Langkah 2: Upload File
```bash
# Cloning repository
git clone https://github.com/YOUR_USERNAME/note.git
cd note

# Copy index.html ke folder ini
# (File sudah ada di folder ini)

# Push ke GitHub
git add .
git commit -m "Add landing page for Quick Note"
git push origin main
```

### Langkah 3: Enable GitHub Pages
1. Go ke repository settings
2. Scroll ke "Pages" (bagian kiri)
3. Select "Deploy from a branch"
4. Select branch: `main` 
5. Folder: `/ (root)`
6. Click "Save"
7. **Tunggu 2-3 menit** sampai live

### Langkah 4: Setup Custom Domain (extension.irwandi.com/note)

**Option A: Jika sudah punya domain irwandi.com**

1. Go ke DNS provider (GoDaddy, Cloudflare, etc)
2. Tambah CNAME record:
   ```
   Name: extension
   Type: CNAME
   Value: YOUR_USERNAME.github.io
   ```
3. Di GitHub repository Settings > Pages:
   - Custom domain: `extension.irwandi.com`
   - Centang "Enforce HTTPS"
   - Tunggu SSL certificate (5-10 menit)

**Option B: Path-based (tanpa subdomain)**
Jika Anda sudah punya website di extension.irwandi.com, cukup:
```html
<!-- Link ke landing: extension.irwandi.com/note -->
<!-- Gunakan GitHub Pages standalone atau iframe -->
```

### Langkah 5: Verify
1. Buka: `https://YOUR_USERNAME.github.io/note` atau `https://extension.irwandi.com`
2. Harus live dan responsive

---

## Folder Structure

```
note/
├── index.html          ← Landing page utama
├── README.md           ← File ini
└── .github/
    └── workflows/      ← (Optional) Auto-deploy
```

---

## Mengapa GitHub Pages Optimal?

| Feature | GitHub Pages | Netlify | Vercel |
|---------|--------------|---------|--------|
| **Cost** | FREE ✓ | FREE | FREE |
| **Setup Time** | 5 min ✓ | 10 min | 10 min |
| **Custom Domain** | YES ✓ | YES | YES |
| **HTTPS** | AUTO ✓ | AUTO | AUTO |
| **Bandwidth** | Unlimited ✓ | Generous | Generous |
| **Complexity** | Minimal ✓ | Moderate | Moderate |

---

## Keuntungan Pakai Claude Design

✅ **Cepat**: HTML murni + Tailwind CDN = Load <1s
✅ **Simple**: Hanya 1 file HTML, tanpa build process
✅ **Responsive**: Tested di mobile/tablet/desktop
✅ **SEO-ready**: Meta tags, semantic HTML
✅ **No Dependencies**: Hanya Tailwind dari CDN (cached globally)
✅ **Git-friendly**: Easy to maintain dan deploy

---

## Tips Customization

### 1. Ganti warna (dari purple ke brand color)
```html
<!-- Cari "from-purple-600" dan ganti -->
<!-- Contoh blue: from-blue-600 to-blue-700 -->
```

### 2. Ganti Chrome Web Store link
```html
<!-- Cari "chromewebstore.google.com" -->
<!-- Ganti dengan: https://chromewebstore.google.com/detail/[YOUR_EXT_ID] -->
```

### 3. Tambah testimonial section
Cukup copy-paste feature card dan modify content.

### 4. Analytics (Optional)
```html
<!-- Add sebelum closing </body> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>
```

---

## Maintenance

### Update landing page:
```bash
git add index.html
git commit -m "Update landing page"
git push origin main
```
Changes live dalam **2-3 menit otomatis**.

### Monitor Performance:
- Google Lighthouse: https://pagespeed.web.dev
- GitHub Pages Stats: Repository > Insights > Traffic

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Domain not working | Check CNAME record, wait 30min, clear browser cache |
| HTTPS error | Wait 10min, GitHub auto-provisions SSL |
| 404 error | Check if branch is `main`, folder is root `/` |
| Slow load | Check Tailwind CDN, it's cached globally (fast) |

---

## Next Steps

1. ✅ Deploy landing page
2. 📱 Create Chrome Extension
   - manifest.json
   - popup.html / popup.js
   - background.js
   - storage logic
3. 🚀 Submit to Chrome Web Store
4. 📊 Add analytics
5. 💬 Collect user feedback

---

**Selesai!** Landing page Anda live di GitHub Pages dengan custom domain. 🎉
