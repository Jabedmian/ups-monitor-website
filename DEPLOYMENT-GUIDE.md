# 🌐 UPS Monitor Pro - Website Deployment Guide

## 📦 What's Included:

1. **index.html** - Main marketing/download website
2. **mobile.html** - Mobile monitoring dashboard
3. **This README** - Deployment instructions

---

## 🚀 How to Deploy Your Website:

### **Option 1: Free Hosting (GitHub Pages)**

**Perfect for: Getting started quickly, free hosting**

1. **Create GitHub account** (if you don't have one)
   - Go to: https://github.com
   - Sign up for free

2. **Create new repository**
   - Click "New" repository
   - Name it: `ups-monitor-website`
   - Make it Public
   - Don't add README

3. **Upload files**
   - Click "uploading an existing file"
   - Drag and drop:
     - `index.html`
     - `mobile.html`
   - Commit changes

4. **Enable GitHub Pages**
   - Go to Settings
   - Click "Pages" (left sidebar)
   - Source: Deploy from a branch
   - Branch: `main` / `root`
   - Click Save

5. **Your website is live!**
   - URL: `https://YOUR-USERNAME.github.io/ups-monitor-website/`
   - Wait 2-3 minutes for deployment

---

### **Option 2: Netlify (Easy Drag & Drop)**

**Perfect for: Professional deployment, custom domain**

1. **Go to Netlify**
   - Visit: https://www.netlify.com
   - Sign up (free)

2. **Deploy**
   - Click "Add new site" → "Deploy manually"
   - Drag the entire `website` folder
   - Wait 30 seconds

3. **Your site is live!**
   - URL: `https://random-name-12345.netlify.app`
   - Can add custom domain in settings

---

### **Option 3: Your Own Web Server**

**Perfect for: Full control, your own hosting**

1. **Upload to your web host**
   ```bash
   # Via FTP or cPanel File Manager
   Upload: index.html, mobile.html
   To: public_html/ or www/
   ```

2. **Access**
   ```
   Main site: https://yourdomain.com/
   Mobile: https://yourdomain.com/mobile.html
   ```

---

## 📱 Mobile Monitoring Setup:

### **For Customers:**

1. **Access mobile dashboard**
   ```
   https://your-website.com/mobile.html
   ```

2. **Configure server**
   - Enter their server IP: `http://192.168.1.100:3000`
   - Click Connect
   - Dashboard shows live data!

3. **Add to Home Screen** (iPhone/Android)
   - **iPhone:** Safari → Share → Add to Home Screen
   - **Android:** Chrome → Menu → Add to Home Screen
   - Now it works like an app!

---

## 🔗 Download Links Setup:

### **Create Download Links:**

You need to host your installation files somewhere. Options:

#### **Option A: GitHub Releases (Recommended)**

1. Go to your GitHub repo
2. Click "Releases" → "Create new release"
3. Upload: `ups-professional-pbx.zip`
4. Publish release
5. Copy download URL

6. Edit `index.html`, find:
   ```html
   <a href="downloads/ups-monitor-windows.zip"
   ```

7. Replace with your GitHub URL:
   ```html
   <a href="https://github.com/USERNAME/REPO/releases/download/v1.0.0/ups-professional-pbx.zip"
   ```

#### **Option B: Google Drive**

1. Upload ZIP to Google Drive
2. Right-click → Share → Anyone with link
3. Copy link
4. Edit `index.html` and paste link

#### **Option C: Dropbox**

1. Upload to Dropbox
2. Get shareable link
3. Change `?dl=0` to `?dl=1`
4. Update `index.html`

---

## 🎨 Customize Your Website:

### **Change Company Name:**

Edit `index.html`:
```html
<!-- Line 106 -->
<h1>⚡ YOUR COMPANY NAME</h1>

<!-- Line 663 -->
<h3 style="margin-bottom: 20px;">YOUR COMPANY NAME</h3>
```

### **Change Contact Email:**

```html
<!-- Line 671 -->
<a href="mailto:YOUR-EMAIL@company.com">
```

### **Change Phone Number:**

```html
<!-- Line 672 -->
<a href="tel:+1234567890">📞 YOUR-PHONE</a>
```

### **Change Pricing:**

```html
<!-- Lines 490-590 -->
<div class="price">$YOUR-PRICE<span class="price-period">/month</span></div>
```

### **Add Your Logo:**

1. Save logo as `logo.png`
2. Upload to website folder
3. Add to `index.html`:
   ```html
   <img src="logo.png" alt="Logo" style="max-width: 200px;">
   ```

---

## 🔧 Add Custom Domain:

### **For Netlify:**

1. Buy domain (Namecheap, GoDaddy, etc.)
2. In Netlify: Settings → Domain Management
3. Add custom domain
4. Update DNS records (Netlify shows you how)
5. Wait 24 hours

### **For GitHub Pages:**

1. Buy domain
2. In repo: Settings → Pages → Custom domain
3. Enter: `www.yourdomain.com`
4. Update DNS:
   - Type: CNAME
   - Name: www
   - Value: your-username.github.io

---

## 📊 Add Analytics:

### **Google Analytics:**

1. Sign up: https://analytics.google.com
2. Get tracking code
3. Add before `</head>` in `index.html`:
   ```html
   <!-- Google Analytics -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'GA_MEASUREMENT_ID');
   </script>
   ```

---

## 🎯 SEO Optimization:

Add to `<head>` in `index.html`:

```html
<!-- SEO Meta Tags -->
<meta name="description" content="Professional UPS monitoring with email and phone call alerts. Monitor your UPS devices from anywhere.">
<meta name="keywords" content="UPS monitor, power monitoring, battery backup, email alerts, phone alerts">
<meta name="author" content="Your Company Name">

<!-- Open Graph (Facebook/LinkedIn) -->
<meta property="og:title" content="UPS Monitor Pro - Professional UPS Monitoring">
<meta property="og:description" content="Monitor your UPS devices with email and phone call alerts">
<meta property="og:image" content="https://your-site.com/preview-image.png">
<meta property="og:url" content="https://your-site.com">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="UPS Monitor Pro">
<meta name="twitter:description" content="Professional UPS monitoring solution">
```

---

## 📧 Contact Form (Optional):

Add to your website:

```html
<form action="https://formspree.io/f/YOUR-FORM-ID" method="POST">
  <input type="email" name="email" placeholder="Your email" required>
  <textarea name="message" placeholder="Your message" required></textarea>
  <button type="submit">Send</button>
</form>
```

Sign up at: https://formspree.io (free)

---

## 🔒 HTTPS / SSL:

**GitHub Pages:** Automatic HTTPS ✅
**Netlify:** Automatic HTTPS ✅
**Your Server:** Use Let's Encrypt (free)

---

## 📱 Progressive Web App (Optional):

Make mobile site installable like native app:

1. Create `manifest.json`:
```json
{
  "name": "UPS Monitor",
  "short_name": "UPS Monitor",
  "start_url": "/mobile.html",
  "display": "standalone",
  "background_color": "#667eea",
  "theme_color": "#667eea",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    }
  ]
}
```

2. Add to `mobile.html` head:
```html
<link rel="manifest" href="manifest.json">
<meta name="theme-color" content="#667eea">
```

---

## 🎯 Marketing Your Website:

1. **Social Media**
   - Share on LinkedIn
   - Post on Facebook
   - Tweet about it

2. **SEO**
   - Submit to Google Search Console
   - Add sitemap
   - Get backlinks

3. **Paid Ads** (optional)
   - Google Ads
   - Facebook Ads
   - LinkedIn Ads

4. **Content Marketing**
   - Write blog posts
   - Create YouTube videos
   - Answer questions on forums

---

## 🆘 Troubleshooting:

### **Downloads not working:**
- Check file URLs
- Make sure files are publicly accessible
- Test in incognito/private mode

### **Mobile app can't connect:**
- Check server is accessible from internet
- Firewall may be blocking port 3000
- Use correct IP address

### **Website not loading:**
- Clear browser cache
- Check DNS settings
- Wait for propagation (24-48 hours)

---

## 📞 Support:

**Need help?**
- GitHub Issues: Open issue in your repo
- Email: your-support@email.com
- Phone: +1 (234) 567-890

---

## ✅ Launch Checklist:

- [ ] Website deployed and accessible
- [ ] Download links working
- [ ] Contact info updated
- [ ] Pricing configured
- [ ] Mobile app tested
- [ ] Custom domain connected (optional)
- [ ] Analytics installed
- [ ] SSL/HTTPS working
- [ ] Social media shared
- [ ] First customer signed up! 🎉

---

**Your website is ready to make money!** 💰

Customers can now:
1. Visit your website
2. Download software
3. Install on their PC
4. Monitor from mobile
5. Pay you monthly! 💵
