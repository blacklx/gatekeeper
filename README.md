# Gatekeeper Bot

Gatekeeper is a **Discord onboarding bot** built for gaming communities and alliances.  
It manages new users through an **Airlock system**, assigns them roles based on **language** and **membership type** (Guest/Member), and lets Leaders approve or reject applications.

---

## ✨ Features
- **Airlock channel** for new arrivals  
- **Language selection** (auto-creates Guest & Member roles per language)  
- **Guest auto-approval** or **Leader approval** for Members  
- **Nickname collection** for Members (e.g. in-game name)  
- **Configurable via slash commands** (`/gatekeeper setup`, `/gatekeeper config …`)  
- **Simulate onboarding** for testing  
- **Works across multiple servers** (guild-specific configuration)  
- **SQLite database** for lightweight storage  

---

## 📸 Example Flow
1. New user joins → placed in **Airlock**.  
2. They select their **language**.  
3. They choose **Guest** or **Member**:  
   - **Guest** → immediately gets Guest + language role.  
   - **Member** → application sent to Leaders in Approvals channel.  
4. Leaders approve → user gets Member + language role.  
5. Bot optionally posts a welcome message in **Public Chat**.  

---

## 📖 Documentation
- [INSTALL.md](./INSTALL.md) → How to install and run Gatekeeper  
- [HOWTO.md](./HOWTO.md) → How to use Gatekeeper inside Discord  
- [COMMANDS.md](./COMMANDS.md) → Full command reference  
- [PRIVACY.md](./PRIVACY.md) → Privacy policy  
- [TERMS.md](./TERMS.md) → Terms of service  
- [CHANGELOG.md](./CHANGELOG.md) → Updates and changes  

---

## ⚙️ Requirements
- **Debian 12** (or Linux host)  
- **Node.js 20+**  
- **Discord bot application** (created in [Discord Developer Portal](https://discord.com/developers/applications))  
- Permissions: `Manage Roles`, `Manage Nicknames`, `Send Messages`, `View Channels`

---

## 🛠️ Tech Stack
- [discord.js v14](https://discord.js.org/)  
- [TypeScript](https://www.typescriptlang.org/)  
- [SQLite](https://www.sqlite.org/) (via `better-sqlite3`)  
- Runs on [Node.js](https://nodejs.org/)  

---

## 📦 Installation
```bash
git clone https://github.com/yourname/gatekeeper-bot.git
cd gatekeeper-bot
npm install
cp .env.example .env   # fill in your Discord token, client ID, etc.
npm run build
npm run register
npm start

For full instructions see INSTALL.md

.
🚀 Usage

Inside your Discord server:

    Run /gatekeeper setup → select Airlock, Approvals, Public channels and roles.

    Run /gatekeeper language bootstrap → creates predefined language roles.

    Invite test users or use /gatekeeper simulate join.

For details see HOWTO.md

.
🔒 Security

    Bot stores only minimal user data (user IDs, language choice, nickname, status).

    No chat messages or sensitive personal data are stored.

    See PRIVACY.md

    for full details.

📜 License

This project is private for now, but can be adapted for other alliances/servers.
All use is subject to TERMS.md
.
