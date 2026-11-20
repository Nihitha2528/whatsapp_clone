# WhatsChat

A WhatsApp-style chat app. Node.js server with **no npm dependencies** + vanilla JS frontend.

## Run
    node server.js          # then open http://localhost:3000
    PORT=8080 node server.js

Needs Node 16+. Open it in two browsers (or two devices on the same network:
http://YOUR-LAN-IP:3000), sign up with different usernames, and chat.
Camera, microphone, voice notes and calls need `localhost` or HTTPS.

## Structure
    server.js              REST API, Server-Sent Events, uploads, WebRTC signalling, bots
    package.json
    public/index.html
    public/css/style.css
    public/js/util.js      helpers, icons, modal/menu
    public/js/api.js       REST client + live event stream
    public/js/call.js      voice/video calls (WebRTC)
    public/js/app.js       UI and state
    data/                  created at runtime: db.json + uploads/

## Features
Accounts (scrypt-hashed passwords), 1:1 and group chats, realtime delivery, typing, online/last seen,
sent/delivered/read ticks, reply, edit, delete for me/everyone, forward, star, reactions, formatting,
emoji, photos/videos/files/audio, voice notes, location, polls, status (24h), voice/video calls,
pin/mute/archive, search, themes and wallpapers, profile photo, Helper/Echo bots.

## Notes
Data is a JSON file (fine for demos, not for scale). Video/voice calls use public STUN only;
behind strict NATs they may need a TURN server (edit `ICE` in public/js/call.js).
Put it behind HTTPS (e.g. a reverse proxy) before exposing it to the internet.
