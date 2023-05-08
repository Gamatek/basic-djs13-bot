# Database
Currently, I use [quick.db v9](https://github.com/plexidev/quick.db/tree/9.1.6), this module supports both local SQLite3 file and MySQL server connection.

## Local SQLite3 File
```js
const { QuickDB } = require("quick.db");

let db = {};
// For the tables
[ "guilds", "users" ].map((table) => {
    db[table] = new QuickDB({ table });
});
```

##MySQL Server Connection
```js
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
