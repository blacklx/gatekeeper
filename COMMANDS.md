# Gatekeeper Bot — Commands

_Last updated: 2025-09-03_

All commands are grouped under `/gatekeeper`.

---

## ⚙️ Setup & Configuration

### `/gatekeeper setup`
Interactive wizard to configure **channels** (Airlock, Approvals, Public Chat) and **roles** (Leader, Member, Guest, Airlock).

### `/gatekeeper config show`
Shows the current configuration for this guild in JSON format.

### `/gatekeeper config set-flag key:<flag> value:<on/off>`
Sets a boolean flag in the configuration.  
Available flags:
- `announce_after_onboarding` → announce in Public Chat after onboarding  
- `require_member_nick` → require nickname for Members  
- `auto_approve_guests` → auto-approve Guest role (no Leader approval)  
- `dm_onboarding` → (if enabled) use DMs for onboarding  

Example:

/gatekeeper config set-flag key:require_member_nick value:on


### `/gatekeeper config set-number key:<key> value:<number>`
Sets a numeric config value.  
Available numeric keys:
- `approval_timeout_hours` → hours before pending applications expire  

---

## 🌍 Language Management

### `/gatekeeper language add code:<code> autonym:<autonym> flag:<emoji>`
Adds or updates a language option for the server.  
- **code** = ISO code (e.g. `ru`, `uk`, `pt-BR`)  
- **autonym** = Language name in its own language (e.g. `Русский`, `Українська`)  
- **flag** = Flag emoji (e.g. 🇷🇺, 🇺🇦)

Example:

/gatekeeper language add code:ru autonym:Русский flag:🇷🇺


### `/gatekeeper language sync`
Creates missing roles for all languages previously added.  
This ensures both `(Guest)` and `(Member)` language roles exist.

### `/gatekeeper language bootstrap`
Bootstraps a predefined set of languages (en, ru, uk, ro, fr, de, tr, pt, pt-BR).  
Automatically creates Guest + Member roles for each.

### `/gatekeeper language list`
Lists all languages configured for this guild.

### `/gatekeeper language me code:<code>`
Sets **your own** language role.  
Removes all other language roles first.

### `/gatekeeper language set user:<@user> code:<code>`
(Leader only) Sets another user’s language role.

---

## 🧑 Nickname Management

### `/gatekeeper nickname me nick:<nickname>`
Changes **your own** nickname in the server.  
Fails if bot lacks permission or hierarchy is incorrect.

### `/gatekeeper nickname set user:<@user> nick:<nickname>`
(Leader only) Changes another user’s nickname.

---

## 🧪 Simulation / Testing

### `/gatekeeper simulate join user:<@user>`
Simulates a user joining the server.  
Starts the Airlock onboarding flow for the selected user.  
Useful for testing without using real new accounts.

---

## ✅ Leader Actions

These are **buttons** shown inside the **Approvals channel** when a new Member application is submitted:

- **Approve** → Grants Member + language role, removes Airlock.  
- **Reject** → Rejects and optionally kicks the user.  

---

## 🔑 Role Overview

- **Leader** → Can approve/reject applications, run setup/config, set nicknames, set languages for others.  
- **Member** → Regular approved members.  
- **Guest** → Guests and friends of members, limited access.  
- **Airlock** → Temporary role until onboarding is complete.  
- **Language roles (Guest/Member)** → One per language, automatically managed.  

---
