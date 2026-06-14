# Deployment Guide

## Before You Deploy

Update these fields in `index.html`:

1. **Your name** — Replace `KISHORE KANNA S` (header & footer)
2. **Email** — Replace `hello@kishore.dev`
3. **Social links** — Update GitHub, LinkedIn, Twitter profiles
4. **Project links** — Replace GitHub URLs with your actual repos
5. **Meta tags** — Update description and og:title/og:url

## Deploy on GitHub Pages (Free)

### Step 1: Create a Repository

```bash
# If you don't have a repo yet
git init
git add .
git commit -m "Initial portfolio commit"
```

### Step 2: Push to GitHub

```bash
# Option A: Create new repo on GitHub named 'portfolio', then:
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
git branch -M main
git push -u origin main

# Option B: Create repo named 'USERNAME.github.io' for direct deployment
git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repo on GitHub
2. Settings → Pages
3. Select `main` branch as source
4. Save

Your portfolio will be live at:

- `https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io` (if using option B)
- `https://github.com/YOUR_USERNAME/portfolio` → Pages URL (if using option A)

## Deploy on Netlify (Recommended)

### Option 1: Using GitHub (Auto-Deploy)

1. **Create Netlify account** at https://netlify.com
2. **Connect GitHub** to Netlify
3. **Select your portfolio repo**
4. **Build command**: (leave empty)
5. **Publish directory**: `.` (root)
6. **Deploy**

Every push to GitHub will auto-deploy!

### Option 2: Manual Deploy

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
cd /path/to/PORTFOLIO
netlify deploy --prod --dir=.
```

Your portfolio will be live at a Netlify subdomain (e.g., `cozy-badger-1234.netlify.app`)

## Deploy on Vercel (Free)

1. **Create Vercel account** at https://vercel.com
2. **Import project** → Select GitHub repo
3. **Deploy** (auto-configured)
4. Your portfolio is live at `username-portfolio.vercel.app`

Every GitHub push = automatic deploy

## Add a Custom Domain

### Example: Deploy to `kishorekanna.com`

1. **Register domain** at GoDaddy, Namecheap, etc.
2. **Update DNS** to point to hosting provider:
   - Netlify: Add DNS records from dashboard
   - Vercel: Add custom domain in settings
   - GitHub Pages: Add CNAME file + DNS update
3. **Wait 24-48 hours** for DNS propagation

### Using GitHub Pages + Custom Domain

1. Add file `.github/workflows/deploy.yml` (or use GitHub Pages settings)
2. Create `CNAME` file in root with your domain:
   ```
   kishorekanna.com
   ```
3. Push to GitHub
4. Update domain DNS to point to GitHub's servers

## Performance Checklist

- [ ] Minify CSS/JS (optional: use tools like PurgeCSS)
- [ ] Optimize images (compress to < 100KB)
- [ ] Test on mobile browsers
- [ ] Check Google PageSpeed Insights
- [ ] Verify SEO metadata in `<head>`
- [ ] Test contact form submission
- [ ] Verify all project links work

## SSL/HTTPS

- **GitHub Pages**: Automatic ✅
- **Netlify**: Automatic ✅
- **Vercel**: Automatic ✅

## Post-Deploy Checklist

- [ ] Portfolio loads correctly
- [ ] Mobile responsive works
- [ ] Contact form opens email client
- [ ] Project links work
- [ ] Social links correct
- [ ] No broken images or styling
- [ ] Animations load smoothly

## Update Your Portfolio

After deployment, to update:

```bash
# Make changes to your files
# Then:
git add .
git commit -m "Update portfolio content"
git push origin main
```

Changes will auto-deploy on Netlify/Vercel or update GitHub Pages within minutes.

## Troubleshooting

**Portfolio not showing?**

- Wait 5-10 minutes for deployment
- Clear browser cache (Ctrl+Shift+Delete)
- Check if DNS is propagated (for custom domains)

**Styles not loading?**

- Check if CSS file path is correct
- Clear cache and hard refresh (Ctrl+Shift+R)

**Images not showing?**

- Verify image paths are relative (not absolute)
- Check if images are in correct folder

**Contact form not working?**

- Check email address is correct
- Test on different browser

## Support

Refer to official docs:

- [GitHub Pages](https://docs.github.com/en/pages)
- [Netlify](https://docs.netlify.com)
- [Vercel](https://vercel.com/docs)
