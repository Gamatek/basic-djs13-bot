# Configuration files exemple
For the configuration of your bot, you can store in a single folder.

```
my-bot/
├─ config/
│  ├─ bot.json
│  ├─ db.json
│  ├─ index.js
│  index.js
```

``` js
// config/index.js
module.exports = {
    bot: require("./bot.json"),
    db: require("./db.json"),
    inviteSupport: "", // The invitation link of your Discord server
    ownerId: "",
    ownersId: []
};

// config/bot.json
{
    "token": "" // The token of your bot
}

// config/db.json
{
    "host": "", // IP or HOST of the mysql server
    "port": 3306,
    "user": "", // Username
    "password": "", // Password
    "database": "" // The name of the database
}
```
