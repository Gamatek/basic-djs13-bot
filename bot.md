# Discord bot client
Package required: `npm i discord.js@13`

With the arrival of DiscordJS v13, we must now give the *intents* of our bot. The `GUILDS` intent is required.

```js
const { Client, Intents } = require("discord.js");

const client = new Client({
    intents: [
        Intents.FLAGS.GUILDS
    ]
});
```
