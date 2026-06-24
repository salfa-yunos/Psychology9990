# 🚀 Deploy Guide — Psychology 9990 Mock Exam

## What you need before starting
1. A free **Netlify** account → netlify.com
2. A free **GitHub** account → github.com
3. An **Anthropic API key** → console.anthropic.com
   - Sign up → Create a new Project → API Keys → Create Key
   - Copy the key (starts with `sk-ant-...`)
   - Top up $5 credit to start (each student exam costs ~$0.02)

---

## Step 1 — Upload to GitHub

1. Go to **github.com** → click the **+** → **New repository**
2. Name it `psych9990-mock` → make it **Private** → click **Create repository**
3. On the next screen, click **uploading an existing file**
4. Drag the entire `psych9990-mock` **folder contents** into the upload area
   - Make sure you upload all files INCLUDING the `netlify/` and `src/` folders
5. Click **Commit changes**

---

## Step 2 — Deploy on Netlify

1. Go to **netlify.com** → **Log in** → click **Add new site**
2. Choose **Import an existing project**
3. Click **GitHub** → authorise Netlify → select your `psych9990-mock` repo
4. Netlify will auto-detect the settings from `netlify.toml`:
   - Build command: `npm run build`
   - Publish directory: `dist`
5. Click **Deploy site**
6. Wait ~60 seconds for the build to finish ✅

---

## Step 3 — Add your API key (critical!)

Without this step, the AI marking won't work.

1. In Netlify, go to your site → **Site configuration** → **Environment variables**
2. Click **Add a variable**
3. Key: `ANTHROPIC_API_KEY`
4. Value: paste your key (`sk-ant-api03-...`)
5. Click **Save**
6. Go to **Deploys** → click **Trigger deploy** → **Deploy site**
   (The site needs to redeploy after adding the variable)

---

## Step 4 — Customise the access code

Open `src/App.jsx` in GitHub and change line 8:

```js
const ACCESS_CODE = "psych2026";  // ← change this to anything you like
```

Commit the change → Netlify will auto-redeploy in ~30 seconds.

---

## Step 5 — Share with students

Your app URL will be something like `happy-einstein-abc123.netlify.app`

You can give it a custom name:
- Netlify → **Site configuration** → **Site details** → **Change site name**
- e.g. `srlk10-psych-mock.netlify.app`

Share the URL + access code with your students. That's it! 🎉

---

## Cost estimate (Anthropic API)

| Scenario | Cost |
|----------|------|
| 1 student, 1 attempt | ~$0.02 |
| 57 students, 1 attempt each | ~$1.14 |
| 57 students, 3 attempts each | ~$3.42 |

Set a spending limit in the Anthropic console to stay in control.

---

## Changing the access code later

Edit `src/App.jsx` line 8 on GitHub → commit → Netlify auto-redeploys.

