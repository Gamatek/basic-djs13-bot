# Discord bot client
Package required for this part : `discord.js@13`

```js
const { Client, Intents } = require("discord.js");

const client = new Client({
    intents: [
        Intents.FLAGS.GUILDS
    ]
});
```
