# aws-workshop

This workshop is based on [The Good Parts of AWS](https://gum.co/aws-good-parts).

## Installation

Install [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [npm](https://www.npmjs.com/get-npm).

## Getting Started

Create a new directory, initialize git and npm.

```shell script

$ mkdir aws-workshop && cd aws-workshop
$ git init
$ npm init -y

```

Create a simple `server.js`:

```js

const {hostname} = require('os');
const http = require('http');
const message = 'Hello World\n';
const port = 8080;

const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end(message);
});

server.listen(port, hostname, () => {
    console.log(`Server running at http://${hostname()}:${port}/`);
});

```

Use `node` to execute `server.js`.

```shell script

$ node server.js

```

Open a new terminal and test:

```shell script

$ curl localhost:8080

```

Update `package.json` with `pm2` dependency.

```text

{
  "name": "aws-workshop",
  "version": "1.0.0",
  "description": "Foobar is a Python library for dealing with word pluralization.",
  "main": "server.js",
  "scripts": {
    "start": "node ./node_modules/pm2/bin/pm2 start ./server.js --name hello_aws --log ../logs/app.log ",
    "stop": "node ./node_modules/pm2/bin/pm2 stop hello_aws"
  },
  "dependencies": {
    "pm2": "^4.2.0"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/russomi-labs/aws-workshop.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/russomi-labs/aws-workshop/issues"
  },
  "homepage": "https://github.com/russomi-labs/aws-workshop#readme"
}


```

Run `npm install` to install the dependency.

```shell script

$ npm install

```

Create the logs directory:

```shell script

$ mkdir ../logs

```

Issue `npm start` and test.

```shell script

$ npm start
$ curl localhost:8080

```



## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
