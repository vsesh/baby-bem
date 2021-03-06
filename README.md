# baby-bem
<img src="bem.png" align="right" />
In this project you can see example of using our tools and approaches.

## Requirements
  * Minimal knowledge about [BEM](http://bem.info/)
  * [nodejs](http://nodejs.org/) >= 0.10.0
  * [npm](http://npmjs.org) >= 1.2.0

## Quick start
```
bash <(curl -s https://raw.githubusercontent.com/baby-loris/baby-bem/master/get-a-pet.sh)
cd <YOUR_PROJECT_NAME>
npm install
SOCKET=8080 npm start
```
Then open the link in your [favorite browser](http://browser.yandex.com/):
```
http://localhost:8080/
```

**Note.** The application uses socket `/tmp/{{dirname}}-{{username}}.socket` by default. Don't forget set up your nginx config properly.

## What's inside?

### Features
  * [Static code analyser and codestyle checking with jsint and jscs](#static-code-analyser-and-codestyle-checking)
  * [Unit tests with mocha and phantomjs](#run-tests)
  * Using [git hooks](http://github.com/tarmolov/git-hooks) to lint your code and run tests before each commit

### Methodologies, libraries, and frameworks
  * [BEM](http://bem.info/) — a Block-Element-Modifier methodology for developing frontend
  * [bh](https://github.com/enb-make/bh) — a templates engine for BEM methodology
  * [ym](https://github.com/ymaps/modules) — a modules system
  * [express](http://expressjs.com/) — a web application framework for node
  * [vow](https://github.com/dfilatov/jspromise) — the fastest Promise/A+ implementation

### Tools
  * [enb](http://enb-make.info) — the fastest builder for BEM projects
  * [jshint](https://github.com/jshint/jshint) — a tool to detect errors and potential problems in JavaScript code
  * [jscs](https://github.com/mdevils/node-jscs) — a code style checker for javascript
  * [git-hooks](https://github.com/icefox/git-hooks) — a tool for git hooks managment
  * [mocha](http://visionmedia.github.io/mocha/) + [chai](http://chaijs.com/) + [sinon](http://sinonjs.org/) + [phantomjs](http://phantomjs.org/) — testing client javascript

## How it works

### Project structure
```
.enb                ENB config for building project
.git-hooks          Git hooks
configs             Project configs
client              Client-side code
client/common       Common blocks
client/demo         Demo blocks
pages               Pages
tests               Tests
tests/client        Client tests
tests/server        Server tests
```

## How to develop?
### Remove demo data
Remove demo level from file system.
```
rm -rf client/demo
```
and from `.enb/make.js`.

### Build project and run enb server
```
npm start
```
Use `SOCKET` environment variable to change default SOCKET. For example, to run on port `8080` you should
```
SOCKET=8080 npm start
```

### Static code analyser and codestyle checking
```
npm run lint
```

### Run tests
Client-side tests:
```
npm run test-client
```
or run `npm start`, then open in your [favorite browser](http://browser.yandex.com/):
```
http://localhost:8080/tests/client/index.html
```

Server-side tests:
```
npm run test-server
```

Run all tests:
```
npm test
```

## Contribution
  * [Codestyle](https://github.com/yandex/codestyle/blob/master/javascript.md)
