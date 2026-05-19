# Verve Sales Enablement — Deployment Guide

## What this is
An internal sales enablement tool for Verve. AI-powered Q&A + searchable library of all sales materials.

## How to deploy (15 minutes, no coding needed)

### Step 1 — Get an Anthropic API key
1. Go to https://console.anthropic.com/settings/keys
2. Click **Create Key**, give it a name (e.g. "Verve Sales Enablement")
3. Copy the key — it starts with `sk-ant-`
4. Keep it somewhere safe, you'll need it in Step 3

### Step 2 — Deploy to Vercel
1. Go to https://vercel.com and sign up for a free account
2. Click **Add New → Project**
3. Choose **"Upload"** (you don't need GitHub)
4. Drag and drop this entire `verve-enablement` folder
5. Click **Deploy**

### Step 3 — Add your API key
1. Once deployed, go to your project in Vercel
2. Click **Settings → Environment Variables**
3. Add a new variable:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** paste your `sk-ant-...` key
4. Click **Save**
5. Go to **Deployments** and click **Redeploy** (so it picks up the new key)

### Step 4 — Share the URL
Vercel gives you a URL like `verve-enablement.vercel.app`
Share that with your team — no setup needed on their end, it just works.

---

## Updating materials
All materials are in `public/index.html` in the `MATERIALS` array near the bottom of the file.
Each entry looks like:
```
{title:"Material Name", platform:"Brand+ Marketplace", type:"Presentation", audience:"Demand", url:"https://..."}
```
Edit that array and redeploy to update the library.

## Costs
- Vercel hosting: **free** on the hobby plan
- Anthropic API: ~$0.003 per conversation at Sonnet rates — negligible for internal use
