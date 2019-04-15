So you want to use Gulp but you don't have anything installed. Let's get you set up.

First, you need to install [Homebrew](https://brew.sh/), a package manager for MacOS.

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then, you need to install [NodeJS](https://nodejs.org/en/), which will also install NPM, the Node Package Manager.

```bash
$ brew install node
```

Finally, with NPM installed, you need to globally install [Gulp](https://gulpjs.com/).

```bash
$ npm install gulp-cli -g
$ npm install gulp -D
```
