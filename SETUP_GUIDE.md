# 🛠️ OptiCare Setup Guide
## How to set up your free system in 15 minutes

---

## What you need before starting
- A Gmail account (free) — you probably already have one
- A phone or computer with Chrome browser
- 15 minutes of your time

---

## PART 1 — Create Your Free Firebase Database (10 min)

### Step 1 — Open Firebase
1. Go to: **https://console.firebase.google.com**
2. Sign in with your Gmail account

---

### Step 2 — Create a New Project
1. Click the big **"+ Add project"** button
2. **Project name:** Type `opticare-yourshopname` (example: `opticare-ravieye`)
3. Click **Continue**
4. On the next screen — **turn OFF Google Analytics** (you don't need it)
5. Click **Create project**
6. Wait 30 seconds... then click **Continue**

---

### Step 3 — Set Up the Database
1. On the left side menu, click **"Firestore Database"**
2. Click **"Create database"**
3. Choose **"Start in test mode"** ← IMPORTANT: choose this one
4. Click **Next**
5. Choose any location (example: `asia-south1` for India)
6. Click **Enable**
7. Wait 1 minute for it to set up

---

### Step 4 — Get Your Secret Keys
1. Click the **gear icon ⚙️** at the top left (next to "Project Overview")
2. Click **"Project settings"**
3. Scroll down to **"Your apps"** section
4. Click the **Web icon** `</>`
5. **App nickname:** Type `opticare-web`
6. **DO NOT tick** the Firebase Hosting checkbox
7. Click **"Register app"**
8. You will see a box with code like this:

```
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "opticare-yourshop.firebaseapp.com",
  projectId: "opticare-yourshop",
  storageBucket: "opticare-yourshop.appspot.com",
  appId: "1:123456789:web:abcdef123456"
};
```

**COPY THESE 3 VALUES — you will need them:**
- `apiKey` → the long text starting with "AIza..."
- `projectId` → your project name
- `appId` → the long text starting with "1:..."

9. Click **Continue to console**

---

### Step 5 — Set Database Rules (IMPORTANT for security)
1. In Firestore, click **"Rules"** tab at the top
2. Delete everything there
3. Paste this instead:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

4. Click **"Publish"**

> ⚠️ NOTE: This rule allows anyone with your keys to access data.
> For extra security after launch, ask your developer to set up
> Firebase Authentication. For now this is fine for a small shop.

---

## PART 2 — Set Up the App on GitHub (Free Hosting) (5 min)

### Step 1 — Create a GitHub Account
1. Go to: **https://github.com**
2. Click **"Sign up"**
3. Create a free account

---

### Step 2 — Create a Repository (your app's folder)
1. After signing in, click the **"+"** icon at top right
2. Click **"New repository"**
3. **Repository name:** `opticare`
4. Make it **Public**
5. Tick **"Add a README file"**
6. Click **"Create repository"**

---

### Step 3 — Upload the Files
1. In your new repository, click **"Add file"** → **"Upload files"**
2. Upload these 2 files:
   - `index.html`
   - `manifest.json`
3. Click **"Commit changes"**

---

### Step 4 — Enable Free Hosting (GitHub Pages)
1. Click **"Settings"** tab in your repository
2. On the left menu, click **"Pages"**
3. Under **"Branch"**, select **"main"**
4. Click **"Save"**
5. Wait 2 minutes
6. GitHub will show you a link like:
   **`https://yourusername.github.io/opticare`**

🎉 **That's your app link! Share it with both branch owners.**

---

## PART 3 — First Time Opening the App

1. Open the app link in **Chrome** on your phone
2. You will see the setup screen
3. Enter:
   - **Firebase API Key** → from Step 4 above (AIza...)
   - **Project ID** → your project name
   - **App ID** → the 1:123... value
4. Enter your shop details (name, branches, phone, address)
5. Click **"Open OptiCare"**

---

## Adding to Phone Home Screen (makes it feel like an app)

### On Android (Chrome):
1. Open the app link in Chrome
2. Tap the **3 dots menu** (top right)
3. Tap **"Add to Home screen"**
4. Tap **"Add"**

Now it appears on your home screen like a real app! ✅

---

## Daily Usage — Super Simple

### Making a Bill:
1. Open OptiCare
2. Tap **"New Bill"**
3. Fill in customer name + phone
4. Add items and prices
5. Tap **"Save & Generate Bill"**
6. Tap **"WhatsApp"** to send bill to customer ✅

### Checking Stock:
1. Tap **"Stock"** tab
2. Red items = need to reorder

### Follow-up Reminders:
1. Tap **"Follow-Up"** tab
2. Tap **"Remind"** next to a customer to send WhatsApp message

---

## If Something Goes Wrong

| Problem | Solution |
|---------|----------|
| App not loading | Check internet connection |
| Data not saving | Check Firebase keys in setup |
| Can't see customers | Make sure you're on the right branch |
| Forgot Firebase keys | Go to Firebase Console → Project Settings → Your Apps |

---

## Cost Breakdown — Forever Free ✅

| Service | Free Limit | Your Usage |
|---------|-----------|------------|
| Firebase Firestore | 50,000 reads/day | ~200/day ✅ |
| Firebase Firestore | 20,000 writes/day | ~50/day ✅ |
| GitHub Pages hosting | Unlimited | ✅ |
| **Total monthly cost** | **₹0** | **₹0** |

---

## Need Help?

If you get stuck on any step, take a screenshot and send it to your developer.

The most common mistake is copy-pasting the wrong Firebase key — make sure you copy the full value including all characters.

---

*OptiCare v1.0 — Built for small optical shops 👁️*
