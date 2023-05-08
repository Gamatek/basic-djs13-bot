# Creation of your bot with DiscordJS v13
Package required: `npm i discord.js@13`

With the arrival of DiscordJS v13, we must now give the *intents* of our bot. The `GUILDS` intent is required.

```js
const { Client, Intents } = require("discord.js");

const client = new Client({
    intents: [
        Intents.FLAGS.GUILDS
    ]
});

client.on("ready", () => {
    console.log(`Logged in as ${client.user.ta}`);
});

client.login(config.token);
```

### List of intents
```
GUILDS
GUILD_MEMBERS *
GUILD_BANS
GUILD_EMOJIS_AND_STICKERS
GUILD_INTEGRATIONS
GUILD_WEBHOOKS
GUILD_INVITES
GUILD_VOICE_STATES
GUILD_PRESENCES *
GUILD_MESSAGES
GUILD_MESSAGE_REACTIONS
GUILD_MESSAGE_TYPING
GUILD_SCHEDULED_EVENTS

DIRECT_MESSAGES
DIRECT_MESSAGE_REACTIONS
DIRECT_MESSAGE_TYPING

MESSAGE_CONTENT *

AUTO_MODERATION_CONFIGURATION
AUTO_MODERATION_EXECUTION

* Privileged Gateway Intents
```
