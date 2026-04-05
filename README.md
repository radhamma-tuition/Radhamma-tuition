# 🪔 RADHAMMA Tuition — Production Deploy Guide

## ⚡ Fastest Way to Get a Domain Link (3 options)

---

## 🥇 Option 1: Firebase Hosting (RECOMMENDED — Free + Fast CDN)

Your project is already set up! Just run these commands:

```bash
# 1. Install Firebase CLI (one time only)
npm install -g firebase-tools

# 2. Login to Firebase
firebase login

# 3. Go into this folder
cd radhamma-prod

# 4. Deploy in ONE command
firebase deploy

# ✅ You'll get a link like: https://radhamma-tuition-3bed3.web.app
```

**Your app will be live at:**
- `https://radhamma-tuition-3bed3.web.app`
- `https://radhamma-tuition-3bed3.firebaseapp.com`

> Free tier includes 10GB bandwidth/month, global CDN, SSL certificate — more than enough.

---

## 🥈 Option 2: Netlify (Drag & Drop — No commands needed!)

1. Go to **https://netlify.com** → sign up free
2. Drag the **`public/`** folder onto the Netlify dashboard
3. ✅ You instantly get a link like `https://radhamma-tuition.netlify.app`
4. Optional: Go to **Site Settings → Domain** to set a custom name

---

## 🥉 Option 3: GitHub Pages (Free via GitHub)

```bash
# 1. Create a GitHub repo named: radhamma-tuition
# 2. Push the public/ folder contents to the repo root

git init
git add public/
git commit -m "deploy"
git remote add origin https://github.com/YOUR_USERNAME/radhamma-tuition.git
git push -u origin main

# 3. Go to GitHub → Settings → Pages → Source: main branch
# ✅ Link: https://YOUR_USERNAME.github.io/radhamma-tuition
```

---

## 🌐 Custom Domain (Optional)

To use your own domain like `www.radhammaturition.in`:

**Firebase:**
```bash
firebase hosting:channel:deploy live
# Then: Firebase Console → Hosting → Add custom domain → follow steps
```

**Netlify:** Site Settings → Domain Management → Add custom domain

---

## 🔑 Login Credentials

| Role | Username | Password |
|------|----------|----------|
| 👩‍🏫 Teacher | `admin` | `admin123` |
| 👨‍🎓 Student 1 | `student1` | `pass123` |
| 👨‍🎓 Student 2 | `student2` | `pass123` |

---

## 🚀 What's Optimized in This Version

- ✅ **Instant splash screen** — visible in <100ms, no blank white page
- ✅ **Preconnect headers** — fonts and Firebase load faster
- ✅ **Offline persistence** — app works even without internet on repeat visits
- ✅ **Firebase auth-compat removed** — smaller bundle, faster load
- ✅ **chart.js deferred** — doesn't block initial page render
- ✅ **Cache-Control headers** — browser caches static assets aggressively
- ✅ **PWA meta tags** — can be added to phone home screen

---

## 📁 File Structure

```
radhamma-prod/
├── public/
│   ├── index.html       ← The entire app (deploy this folder)
│   └── netlify.toml     ← Netlify config
├── firebase.json        ← Firebase Hosting config + cache headers
├── firestore.rules      ← Database security rules
├── .firebaserc          ← Firebase project link
└── README.md
```
