## nodemon and express local import

* package.json
```sh
{
  "name": "nodeapp",
  "version": "1.0.0",
  "description": "",
  "main": "app.js",
  "scripts": {
    "start": "node ./nodemon/bin/nodemon.js app.js && exit 1"
  },
  "author": "s.m.amran",
  "license": "MIT"
}
```

* app.js
```js
const express = require('./express/index.js');

const app = express();
const port = 3000;

app.get('/', (req, res) => {
    console.log(req);
    res.send('Hello World!').end();
});

app.listen(port, () => console.log(`Example app listening on port ${port}!`) );
```

* ` npm start `
