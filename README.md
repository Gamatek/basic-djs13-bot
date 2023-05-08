# Basic [DiscordJS@13]([https://github.com/discordjs/discord.js/tree/v13](https://github.com/discordjs/discord.js/tree/13.16.0)) Bot

### Sqlite Database
Currently, I use [quick.db@9](https://github.com/plexidev/quick.db/tree/9.1.6), this module supports both local SQLite3 file and MySQL server connection.
```js
const { QuickDB, MySQLDriver } = require("quick.db");
mysql.connect().then(async () => {
    console.log(`DateBase connected`);
    
    // CODE
}).catch((err) => {
    console.error(err.stack);
});
```
