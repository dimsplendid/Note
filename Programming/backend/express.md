---
date updated: '2021-08-24T11:27:09+08:00'

---

# express

[[Nodejs]]

## route

The route is the path follow address. Just like the hyperlink of html file. express uisng route to maintain the serve of sites

```javascript
import express from 'express'

const app = express()

app.get('/test', (req, res) => {
	res.send("Route hit /test")
})

app.listen(3000, () => {
	console.log('Server is running on port: 3000')
})
```

For example, using the code above and type `[address]/test`, you can get `Route hit /test` on the site.

## router

As usual, writing all the things in one file is hard to read and maintain. `express` has a convenient function that can make a **sub-app**, and using it later in the main server `app.js`
```javascript
// routes/test.js
import { Router } from 'express'

const router = Router()
// then using it just like app
// like:
router.get('/test', (req, res) => {
	res.send('Route hit /test')
})

export { router as test}
```
```javascript
// app.js
import express from 'express'
import { test } from './routes/test'

const app = express()
app.use(test)

app.listen(3000, () => {
	console.log('Server is running on port: 3000')
})
```
You can get the same result from 1st example.
## middleware

## writing in [[typescript]]
See [[express_ts]]
