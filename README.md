# Wormhole Signaling Server

WebSocket signaling server for [Wormhole](https://github.com/yourusername/wormhole) P2P desktop portal.

## What This Does

This server helps two Wormhole apps find each other and establish a peer-to-peer connection. It doesn't handle any file transfers or video - those go directly between users.

## Deployment on Render

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

### Manual Deployment

1. Fork or clone this repository
2. Go to [Render Dashboard](https://dashboard.render.com/)
3. Click "New +" → "Web Service"
4. Connect your repository
5. Configure:
   - **Name**: `wormhole-signaling`
   - **Environment**: `Node`
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Plan**: Free
6. Click "Create Web Service"

Your server will be available at: `https://your-service-name.onrender.com`

## Health Check

Visit `https://your-service-name.onrender.com/health` to check server status.

## Environment Variables

- `PORT` - Automatically set by Render (default: 3000)

## Local Development

```bash
npm install
npm start
```

Server runs on `ws://localhost:3000`

## License

MIT
