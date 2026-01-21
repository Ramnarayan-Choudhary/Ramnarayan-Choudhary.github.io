# 🚀 Deployment Guide

This guide will help you deploy your portfolio website to various hosting platforms.

## 📋 Pre-Deployment Checklist

Before deploying, make sure you have:

- [ ] Added your profile photo to `assets/profile.jpg`
- [ ] Added project images to the `assets/` folder
- [ ] Updated all personal information in `index.html`
- [ ] Added your resume as `assets/resume.pdf`
- [ ] Updated social media links
- [ ] Tested the website locally
- [ ] Optimized images for web

## 🌐 GitHub Pages (Recommended)

GitHub Pages is free and perfect for static websites like portfolios.

### Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click "New" to create a new repository
3. Name it `portfolio` or `your-username.github.io`
4. Make it public
5. Initialize with README (optional)

### Step 2: Upload Your Files

**Option A: Using Git (Recommended)**
```bash
# Clone your repository
git clone https://github.com/yourusername/portfolio.git
cd portfolio

# Copy your portfolio files to this directory
# Then add, commit, and push
git add .
git commit -m "Initial portfolio commit"
git push origin main
```

**Option B: Using GitHub Web Interface**
1. Click "uploading an existing file"
2. Drag and drop all your portfolio files
3. Commit the changes

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" section
4. Under "Source", select "Deploy from a branch"
5. Choose "main" branch and "/ (root)" folder
6. Click "Save"

### Step 4: Access Your Website

Your website will be available at:
- `https://yourusername.github.io/portfolio` (if repo is named "portfolio")
- `https://yourusername.github.io` (if repo is named "yourusername.github.io")

## 🎯 Netlify

Netlify offers great features like form handling and custom domains.

### Deploy from GitHub

1. Go to [Netlify](https://netlify.com)
2. Sign up/Login with GitHub
3. Click "New site from Git"
4. Choose your repository
5. Deploy settings:
   - Branch: `main`
   - Build command: (leave empty)
   - Publish directory: (leave empty)
6. Click "Deploy site"

### Drag and Drop Deploy

1. Zip your project folder
2. Go to [Netlify](https://netlify.com)
3. Drag and drop your zip file
4. Your site is live!

## ⚡ Vercel

Perfect for modern web projects with zero configuration.

### Deploy from GitHub

1. Go to [Vercel](https://vercel.com)
2. Sign up with GitHub
3. Click "New Project"
4. Select your repository
5. Click "Deploy"

### Deploy from CLI

```bash
# Install Vercel CLI
npm i -g vercel

# In your project directory
vercel

# Follow the prompts
```

## 🔧 Other Hosting Options

### Firebase Hosting

```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize Firebase in your project
firebase init hosting

# Deploy
firebase deploy
```

### Surge.sh

```bash
# Install Surge
npm install -g surge

# In your project directory
surge

# Follow the prompts
```

## 🎨 Custom Domain Setup

### For GitHub Pages

1. Buy a domain from any registrar
2. Add a `CNAME` file to your repository with your domain name
3. In your DNS settings, add a CNAME record pointing to `yourusername.github.io`

### For Netlify

1. Go to Site settings > Domain management
2. Add custom domain
3. Follow DNS setup instructions

### For Vercel

1. Go to Project settings > Domains
2. Add your domain
3. Configure DNS as instructed

## 🔒 SSL Certificate

All mentioned platforms provide free SSL certificates automatically!

## 📊 Analytics Setup

### Google Analytics

1. Go to [Google Analytics](https://analytics.google.com)
2. Create a property
3. Get your tracking code
4. Add it to your `index.html` before closing `</head>` tag:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_TRACKING_ID');
</script>
```

## 🚀 Performance Optimization

### Before Deployment

1. **Optimize Images:**
   - Use [TinyPNG](https://tinypng.com) or [ImageOptim](https://imageoptim.com)
   - Resize images to appropriate dimensions
   - Use WebP format when possible

2. **Minify CSS/JS:**
   - Use online minifiers or build tools
   - Remove unused CSS

3. **Enable Compression:**
   - Most hosting platforms enable gzip automatically

### After Deployment

1. **Test Performance:**
   - Use [Google PageSpeed Insights](https://pagespeed.web.dev)
   - Use [GTmetrix](https://gtmetrix.com)

2. **Test Responsiveness:**
   - Use browser dev tools
   - Test on actual devices

## 🔍 SEO Optimization

### Meta Tags

Ensure your `index.html` has:

```html
<meta name="description" content="Ramnarayan Choudhary - IIT Bombay Student passionate about Machine Learning, Cybersecurity, and Innovation">
<meta name="keywords" content="Ramnarayan Choudhary, IIT Bombay, Machine Learning, Cybersecurity, Portfolio">
<meta name="author" content="Ramnarayan Choudhary">

<!-- Open Graph -->
<meta property="og:title" content="Ramnarayan Choudhary - Portfolio">
<meta property="og:description" content="IIT Bombay Student passionate about Machine Learning and Cybersecurity">
<meta property="og:image" content="https://yoursite.com/assets/profile.jpg">
<meta property="og:url" content="https://yoursite.com">

<!-- Twitter Cards -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Ramnarayan Choudhary - Portfolio">
<meta name="twitter:description" content="IIT Bombay Student passionate about Machine Learning and Cybersecurity">
<meta name="twitter:image" content="https://yoursite.com/assets/profile.jpg">
```

## 📱 Testing

Before going live, test your website:

### Browser Testing
- Chrome, Firefox, Safari, Edge
- Mobile browsers

### Device Testing
- Desktop (1920x1080, 1366x768)
- Tablet (768px width)
- Mobile (375px, 320px width)

### Functionality Testing
- Navigation links
- Contact form
- Responsive design
- Loading speed
- Social media links

## 🔄 Continuous Deployment

### GitHub Actions (Advanced)

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./
```

## 🎯 Monitoring

### Uptime Monitoring
- [UptimeRobot](https://uptimerobot.com)
- [Pingdom](https://pingdom.com)

### Error Tracking
- [Sentry](https://sentry.io)
- Browser console for client-side errors

## 💡 Tips for Success

1. **Keep it Simple:** Don't over-complicate the deployment process
2. **Test Locally:** Always test your changes locally first
3. **Backup:** Keep backups of your code
4. **Monitor:** Set up basic monitoring and analytics
5. **Update Regularly:** Keep your portfolio updated with new projects
6. **Mobile First:** Ensure mobile experience is perfect
7. **Fast Loading:** Optimize for speed

## 🆘 Troubleshooting

### Common Issues

**Website not loading:**
- Check if files are in the root directory
- Ensure `index.html` is present
- Check console for errors

**Images not showing:**
- Verify image paths are correct
- Check if images are in the `assets/` folder
- Ensure images are web-optimized

**Mobile layout broken:**
- Test responsive design
- Check CSS media queries
- Validate HTML/CSS

**Contact form not working:**
- Form requires backend for actual email sending
- Consider using Netlify Forms or FormSubmit

## 📞 Support

If you need help:
1. Check the repository's Issues section
2. Read hosting platform documentation
3. Search Stack Overflow
4. Contact the repository maintainer

---

🎉 **Congratulations! Your portfolio is now live and ready to impress!** 