# 🤖 Slobos & Mr. Juice Aternos 24/7 Hosting Bot

A Minecraft bot that helps keep an Aternos server online 24/7 by automatically joining it using a Mineflayer-based bot. Perfect for SMPs or small multiplayer servers that shut down when no players are online.

---

## ✨ Features
*   ✅ **Auto-Connect**: Automatically joins your server.
*   ✅ **Infinite Uptime**: Prevents AFK kicks and server shutdowns.
*   ✅ **Smart Reconnect**: Automatically reconnects if the internet drops or server restarts.
*   ✅ **Render-Ready**: Includes "Self-Ping" to run 24/7 for FREE on Render.com.
*   ✅ **Plugin Support**: Compatible with Paper/Spigot/Bukkit (auto-auth included).

---

## 🛠️ Requirements
*   **GitHub Account**
*   **Aternos Server**
*   **Render Account** (for 24/7 hosting)
*   **Common Sense!** 🧠        

---

## 🚀 Setup Guide

We have made setup super easy! Check out the guide below:

[**Detailed Google Doc Guide**](https://docs.google.com/document/d/1Fl0dRzP6O30ehp5-QcaB11IobF8I1JJhKUipzCWiCYA/edit?tab=t.0).

---

## ⚙️ Usage
*   **Start**: Just turn on your Aternos server. The bot will join automatically.
*   **Status**: Visit the Render URL to see a status dashboard.
*   **Chat**: The bot logs chat to the console.

### Auto-auth configuration (`settings.json`)

Set `utils.auto-auth.mode` to control whether the bot sends auth commands:

* `none` (default) → never sends `/login` or `/register`
* `login` → sends `/login <password>`
* `register_then_login` → sends `/register <password> <password>` when prompted, and `/login <password>` when needed

> If auth mode is `login` or `register_then_login`, `utils.auto-auth.password` must be set.

#### Example: server **without** `/login` (online-mode)

```json
"auto-auth": {
  "enabled": false,
  "mode": "none",
  "password": ""
}
```

#### Example: server **with** `/login` (AuthMe/offline-mode)

```json
"auto-auth": {
  "enabled": true,
  "mode": "login",
  "password": "yourAuthPassword"
}
```

## 🧰 Troubleshooting

### `lost connection: You logged in from another location`

This means the same Minecraft username is connected from somewhere else at the same time.

To fix:
- Run only **one** AFK bot instance per account.
- Check hosting process managers (Render restarts, PM2, nodemon, duplicate deploys) so they are not launching multiple bot processes.
- Increase `utils.auto-reconnect-delay` in `settings.json` if your host/server is unstable and reconnects are too aggressive.

Recent versions also log connection lifecycle events (connect/spawn/kick/end/reconnect scheduled/canceled) so you can see exactly when reconnects are triggered.

---

## ⚠️ Disclaimer
This project is not affiliated with Aternos, Mojang, or Microsoft. Use at your own risk. Misuse may violate platform terms of service. This bot does not bypass Aternos queue limits; it only keeps the server active once it is online.

---

## ❤️ Credits
*   **Slobos (Discord: sloboscc)** — Original creator & idea. (The GOAT 🐐)
*   **Mr.Juice (Discord: Mr.Juice3046)** — Updates, Guide, & Maintenance.

**License**: MIT License
