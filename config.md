# Adding a configuration files
For the configuration of your bot, you can store in a single folder.

```
my-bot/
├─ config/
│  ├─ bot.json
│  ├─ db.json
│  ├─ index.js
│  index.js
```

## Files
``` js
// config/index.js
module.exports = {
    bot: require("./bot.json"),
    db: require("./db.json"),
    inviteSupport: "", // The invitation link of your Discord server
    ownerId: "", // The bot's owner
    ownersId: [] // Users admin, they will have access to the admin features
};

// config/bot.json
{
    "token": "" // The token of your bot
}

// config/db.json
{
    "host": "", // IP or HOST of the mysql server
    "port": 3306, // Default is 3306 of mysql server
    "user": "", // Username
    "password": "", // Password
    "database": "" // The name of the database
}
```

## Load configuration
```js
const config = require("./config.json");
...
```
