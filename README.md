# express-async-error-handler

I'm not sure why this doesn't exist already. Handles a

## Usage

```js
const asyncErrorHandler = require('express-async-error-handler')
const express = require('express')
const router = express.Router()

// Route
router.post('/hello', asyncErrorHandler(async function() {
  await thisWillThrowAnError()
}))

// Error handler
router.use(function(err, req, res, next) {
  res.status(err.status || 500)
})
```
