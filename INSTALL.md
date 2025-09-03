# Installation Guide – Gatekeeper Bot

This document describes how to install and run the **Gatekeeper Bot**.

---

## 1. Requirements
- **Debian 12** (or compatible Linux distribution)
- **Node.js 20+** (LTS recommended)
- **npm** (comes with Node.js)
- **Discord Bot Application** (create via [Discord Developer Portal](https://discord.com/developers/applications))
- Basic knowledge of Linux command line

---

## 2. Install Node.js and dependencies
```bash
sudo apt update
sudo apt install -y curl git build-essential
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
node -v   # should show v20.x
npm -v

3. Clone or create project folder

mkdir -p ~/bots && cd ~/bots
git clone https://github.com/yourname/gatekeeper-bot.git
cd gatekeeper-bot

If you don’t use git, create a folder and copy all project files manually.
4. Install packages

npm install

5. Configure environment

Create a .env file (based on .env.example):

DISCORD_TOKEN=your-bot-token
DISCORD_CLIENT_ID=your-application-client-id
TEST_GUILD_ID=your-guild-id   # optional, faster updates during testing
DATABASE_PATH=./data/bot.db

6. Build and register commands

npm run build
npm run register

7. Start the bot

npm start

You should see:

Ready! Logged in as Gatekeeper#1234

8. Run bot with PM2 (autostart)

Install PM2 globally:

sudo npm install -g pm2

Start bot:

pm2 start dist/index.js --name gatekeeper

Enable startup on boot:

pm2 save
pm2 startup

Check logs:

pm2 logs gatekeeper

9. Initial setup inside Discord

    Place bot’s role above Member/Guest/Language roles in the role hierarchy.

    Run:

/gatekeeper setup

    Select channels: Airlock, Approvals, Public Chat

    Select roles: Leaders, Member, Guest, Airlock

    Run:

/gatekeeper language bootstrap

    Creates predefined language roles for Members and Guests.

✅ Installation complete! Now see HOWTO.md
for usage instructions.
