# Basic DiscordJS v13 Bot
A simple tuto for a great bot!

1. [Adding a __configuration files__](https://github.com/Gamatek/basic-djs13-bot/blob/main/config.md)
2. [Adding a __database__](https://github.com/Gamatek/basic-djs13-bot/blob/main/db.md)
3. [Setup your __bot__](https://github.com/Gamatek/basic-djs13-bot/blob/main/bot.md)



## Handler events
```js
const eventFiles = fs.readdirSync("./events").filter((file) => file.endsWith(".js") || fs.statSync(`./events/${file}`).isDirectory());
for(const file of eventFiles) {
    const event = require(`./events/${file}`);
    const eventName = file.replace(/\.[^.]*$/, "");
    client.on(eventName, (...args) => event(client, db, ...args));
};
```
