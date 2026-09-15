# 🫧🦋 ʀuɴAk

A Telegram group management bot with a fun/economy side, built with **Pyrogram** + **MongoDB**.

**Owner:** [@rohon_x04](https://t.me/rohon_x04)

## Features

- **Moderation:** kick, ban, unban, mute, unmute, warn, warns, resetwarns, promote, demote
- **Locks:** block URLs, stickers, media, @usernames, or forwards per-group
- **Welcome:** custom welcome messages with placeholders, on/off toggle
- **Economy (Bubbles 🫧):** balance, daily reward, give, rob, leaderboard
- **Shop:** buy cosmetic items with Bubbles, /inventory
- **Fun & Games:** /roll /flip /8ball /rps /guess /hug /slap /pat /quote
- **Owner tools:** /broadcast, /stats

## 1. Get your credentials

| Credential | Where to get it |
|---|---|
| `API_ID` / `API_HASH` | https://my.telegram.org → API Development Tools |
| `BOT_TOKEN` | Message [@BotFather](https://t.me/BotFather), `/newbot` |
| `MONGO_URI` | https://www.mongodb.com/cloud/atlas → free M0 cluster → "Connect" → "Drivers" |
| `OWNER_ID` | Message [@userinfobot](https://t.me/userinfobot), it replies with your numeric ID |

Copy `.env.example` to `.env` and fill in the values for local testing.

## 2. Run locally

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 main.py
```

## 3. Deploy on Render

1. Push this project to a GitHub repo.
2. On [Render](https://render.com), create a **New → Background Worker** (not Web Service — this bot doesn't need to serve HTTP traffic, though `main.py` also opens a health-check port in case you pick Web Service instead).
3. Connect your repo.
4. Build command: `pip install -r requirements.txt`
5. Start command: `python3 main.py` (already set via the `Procfile`)
6. Add every variable from `.env.example` under **Environment → Environment Variables**.
7. Deploy. Check the logs — you should see `✅ MongoDB initialized` and `🚀 ʀuɴAk is starting...`.

## Notes

- Never commit `.env` or paste real tokens into files you share — `.gitignore` already excludes it.
- If a bot token or database credential is ever exposed publicly, regenerate it immediately via @BotFather / your MongoDB Atlas dashboard.
- Structured with inspiration from LearningBotsOfficial's Nomade group-manager skeleton and RoxxOP's Baka economy/fun plugins — rebuilt and rebranded for ʀuɴAk.
