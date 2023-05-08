# Database

<img src="./assets/quickdb.png">

Package required: `npm i quick.db@9`

Currently, I use [quick.db v9](https://github.com/plexidev/quick.db/tree/9.1.6), this module supports both local SQLite3 file and MySQL server connection.

## Local SQLite3 File
If you want a mysql server, please install this packages: `npm i better-sqlite3 quick.db@9` and [node-gyp](https://github.com/nodejs/node-gyp).
```js
const { QuickDB } = require("quick.db");

let db = {};
// For the tables
[ "guilds", "users" ].map((table) => {
    db[table] = new QuickDB({ table });
});
```

## MySQL Server Connection
If you want a mysql server, please ALSO install this packages: `npm i mysql2 quick.db@9`
```js
const { QuickDB, MySQLDriver } = require("quick.db");

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
