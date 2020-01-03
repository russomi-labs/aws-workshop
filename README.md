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

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
