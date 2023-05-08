# Discord bot client

```js
const { Client, Intents } = require("discord.js");

const client = new Client({
    intents: [
        Intents.FLAGS.GUILDS
    ]
});
```
