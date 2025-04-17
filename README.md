<div align='center'>
    <h1>
        CroxyDB
    </h1>
    <p>
       <a href='https://nodei.co/npm/croxydb/'><img src='https://nodei.co/npm/croxydb.png' alt='NPM info' /></a>
    </p>
    <p>
        <a href='https://www.npmjs.com/package/croxydb'><img src='https://img.shields.io/npm/dt/croxydb.svg?style=for-the-badge' alt='Total Download' /></a>
        <a href='https://www.npmjs.com/package/croxydb'><img src='https://img.shields.io/npm/dm/croxydb.svg?style=for-the-badge' alt='Monthly Download' /></a>
        <a href='https://www.npmjs.com/package/croxydb'><img src='https://img.shields.io/npm/dw/croxydb.svg?style=for-the-badge' alt='Weekly Download' /></a>
    </p>
    <p>
        <a href='https://www.npmjs.com/package/croxydb'><img src='https://img.shields.io/npm/l/mzrdb.svg?style=for-the-badge' alt='License' /></a>
        <a href='https://discord.gg/ABjAfsvy5J' target='_blank'> <img alt='Discord' src='https://img.shields.io/badge/Support-Click%20here-7289d9?style=for-the-badge&logo=discord'> </a>
    </p>
</div>

## What's new in 0.0.26?
- You can now reduce down to - in the 'db.subtract' function.

# Examples
## Moving Everything to CroxyDB (QuickDB)
```js
const db = require('croxydb');
const quickdb = require('quick.db');

await db.move(quickdb);
```

## Moving Everything to MongoDB (Local CroxyDB)
```js
const db = require('croxydb');
const jsondb = require('../your_file.json');

db.setAdapter('mongo', { url: 'YOUR_MONGO_URL', Schema: 'Schema Name' });

db.moveToMongo(jsondb);
```

## All Local CroxyDB Examples
```js
const db = require('croxydb');

db.set('x.y.z', 'abc') // abc

db.get('x') // { y: { z: 'abc' } }
db.fetch('x') // { y: { z: 'abc' } }
db.all() // { x: { y: { z: 'abc' } } }

db.push('a', 'hello') //  [ 'hello' ]
db.push('a', 'world') //  [ 'hello', 'world' ]
db.unpush('a', 'hello') // [ 'world' ]

db.push('b', { test: 'croxydb' }) // [ { test: 'croxydb' } ]
db.push('b', { test2: 'croxydb2' }) // [ { test: 'croxydb' }, { test2: 'croxydb2' } ]
db.delByPriority('b', 1) // [ { test2: 'croxydb' } ]
db.setByPriority('b', { newtest: 'hey this is edited' }, 1) // [ { newtest: 'hey this is edited' } ]

db.has('x') // true
db.delete('x') // true
db.deleteAll() // true
```

## All CroxyDB Mongo Examples
```js
const db = require('croxydb');
db.setAdapter('mongo', {
    url: 'Your Mongo URL', 
    schema: 'Schema Name' // Not required. You can't define your own schema. Just name.
});

await db.set('x.y.z', 'abc') // abc

await db.get('x') // { y: { z: 'abc' } }
await db.fetch('x') // { y: { z: 'abc' } }
await db.all() // { x: { y: { z: 'abc' } } }

await db.push('a', 'hello') //  [ 'hello' ]
await db.push('a', 'world') //  [ 'hello', 'world' ]
await db.unpush('a', 'hello') // [ 'world' ]

await db.push('b', { test: 'croxydb' }) // [ { test: 'croxydb' } ]
await db.push('b', { test2: 'croxydb2' }) // [ { test: 'croxydb' }, { test2: 'croxydb2' } ]
await db.delByPriority('b', 1) // [ { test2: 'croxydb' } ]
await db.setByPriority('b', { newtest: 'hey this is edited' }, 1) // [ { newtest: 'hey this is edited' } ]

await db.has('x') // true
await db.delete('x') // true
await db.deleteAll() // true
```
> MongoDB Support (It is new feature, if you find any bugs join my [Discord](https://discord.gg/ABjAfsvy5J))

## All Options Examples
```js
const db = require('croxydb');

db.setReadable(true) // It makes readable your JSON DB file.
db.noBlankData(true) // If you delete anything from object and new object size is less than 1, automaticly removes that object.
db.setAdapter('yamldb') // It makes adapter as YAML adapter. Default adapter is JsonDB
db.setFolder('folder') // You can set database folder name
db.setFile('db') // You can set database file name
db.setCheckUpdates(true) // It warns you if any updates happens.

db.set('x.y.z', 'abc') // abc

db.get('x') // { y: { z: 'abc' } }
db.fetch('x') // { y: { z: 'abc' } }
db.all() // { x: { y: { z: 'abc' } } }

db.push('a', 'hello') //  [ 'hello' ]
db.push('a', 'world') //  [ 'hello', 'world' ]
db.unpush('a', 'hello') // [ 'world' ]

db.push('b', {test: 'croxydb'}) // [ { test: 'croxydb' } ]
db.push('b', {test2: 'croxydb2'}) // [ { test: 'croxydb' }, { test2: 'croxydb2' } ]
db.delByPriority('b', 1) // [ { test2: 'croxydb' } ]
db.setByPriority('b', { newtest: 'hey this is edited' }, 1) // [ { newtest: 'hey this is edited' } ]

db.has('x') // true
db.delete('x') // true
db.deleteAll() // true
```

## Contact & Support
[![Discord Server](https://api.weblutions.com/discord/invite/ABjAfsvy5J)](https://discord.gg/ABjAfsvy5J)
