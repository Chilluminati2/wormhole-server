# 🚀 Quick Deploy to Render - Step by Step

## What You Need
- A GitHub account (free)
- A Render account (free) - sign up at render.com

## Steps

### 1. Upload to GitHub

1. Go to [github.com](https://github.com) and log in
2. Click the **"+"** in top right → **"New repository"**
3. Name it: `wormhole-server`
4. Make it **Public**
5. Click **"Create repository"**

6. On the next page, you'll see "uploading an existing file". Click that, or:
   - Drag and drop these 3 files from the `server-deploy` folder:
     - `server.js`
     - `package.json`
     - `README.md`
7. Click **"Commit changes"**

### 2. Deploy on Render

1. Go to [render.com](https://render.com)
2. Sign up with your GitHub account (or create account)
3. Once logged in, click **"New +"** → **"Web Service"**
4. Click **"Connect a repository"** or **"Build and deploy from a Git repository"**
5. Find and select your `wormhole-server` repository
6. Fill in the form:
   - **Name**: `wormhole-signaling` (or any name you like)
   - **Region**: Choose closest to you
   - **Branch**: `main`
   - **Root Directory**: leave blank
   - **Environment**: `Node`
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Instance Type**: `Free`
7. Click **"Create Web Service"**

### 3. Wait for Deployment

- Render will start building your server
- This takes ~2-3 minutes
- You'll see logs scrolling
- When done, you'll see: **"Your service is live 🎉"**

### 4. Get Your Server URL

At the top of the page, you'll see your URL:
```
https://wormhole-signaling-xxxx.onrender.com
```

**Copy this URL!** You'll need it for the next step.

### 5. Update the Wormhole App

1. Open `src/webrtc.js` in your Wormhole project
2. Find line ~18 that says:
   ```javascript
   this.signalingServerUrl = 'ws://localhost:3000';
   ```
3. Change it to (use YOUR Render URL with `wss://`):
   ```javascript
   this.signalingServerUrl = 'wss://wormhole-signaling-xxxx.onrender.com';
   ```
4. Save the file

### 6. Test It!

1. Close any running Wormhole apps
2. Run `npm start` to start Wormhole
3. Your app should now connect to the Render server!
4. Send the updated app to your friend
5. Both of you can now connect! 🌀

---

## Troubleshooting

**"Failed to connect"**
- Make sure you used `wss://` (not `ws://`)
- Check your Render URL is correct
- Wait 30 seconds if server was sleeping (free tier)

**Server shows as "Suspended"**
- Free tier sleeps after 15 minutes
- First connection wakes it up (~30 seconds)
- Consider paid tier ($7/mo) for instant connections

**Still not working?**
- Check Render logs for errors
- Verify both users updated to the new server URL
- Test health endpoint: `https://your-url.onrender.com/health`

---

## Need Help?

Check the Render logs:
1. Go to your Render dashboard
2. Click on your `wormhole-signaling` service
3. Click "Logs" tab
4. Look for connection messages

Your server health: `https://your-service.onrender.com/health`
