# 🤖 Artemis Nerd Café Discord Bot

A modular Discord bot built with [discord.py](https://github.com/Rapptz/discord.py) for the **Nerd Café** community server. Artemis handles moderation, antispam, a reputation system, support tickets, anonymous confessions, exam utilities, logging, server statistics, and much more. It was built to be an all in one bot for any community no matter the scale. 

> **Bot version:** `26.0.0` · **Prefix:** `--- ` (plus several `?fun` commands) · **Primary:** Slash commands

---



## ✨ Features

### 🛡️ Moderation

- **`/ban` `/unban` `/kick` `/mute` `/unmute` `/warn`** — full mod command with case IDs, MongoDB case logging, DM notifications, and rich log embeds.
- **`/record`** — paginated punishment history per user (also available as a right-click context menu), with summary mode.
- **`/delete_record`** — remove a case by ID.
- **`/automod`** — ***
- **Cheese Touch channel watcher** ***
- **Cross-channel duplicate watcher** 

### 🚨 Anti-Spam & Auto-Moderation (`antispamfilters.py`)

- **NSFW image detection** ***
- **Phishing detection** ***

### ⭐ Reputation System

- Automatic +1 rep when members thank each other (reply or mention) in mapped subject channels.
- **`/rep`** — per-user rep card with channel breakdown, monthly count, and rank (Bronze/Silver/Gold).
- **`/leaderboard`** — server-wide or per-channel top 50 with pagination.
- **`/rep_control`** — staff-only add/remove/set reps globally or per channel.
- 100+ rep members automatically receive the "Caffieated" role. 
- Easter egg: ***

### 🎫 Support Tickets

- Persistent dropdown panel with different ticket types, each routed to its own staff roles.
- Spam and misuse protection
- Full audit logging to a log channel; closed tickets management.

### 🕵️ Anonymous Confessions

- `/confess` opens a modal; submissions go to a private approval channel with persistent ✅/❌ buttons.
- Approved confessions are numbered (`Confession #N`) and posted publicly — submitter identity is never revealed or stored for privacy purpose. 

### 🗄️ Channel Archiving
***

### 📝 Logging

***

### 📊 Server Statistics

***

### 🆘 Helper Auto-Ping

**
### 🎓 Study Utilities

- `/find_questions` and `/random_pyp` — search paper.sc for Cambridge IGCSE/A-Level papers.
- `/timetable` — parse official Cambridge timetableand browse exams by subject, zone, series, or date.

### 🎨 Fun & Community

- **`/rules`** full rules embed + persistent dropdown (`/rules_dd`), 
- **`/profile`** (Components V2 layout view with status/devices/roles/permissions), 
- **`/colour`** self-assignable colour roles, 
- boost announcements with role auto-mapping, 
- welcome banner image with the member's avatar composited in, 
- counting channel game, 
- keyword auto-responses, 
- dad-jokes
- a number guessing game

### 🧩 Module System

Every subsystem can be toggled at runtime with **`/update`** and inspected with **`/status`** — useful for maintenance or debugging without restarting.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- A MongoDB cluster 
- Discord application 

### Installation

```bash
git clone https://github.com/<you>/artemis-bot.git
cd artemis-bot
pip install -r requirements.txt
```

### Environment Variables

Create a `.env` file:

```env
BOT_TOKEN=your_discord_bot_token
MONGO_LINK=mongodb+srv://user:pass@cluster/main
```

### Required assets (repo root)

| File | Used by |
| --- | --- |
| `nclogo.png` | Rules embeds, rep leaderboard, boost embeds |
| `welcome_banner.png` | Welcome image background (avatar is composited into the circle) |
| `edited_image.png` / `nc_social.png` | Ticket panel & welcome previews |
| `channel_role_map.json` | Helper-ping channel → role mapping |


### Running the bot

```bash
python app.py
```

---

## 🗂️ Project Structure

---

## 📖 Command Reference (highlights)

---

## ⚙️ Configuration

Almost everything is driven by IDs in **`constants_main.py`**:
The current system is very hardcoded with channel, role and other IDs, in future updates (if any) plans to make the system truly modular and global

- **Channels:** error thread, command log, rep log, mod log/chat, DM log, confession channels, ticket panel/log, archive forums, 
- **Roles:** muted, focus, colour roles, "server owner" vanity role, allowed-role lists for each command tier.
- **Rep words** (`acknowledgment_words`) 

---

## 🧪 Error Handling & Reliability


---

## 🤝 Contributing

1. Fork the repo and create a feature branch.
2. Keep modules self-contained (one file per feature) and wire them through `app.py`.
3. Use `await report_error(bot, guild, e)` for exception reporting instead of bare prints.
4. Run `/status` and `/dbcheck` before and after changes.

---

## 📄 License

This project is private to the Nerd Café team. All rights reserved.

---

This readme was partially written with AI (you will know which parts are AI).

Some features are kept secret or entirely not mentioned cuz they are really unique systems that i have yet to see in any other bots

*Made with caffeine and love for the Nerd Café community.*
