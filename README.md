# koa-history-api-fallback-middleware

## Installation
```bash
npm i -S koa-history-api-fallback-middleware
```
or
```bash
npm i -D koa-history-api-fallback-middleware
```

## Example
```js
const path = require('path')
const Koa = require('koa')
const app = new Koa()

const historyMiddleware = require('koa-history-api-fallback-middleware')({
  rewrites: [{
    from: /^\/lvchao\/view\/*/,
    // to: function({ parsedUrl, match, req }) {
    //   return '/static/index.html'
    // },
    to: '/static/index.html'
  }]
})

app.use(historyMiddleware)
app.use(require('koa-static')(path.resolve(process.cwd(), './public')))
```

## more
- see [connect-history-api-fallback](https://www.npmjs.com/package/connect-history-api-fallback) know more about
- this module don't suport options.index config