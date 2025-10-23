# Discord Translation Bot

## Overview
This is a Discord bot that provides message translation functionality using the DeepL API. Users can right-click any message and select "Translate Message" to see an instant translation in their preferred language. Translations appear as ephemeral messages (only visible to the requesting user) directly in the channel.

## Project Type
Backend Discord bot application (no frontend)

## Tech Stack
- **Runtime**: Node.js (CommonJS)
- **Bot Framework**: Discord.js v14
- **Translation API**: DeepL API
- **Storage**: JSON files for user preferences and caching

## Features
- **Automatic Translate Buttons**: Bot automatically adds a "🌍 Translate" button under each message in translation channels
- **Context Menu Translation**: Right-click any message and select "Translate Message"
- **Ephemeral Responses**: Translations appear only to the requesting user in the same channel (no DMs)
- **Language Preferences**: Users can set their preferred language using `/setlanguage` command
- **Admin Controls**: `/settranslatechannel` command to configure which channels support translation
- **Caching**: Translation cache to reduce API calls and improve performance (6-hour cache)
- **Multi-language Support**: Supports 25+ languages via DeepL

## Required Environment Variables
- `DISCORD_TOKEN`: Discord bot token (from Discord Developer Portal)
- `DEEPL_KEY`: DeepL API key (from DeepL website)
- `CLIENT_ID`: Discord Application ID (for deploying commands)

## File Structure
- `index.js`: Main bot file with interaction handlers and cache cleanup
- `commands/`: Command handlers
  - `setlanguage.js`: User language preference slash command
  - `settranslatechannel.js`: Admin command to configure translation channels
  - `translate.js`: Context menu command for translating messages
- `data/`: JSON storage files
  - `userLanguages.json`: User language preferences
  - `translateChannel.json`: Configured translation channels
  - `cache.json`: Translation cache
- `clear-and-deploy.js`: Script to deploy commands to Discord

## Setup Instructions
1. Ensure `DISCORD_TOKEN` and `DEEPL_KEY` secrets are configured in Replit Secrets
2. Run `npm install` to install dependencies
3. The bot will start automatically via the "Discord Bot" workflow

## Discord Bot Setup
To use this bot in your Discord server:
1. Create a bot application in Discord Developer Portal
2. Enable these intents in the bot settings:
   - Message Content Intent
   - Server Members Intent (optional)
   - Presence Intent (optional)
3. Invite the bot to your server with appropriate permissions
4. Use `/settranslatechannel` command (admin only) to configure which channels support translation
5. Users can use `/setlanguage` command to set their preferred language and translation mode

## Current Configuration
- **Translation Channels**: 1 channel configured (ID: 1149772212509880551)
- **Registered Users**: 2 users with language preferences configured
- **Bot Status**: Running successfully

## Recent Changes
- **October 22, 2025**: 
  - Project imported into Replit environment
  - Refactored from reaction-based DM system to context menu with ephemeral messages
  - Removed reaction emoji and auto-translation modes
  - Added context menu command "Translate Message"
  - Added automatic "🌍 Translate" buttons under each message in translation channels
  - Simplified user experience (no more DMs, translations appear in-channel)
  - Fixed discord.js v15 deprecation warning (ready → clientReady)
  - Dependencies installed, workflow configured
