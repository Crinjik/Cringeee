[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)
[![Discord Bots](https://top.gg/api/widget/servers/788083161296273517.svg)](https://top.gg/bot/788083161296273517)

# Minecraft Server Status - Discord Bot
A simple [Discord.js](https://www.npmjs.com/package/discord.js) bot that displays the status of [Minecraft](https://minecraft.gamepedia.com) servers using the [mcping-js](https://www.npmjs.com/package/mcping-js) node module.

## Features
- Self-updating voice channels to display the server's status and the number of players online
- Support for monitoring multiple Minecraft servers at once
- See the usernames of the players on the server
- Check the status of non-monitored servers
- Slash command support with ephemeral responses to prevent channels from being cluttered with commands

## Setup

### Method 1: Invite the Bot
- [Invite](https://discord.com/api/oauth2/authorize?client_id=788083161296273517&permissions=268435472&scope=bot%20applications.commands) the bot to your server

### Method 2: Heroku Deployment
*Note: self-hosting through Heroku deployment is still being worked on*
- Follow [this](https://discordjs.guide/preparations/setting-up-a-bot-application.html) guide and [this](https://discordjs.guide/preparations/adding-your-bot-to-servers.html) guide to set up and invite the bot to your server. When creating the invite link, make sure to check the boxes for **Manage Roles** and **Manage Channels**
- Use the **Deploy to Heroku** button to create an instance of the bot
- Fill out the configuration variables using your client ID (found in the "OAuth2" section of the Discord Developer Portal) and bot token (found in the "Bot" section of the Discord Developer Portal)

## Usage
- Use `/monitor ip` (replace `ip` with the IP address of the server you would like to monitor) to create two self-updating voice channels that display the server's status and the number of players online
- Use `/status` to get a detailed report of the default server's status (the first server that was monitored that hasn't been unmonitored). This detailed report includes the server's status, the number of players online, a list of usernames corresponding to the players online, and the server's version
- Use `/status ip` to get a detailed report of the specified server's status
- Use `/unmonitor ip` to delete the self-updating channels corresponding to the specified server
- Use `/unmonitor all` to delete all of the self-updating channels. This should be done prior to removing the bot from the server

## Commands
- `/help` - List the other commands
- `/status [ip]` - Displays the current status and active players for the default server or the specified IP address
- `/monitor ip` - Monitor the server with the specified IP address
- `/unmonitor ip|all` - Unmonitor the server with the specified IP address or all servers

## To-Do
- Allow users to manage default server for `/status` command (`/default ip` command and `/monitor ip [default]` option, add new key-value pair to server object and use findIndex to get default server)
- Allow users to set a nickname for the server (`/nickname` command and `/monitor ip nickname`)
- Add graph support (see [this](https://github.com/cappig/MC-status-bot) repository)
- Self-hosting via Heroku deployment