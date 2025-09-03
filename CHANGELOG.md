# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Command `/gatekeeper language list` for showing all configured languages and roles.
- Command `/gatekeeper language me` to let users change their own language role.
- Command `/gatekeeper language set` to let Leaders assign language roles to members.

---

## [0.1.0] - 2025-09-03

### Added
- Initial onboarding flow (`/gatekeeper setup`) with Airlock, Approvals and Public chat.
- Language system with per-guild configuration and role creation.
- Distinction between **Guest** and **Member** language roles to enforce channel separation.
- Slash commands under `/gatekeeper` namespace to avoid conflicts with other bots.
- `language bootstrap` to pre-seed multiple common languages at once.
- `language sync` to automatically create missing Member/Guest roles.
- Approval workflow for Leaders with Approve/Reject buttons.
- Auto-approval option for Guests (`auto_approve_guests`).
- Config flags: `announce_after_onboarding`, `require_member_nick`, `auto_approve_guests`, `dm_onboarding`.
- Nickname support during onboarding and via `/gatekeeper nickname`.
- Simulation helper: `/gatekeeper simulate join` for testing new member onboarding.
- Multi-language support with JSON dictionaries (`i18n/en.json`, `ru.json`, `uk.json`, etc.).
- Welcome message improvements (short, per-language format).
- PM2/systemd support for production deployment.

### Changed
- Consolidated commands into a single `/gatekeeper` command with subcommands.
- Refactored language handling to maintain both Member and Guest roles per language.
- Approval buttons now disable after being clicked (prevents multiple approvals).
- Moved onboarding messages to **ephemeral** responses to avoid clutter in channels.
- Migrated to explicit JSON imports (`with { type: "json" }`) for Node.js 20+/22+ compatibility.
- Updated TypeScript config (`tsconfig.json`) for NodeNext module resolution.

### Fixed
- Duplicate commands showing up due to global vs guild registration.
- Old Guest language roles leaking into Member sections.
- "Unknown interaction" errors on long-running commands (`language bootstrap/sync`) by deferring replies.
- Nickname handling improved; bot now checks role hierarchy and permissions.
- Error handling for missing configs and invalid interactions.

[Unreleased]: https://github.com/blacklx/gatekeeper/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/blacklx/gatekeeper/releases/tag/v0.1.0
