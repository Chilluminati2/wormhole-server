# 📝 Render Deployment Checklist

## Pre-Deployment
- [ ] Created GitHub account
- [ ] Created Render account
- [ ] Uploaded server files to GitHub repository

## Deployment Steps
- [ ] Connected GitHub to Render
- [ ] Created new Web Service on Render
- [ ] Selected `wormhole-server` repository
- [ ] Configured build settings:
  - Build Command: `npm install`
  - Start Command: `npm start`
- [ ] Selected Free tier
- [ ] Clicked "Create Web Service"
- [ ] Waited for deployment (2-3 minutes)
- [ ] Verified service is live

## Post-Deployment
- [ ] Copied my Render URL: `_______________________________`
- [ ] Converted to WebSocket URL (wss://): `_______________________________`
- [ ] Updated `src/webrtc.js` with new URL
- [ ] Tested connection locally
- [ ] Sent updated app to friend
- [ ] Both tested connection together

## Server URL Template
```
HTTP URL:  https://wormhole-signaling-xxxx.onrender.com
WS URL:    wss://wormhole-signaling-xxxx.onrender.com
Health:    https://wormhole-signaling-xxxx.onrender.com/health
```

## My Deployed Server Info
- **Service Name**: _______________________________
- **Render URL**: _______________________________
- **WebSocket URL**: _______________________________
- **Deployment Date**: _______________________________

---

✅ Deployment complete! Your Wormhole server is live!
