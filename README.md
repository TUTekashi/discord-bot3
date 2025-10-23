# Discord Translation Bot

A Discord bot that provides seamless message translation using the DeepL API. Users can translate any message to their preferred language with a simple right-click.

## Features

- **One-Click Translate Buttons**: Bot automatically adds a "🌍 Translate" button under each message
- **Context Menu Translation**: Right-click any message and select "Translate Message"
- **Ephemeral Responses**: Translations appear only to you in the same channel
- **25+ Languages**: Support for Arabic, Chinese, English, Spanish, French, German, Japanese, and more
- **Smart Caching**: Reduces API calls by caching translations for 6 hours
- **Channel Control**: Admins can enable/disable translation per channel

## How to Use

### For Users

1. **Set Your Language**
   - Use `/setlanguage` command
   - Select your preferred language from the dropdown
   - You'll receive a confirmation message

2. **Translate Messages** (Two easy ways!)
   
   **Option A - Click the Button:**
   - Look for the "🌍 Translate" button under any message
   - Click it to see your translation instantly (only you can see it!)
   
   **Option B - Right-Click Menu:**
   - Right-click (or long-press on mobile) any message
   - Select "Apps" → "Translate Message"
   - You'll see the translation instantly (only you can see it!)

### For Administrators

1. **Enable Translation in Channels**
   - Use `/settranslatechannel` command
   - Select the channel where you want translation enabled
   - Choose "Add" to enable or "Remove" to disable

## Setup

### Prerequisites

- Node.js v20 or higher
- A Discord bot application (create one at [Discord Developer Portal](https://discord.com/developers/applications))
- A DeepL API key (free or paid, from [DeepL](https://www.deepl.com/pro-api))

### Required Environment Variables

Add these to your Replit Secrets or `.env` file:

```
DISCORD_TOKEN=your_discord_bot_token
DEEPL_KEY=your_deepl_api_key
CLIENT_ID=your_discord_application_id
```

### Installation

1. Install dependencies:
   ```bash
   npm install
   ```

2. Deploy commands to Discord:
   ```bash
   node clear-and-deploy.js
   ```

3. Start the bot:
   ```bash
   node index.js
   ```

### Bot Permissions

Your bot needs these permissions:
- Read Messages/View Channels
- Send Messages
- Use Application Commands

Invite URL format:
```
https://discord.com/api/oauth2/authorize?client_id=YOUR_CLIENT_ID&permissions=277025508352&scope=bot%20applications.commands
```

## Supported Languages

Arabic, Bulgarian, Chinese, Czech, Dutch, English, Finnish, French, German, Greek, Hungarian, Italian, Japanese, Korean, Latvian, Lithuanian, Polish, Portuguese, Russian, Slovak, Slovenian, Spanish, Swedish, Turkish, Ukrainian

## Project Structure

```
├── commands/
│   ├── setlanguage.js          # User language preference command
│   ├── settranslatechannel.js  # Admin channel configuration
│   └── translate.js            # Context menu translation command
├── data/
│   ├── cache.json              # Translation cache
│   ├── translateChannel.json   # Enabled channels
│   └── userLanguages.json      # User language preferences
├── index.js                    # Main bot file
└── clear-and-deploy.js         # Command deployment script
```

## How It Works

1. **Language Detection**: When you request a translation, the bot automatically detects the source language
2. **Translation**: DeepL API translates the message to your preferred language
3. **Caching**: Translations are cached for 6 hours to reduce API usage
4. **Ephemeral Display**: You see the translation as an ephemeral message (private to you)

## Differences from DM-based Systems

This bot uses ephemeral messages instead of DMs, which means:
- ✅ No need to enable DMs from server members
- ✅ Translations appear in context (same channel as the message)
- ✅ Cleaner user experience
- ✅ No spam in DM inbox

## Support

For issues or questions, check the bot logs or review the DeepL API status if translations aren't working.
