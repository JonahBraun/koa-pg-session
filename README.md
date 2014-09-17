koa-mysql-session
=================
this is an adpatation of the logic from the connect mysql-session-store (https://github.com/sugendran/mysql-session-store) to koa-generic-session (https://github.com/koajs/generic-session).


Usage
=================
```js
const koa = require('koa')
    , session = require('koa-generic-session')
    , MysqlStore = require('koa-mysql-session')
    , app = koa() ;

const THIRTY_MINTUES = 30 * 60 * 1000;

app.keys = ['your-session-secret']
app.use(session({
        store: new MysqlStore(config.db),
        rolling: true,
        cookie: {
            maxage:THIRTY_MINTUES
        }
}))
```