# Privacy Policy

_Last updated: 2025-09-03_

This document describes how the **Gatekeeper Bot** handles user data.

## Data We Collect
- **Discord user IDs** and **guild IDs** (for linking onboarding state to the correct server).
- **Language selection** and chosen role (Guest or Member).
- **Optional nickname** if provided during onboarding.
- **Application status** (pending, approved, rejected, expired).
- **Timestamps** (created/updated).

## Data We Do NOT Collect
- We do not collect or store message content from Discord channels.
- We do not track or log IP addresses, locations, or device information.
- We do not sell or share data with third parties.

## Data Storage
- Data is stored in a local SQLite database (`data/bot.db`) on the server where the bot is hosted.
- Only server administrators who run the bot have access to this database.
- Data is retained only for the purpose of onboarding and role management.

## Data Deletion
- Guild owners/admins may request a full purge of stored data for their guild at any time.
- Users leaving the server will not automatically be deleted from the database, but entries can be removed manually on request.

## Security
- The bot only stores the minimal data required to function.
- The database is stored on a secured server with restricted access.
- Discord OAuth tokens and sensitive configuration values are kept in `.env` and not shared.

## Contact
If you have questions or requests regarding your data, please contact the administrators of the server running Gatekeeper Bot.
