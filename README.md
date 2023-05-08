# Basic DiscordJS v13 Bot
A simple tuto for a great bot!

## Configuration files

### Tree
```
my-bot/
├─ config/
│  ├─ bot.json
│  ├─ db.json
│  ├─ index.js
```

### bot.json
```js
{
    "token": "" // The token of your bot
}
```

### db.json
```js
{
    "host": "", // IP or HOST of the mysql server
    "port": 3306,
    "user": "", // Username
    "password": "", // Password
    "database": "" // The name of the database
}
```

#### index.js
```js
module.exports = {
    bot: require("./bot.json"),
    db: require("./db.json"),
    inviteSupport: "", // The invitation link of your Discord server
    ownerId: "",
    ownersId: []
};
```

## Database
Currently, I use [quick.db v9](https://github.com/plexidev/quick.db/tree/9.1.6), this module supports both local SQLite3 file and MySQL server connection.
```js
// Local SQLite3 File
const { QuickDB } = require("quick.db");

let db = {};
// For the tables
[ "guilds", "users" ].map((table) => {
    db[table] = new QuickDB({ table });
});

// MySQL Server Connection
const { QuickDB, MySQLDriver } = require("quick.db"); // Add mysql2 package for MySqlDriver: npm i mysql2

const mysql = new MySQLDriver({
    "host": "HOST",
    "port": 3306,
    "user": "USERNAME",
    "password": "PASSWORD",
    "database": "DATABASE"
});

mysql.connect().then(async () => {
    console.log(`DateBase connected`);

    let db = {};
    // For the tables
    [ "guilds", "users" ].map((table) => {
        db[table] = new QuickDB({ table, driver: mysql });
    });
}).catch((err) => {
    console.error(err.stack);
});
```

## Bot
```js
const { Client, Intents } = require("discord.js");

const client = new Client({
    intents: [
        Intents.FLAGS.GUILDS
    ]
});
```

## Handler events
```js
const eventFiles = fs.readdirSync("./events").filter((file) => file.endsWith(".js") || fs.statSync(`./events/${file}`).isDirectory());
for(const file of eventFiles) {
    const event = require(`./events/${file}`);
    const eventName = file.replace(/\.[^.]*$/, "");
    client.on(eventName, (...args) => event(client, db, ...args));
};
```
