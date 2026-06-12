# 🌸 Nami Sushi — Deployment Guide

## Step 1 — Set up EmailJS (so you get order emails)

1. Go to https://www.emailjs.com and sign up free
2. Click **Add New Service** → choose Gmail → connect your Gmail account → note the **Service ID**
3. Click **Email Templates** → **Create New Template**
   - Set the template body to something like:
     ```
     New order from: {{customer_name}}
     
     Items:
     {{order_items}}
     
     Total: {{order_total}}
     
     Note: {{customer_note}}
     ```
   - Save and note the **Template ID**
4. Go to **Account** → **General** → copy your **Public Key**
5. Open `src/App.jsx` and replace the 3 values at the very top:
   ```js
   const EMAILJS_SERVICE_ID  = "YOUR_SERVICE_ID";   // ← paste here
   const EMAILJS_TEMPLATE_ID = "YOUR_TEMPLATE_ID";  // ← paste here
   const EMAILJS_PUBLIC_KEY  = "YOUR_PUBLIC_KEY";   // ← paste here
   ```

---

## Step 2 — Deploy to Vercel (free, takes 2 minutes)

1. Go to https://github.com and create a free account if you don't have one
2. Click **+** → **New repository** → name it `nami-sushi` → click **Create**
3. Upload all the files in this folder to that repository
4. Go to https://vercel.com → sign up with your GitHub account
5. Click **Add New Project** → select your `nami-sushi` repo
6. Leave all settings as default → click **Deploy**
7. In ~1 minute you'll get a live link like: `nami-sushi.vercel.app` 🎉

---

## Step 3 — Share with customers

Send your link via:
- 📸 Instagram bio
- 💬 WhatsApp
- 📍 Google Maps listing
- 🖨️ Print it as a QR code at https://qr.io (free)

---

## Optional — Get a custom domain (~$10/year)

1. Go to https://www.namecheap.com
2. Search for `namisushi.com` or similar
3. Buy it (~$10/year)
4. In Vercel → your project → **Settings** → **Domains** → add your domain
5. Follow the instructions to connect it

---

## File structure

```
nami-sushi/
├── index.html          ← page shell
├── package.json        ← project config
├── vite.config.js      ← build config
└── src/
    ├── main.jsx        ← React entry point
    └── App.jsx         ← your full sushi app ✨
```
