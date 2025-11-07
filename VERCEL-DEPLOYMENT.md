# 🚀 Vercel Deployment Guide for Yashodeep's Portfolio

## 📧 Step 1: Setup EmailJS (Required for Contact Form)

### 1.1 Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Sign up with your Gmail account
3. Verify your email address

### 1.2 Add Email Service
1. Go to **Email Services** in dashboard
2. Click **Add New Service**
3. Select **Gmail**
4. Connect your Gmail account (`yashodeepchaudhary05@gmail.com`)
5. Note down the **Service ID** (e.g., `service_abc123`)

### 1.3 Create Email Template
1. Go to **Email Templates**
2. Click **Create New Template**
3. Use this template:

```
Subject: New Portfolio Contact: {{subject}}

From: {{from_name}} ({{from_email}})
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio website.
Reply directly to this email to respond to {{from_name}}.
```

4. Note down the **Template ID** (e.g., `template_xyz789`)

### 1.4 Get Public Key
1. Go to **Account** → **General**
2. Find your **Public Key** (e.g., `user_def456`)

## 🔧 Step 2: Update Portfolio Code

### 2.1 Update JavaScript
Replace these placeholders in `script.js`:
- `YOUR_PUBLIC_KEY` → Your actual public key
- `YOUR_SERVICE_ID` → Your actual service ID  
- `YOUR_TEMPLATE_ID` → Your actual template ID

**Example:**
```javascript
// Replace line 101 in script.js
emailjs.init('user_def456'); // Your actual public key

// Replace line 125 in script.js
await emailjs.send('service_abc123', 'template_xyz789', templateParams);
```

## 🌐 Step 3: Deploy to Vercel

### Option A: Using Vercel Website (Easiest)
1. Go to [vercel.com](https://vercel.com)
2. Sign up/login with GitHub account
3. Click **Add New** → **Project**
4. **Import Git Repository** or **Browse** to upload folder
5. If uploading folder:
   - Zip your portfolio folder
   - Drag & drop the zip file
   - Vercel will automatically extract and deploy

### Option B: Using GitHub + Vercel
1. **Create GitHub Repository:**
   ```bash
   # In your portfolio folder
   git init
   git add .
   git commit -m "Initial portfolio commit"
   git branch -M main
   git remote add origin https://github.com/yashodeepchaudhari/portfolio.git
   git push -u origin main
   ```

2. **Connect to Vercel:**
   - Go to Vercel dashboard
   - Click **Add New** → **Project**
   - Import from GitHub
   - Select your portfolio repository
   - Click **Deploy**

### Option C: Using Vercel CLI
1. **Install Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

2. **Deploy:**
   ```bash
   # In your portfolio folder
   vercel
   # Follow the prompts
   ```

## ✅ Step 4: Test Your Deployment

1. **Visit your live site** (Vercel will provide the URL)
2. **Test the contact form:**
   - Fill out all fields
   - Submit the form
   - Check your Gmail for the message
3. **Test on mobile devices**
4. **Check all links and animations**

## 🎯 Step 5: Custom Domain (Optional)

1. **Purchase a domain** (e.g., `yashodeepchaudhary.com`)
2. **In Vercel dashboard:**
   - Go to your project
   - Click **Domains**
   - Add your custom domain
   - Follow DNS configuration instructions

## 📱 Files to Include in Deployment

Make sure these files are in your portfolio folder:
- ✅ `index.html`
- ✅ `styles.css`
- ✅ `script.js` (updated with EmailJS credentials)
- ✅ `yashodeep-photo.jpg`
- ✅ `README.md`
- ❌ `contact.php` (not needed for Vercel)

## 🔍 Troubleshooting

### Contact Form Not Working
- **Check EmailJS credentials** in `script.js`
- **Verify email service** is connected in EmailJS dashboard
- **Check browser console** for error messages
- **Test EmailJS template** in their dashboard

### Images Not Loading
- **Check file names** match exactly (case-sensitive)
- **Verify image paths** in HTML and CSS
- **Ensure images are in root folder**

### Site Not Loading
- **Check Vercel deployment logs**
- **Verify all files are uploaded**
- **Check for JavaScript errors** in browser console

## 📞 Support Resources

- **Vercel Documentation**: [vercel.com/docs](https://vercel.com/docs)
- **EmailJS Documentation**: [emailjs.com/docs](https://www.emailjs.com/docs/)
- **Vercel Community**: [github.com/vercel/vercel/discussions](https://github.com/vercel/vercel/discussions)

## 🎉 Final Checklist

- [ ] EmailJS account created and configured
- [ ] Gmail service connected to EmailJS
- [ ] Email template created with proper variables
- [ ] JavaScript updated with actual EmailJS credentials
- [ ] Portfolio deployed to Vercel
- [ ] Contact form tested and working
- [ ] All sections display correctly
- [ ] Mobile responsiveness verified
- [ ] Custom domain configured (optional)

---

**Your portfolio will be live at: `https://your-project-name.vercel.app`**

**Estimated setup time: 15-20 minutes** ⏱️

**Once deployed, anyone can contact you through the form and messages will be sent directly to `yashodeepchaudhary05@gmail.com`!** 📧
