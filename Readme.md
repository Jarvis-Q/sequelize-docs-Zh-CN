# Sequelize Docs 中文版

![](http://docs.sequelizejs.com/manual/asset/logo-small.png)

[![Travis build](https://img.shields.io/travis/sequelize/sequelize/master.svg?style=flat-square)](https://travis-ci.org/sequelize/sequelize)
[![npm](https://img.shields.io/npm/dm/sequelize.svg?style=flat-square)](https://npmjs.org/package/sequelize)
[![npm](https://img.shields.io/npm/v/sequelize.svg?style=flat-square)](https://github.com/sequelize/sequelize/releases)

> 此项目同步自 [sequelize](https://github.com/sequelize) / [sequelize](https://github.com/sequelize/sequelize) 项目中的  docs. 除特殊情况, 将保持每月一次的同步频率.
> 
> 更新日志请参阅: [CHANGELOG](CHANGELOG.md)

Sequelize 是一个基于 promise 的 Node.js ORM, 目前支持 Postgres, MySQL, SQLite 和 Microsoft SQL Server. 它具有强大的事务支持, 关联关系, 读取和复制等功能.


## 使用示例

[Basic usage - 基本用法](./book/usage.md)

```js
const Sequelize = require('sequelize');
const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: 'mysql'|'sqlite'|'postgres'|'mssql',

  pool: {
    max: 5,
    min: 0,
    acquire: 30000,
    idle: 10000
  },

  // 仅限 SQLite
  storage: 'path/to/database.sqlite',

  // 请参考 Querying - 查询 操作符 章节
  operatorsAliases: false
});

const User = sequelize.define('user', {
  username: Sequelize.STRING,
  birthday: Sequelize.DATE
});

sequelize.sync()
  .then(() => User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20)
  }))
  .then(jane => {
    console.log(jane.toJSON());
  });
```

请通过 [Getting started - 入门](./book/getting-started.md) 来学习更多相关内容。 如果你想要学习 Sequelize API 请通过 [API Reference](http://docs.sequelizejs.com/identifiers) (英文)。