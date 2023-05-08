# Configuration files

## Tree
```
my-bot/
├─ config/
│  ├─ bot.json
│  ├─ db.json
│  ├─ index.js
```

## bot.json
```js
{
    "token": "" // The token of your bot
}
```

## db.json
```js
{
    "host": "", // IP or HOST of the mysql server
    "port": 3306,
    "user": "", // Username
    "password": "", // Password
    "database": "" // The name of the database
}
```

## index.js
```js
module.exports = {
    bot: require("./bot.json"),
    db: require("./db.json"),
    inviteSupport: "", // The invitation link of your Discord server
    ownerId: "",
    ownersId: []
};
```
