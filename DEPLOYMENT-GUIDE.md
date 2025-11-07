# 🚀 Portfolio Deployment Guide

## 📧 Email Integration Options

### Option 1: PHP Mail (Basic - Requires PHP Hosting)
- **Current Setup**: `contact.php` file included
- **Requirements**: Web hosting with PHP support
- **Email Delivery**: Uses server's mail function
- **Hosting Options**: 
  - 000webhost (Free)
  - InfinityFree (Free)
  - Hostinger
  - GoDaddy

### Option 2: EmailJS (Recommended - No Backend Required)
**Setup Steps:**
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Create free account
3. Add email service (Gmail recommended)
4. Create email template
5. Get Service ID, Template ID, and Public Key
6. Replace JavaScript code with EmailJS integration

**EmailJS Integration Code:**
```javascript
// Add to HTML head
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>

// Replace contact form handler in script.js
emailjs.init('YOUR_PUBLIC_KEY');

contactForm.addEventListener('submit', async (e) => {
    e.preventDefault();
    
    const templateParams = {
        from_name: document.getElementById('name').value,
        from_email: document.getElementById('email').value,
        subject: document.getElementById('subject').value,
        message: document.getElementById('message').value,
        to_email: 'yashodeepchaudhary05@gmail.com'
    };

    try {
        await emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams);
        showNotification('Message sent successfully!', 'success');
        contactForm.reset();
    } catch (error) {
        showNotification('Failed to send message.', 'error');
    }
});
```

### Option 3: Netlify Forms (Easy Deployment)
**Setup Steps:**
1. Add `netlify` attribute to form
2. Add hidden input for form name
3. Deploy to Netlify

**Form Update:**
```html
<form class="contact-form" id="contact-form" netlify>
    <input type="hidden" name="form-name" value="contact" />
    <!-- existing form fields -->
</form>
```

### Option 4: Formspree (Simple Integration)
**Setup Steps:**
1. Go to [Formspree.io](https://formspree.io/)
2. Create account and get form endpoint
3. Update form action

**Form Update:**
```html
<form class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
    <!-- existing form fields -->
</form>
```

## 🌐 Deployment Platforms

### 1. GitHub Pages (Free - Static Only)
**Steps:**
1. Create GitHub repository
2. Upload portfolio files
3. Enable GitHub Pages in settings
4. **Note**: No PHP support, use EmailJS or Netlify Forms

### 2. Netlify (Free - Recommended)
**Steps:**
1. Create [Netlify](https://netlify.com) account
2. Drag & drop portfolio folder
3. Automatic deployment
4. **Features**: Form handling, custom domain, SSL

### 3. Vercel (Free)
**Steps:**
1. Create [Vercel](https://vercel.com) account
2. Import from GitHub or upload files
3. Automatic deployment
4. **Note**: Use EmailJS for contact form

### 4. Traditional Web Hosting (PHP Support)
**Recommended Hosts:**
- **Free**: 000webhost, InfinityFree
- **Paid**: Hostinger, Bluehost, GoDaddy

**Steps:**
1. Purchase hosting plan
2. Upload files via FTP/File Manager
3. Configure email settings
4. Test contact form

## 📱 Pre-Deployment Checklist

### ✅ Image Setup
- [x] Your photo added as `yashodeep-photo.jpg`
- [x] CSS updated for proper image display
- [ ] Optimize image size (recommended: < 500KB)

### ✅ Contact Form
- [x] PHP handler created (`contact.php`)
- [x] JavaScript updated for form submission
- [ ] Choose email service (EmailJS recommended for static hosting)
- [ ] Test form functionality

### ✅ Content Review
- [x] Personal information updated
- [x] Projects information accurate
- [x] Contact details correct
- [x] Social media links working

### ✅ Performance
- [ ] Compress images
- [ ] Minify CSS/JS (optional)
- [ ] Test on mobile devices
- [ ] Check loading speed

## 🔧 Quick Setup for EmailJS (Recommended)

1. **Sign up at EmailJS.com**
2. **Add Gmail service** with your email
3. **Create template** with these variables:
   - `{{from_name}}`
   - `{{from_email}}`
   - `{{subject}}`
   - `{{message}}`
4. **Get credentials** (Service ID, Template ID, Public Key)
5. **Update HTML** - Add EmailJS script
6. **Update JavaScript** - Replace contact form handler
7. **Deploy** to any static hosting platform

## 📧 Email Template Example
```
New Contact Form Submission

From: {{from_name}} ({{from_email}})
Subject: {{subject}}

Message:
{{message}}

---
Sent from your portfolio website
```

## 🚀 Deployment Commands

### For GitHub Pages:
```bash
git init
git add .
git commit -m "Initial portfolio commit"
git branch -M main
git remote add origin https://github.com/yourusername/portfolio.git
git push -u origin main
```

### For Netlify CLI:
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=.
```

## 📞 Support
- **EmailJS Issues**: Check EmailJS documentation
- **Hosting Problems**: Contact your hosting provider
- **Form Not Working**: Verify email service configuration
- **Image Not Loading**: Check file path and permissions

---
**Your portfolio is ready for deployment! Choose your preferred email service and hosting platform.** 🎉
