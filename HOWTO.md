
---

# HOWTO.md

```markdown
# How to Use – Gatekeeper Bot

This document explains how to operate the **Gatekeeper Bot** once installed.

---

## 1. Onboarding Flow
1. New member joins server.
2. They are moved into **Airlock** role and see the onboarding message.
3. They select their **language**.
4. They choose **Guest** or **Member**:
   - **Guest** → Auto-approved → gets `Guest` + `Language (Guest)` role.
   - **Member** → Application sent to Leaders in #approvals → on approval, gets `Member` + `Language (Member)` role.
5. After onboarding, bot optionally posts a welcome in **Public Chat**.

---

## 2. Main Commands

### Setup & Config

/gatekeeper setup

Interactive wizard: choose channels and roles.

/gatekeeper config show

Show current guild config.

/gatekeeper config set-flag key:<flag> value:on|off

Change boolean settings (e.g. `auto_approve_guests`).

/gatekeeper config set-number key:approval_timeout_hours value:24

Change numeric settings.

---

### Languages

/gatekeeper language bootstrap

Pre-loads all predefined languages with Member/Guest roles.

/gatekeeper language list

Shows configured languages and their roles.

/gatekeeper language add code:<code> autonym:<name> flag:<emoji>

Add or update one language manually.

/gatekeeper language sync

Creates missing roles for all configured languages.

/gatekeeper language me code:<code>

Change your own language role.

/gatekeeper language set user:@user code:<code>

Leader-only: assign a language role to another member.

---

### Nicknames

/gatekeeper nickname me nick:<name>

Change your own nickname.

/gatekeeper nickname set user:@user nick:<name>

Leader-only: change another member’s nickname.

---

### Simulation (testing)

/gatekeeper simulate join user:@user

Pretend a user just joined (useful for testing onboarding).

---

## 3. Configuration Flags
- `announce_after_onboarding` → Post welcome message in Public Chat (on/off).
- `require_member_nick` → Force Member applicants to set in-game nickname.
- `auto_approve_guests` → Auto-approve Guests without manual approval.
- `dm_onboarding` → Run onboarding via DM instead of Airlock channel.

---

## 4. Channel Permissions
- **Airlock** → only Airlock role + Leaders see it.
- **Approvals** → Leaders only.
- **Guest Language Channels** → visible to Guests + Guest language roles.
- **Member Language Channels** → visible to Members + Member language roles.

---

## 5. Best Practices
- Keep bot’s role **at the top** of role hierarchy (above Members/Guests).
- Run `/gatekeeper language sync` after manual role changes.
- Disable Discord’s default welcome messages to avoid duplicates.
- Use `/gatekeeper config show` regularly to verify settings.

---

✅ That’s it! New members now have a smooth onboarding process.
