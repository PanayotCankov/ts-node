# TypeScript Node

[![NPM version][npm-image]][npm-url]
[![NPM downloads][downloads-image]][downloads-url]
[![Build status][travis-image]][travis-url]
[![Test coverage][coveralls-image]][coveralls-url]

> TypeScript execution environment and REPL for node. **Works with `typescript@>=1.5`**.

## Installation

```sh
npm install -g ts-node

# Install a TypeScript compiler (requires `typescript` by default).
npm install -g typescript
```

## Features

* Execute TypeScript files with node
* Interactive REPL
* Execute (and print) TypeScript through the CLI
* Uses source maps
* Loads from `tsconfig.json`

## Usage

```sh
# Execute a script as you world normally with `node`.
ts-node script.ts

# Starts the TypeScript REPL.
ts-node

# Execute code with TypeScript.
ts-node -e 'console.log("Hello, world!")'

# Execute, and print, code with TypeScript.
ts-node -p '"Hello, world!"'

# Pipe scripts to execute with TypeScript.
echo "console.log('Hello, world!')" | ts-node
```

![TypeScript REPL](https://github.com/TypeStrong/ts-node/raw/master/screenshot.png)

### Mocha

```sh
mocha --require ts-node/register [...args]
```

### Tape

```sh
ts-node node_modules/tape/bin/tape [...args]
```

### Gulp

```sh
# Just create a `gulpfile.ts` and run `gulp`.
gulp
```

### Loading `tsconfig.json`

**Typescript Node** uses `tsconfig.json` automatically, use `-n` to skip loading `tsconfig.json`.

### Configuration Options

You can set options by passing them in before the script.

```sh
ts-node --compiler ntypescript --project src --ignoreWarnings 2304 hello-world.ts
```

* **--project, -P** Location to resolve `tsconfig.json` from (also `process.env.TS_NODE_PROJECT`)
* **--noProject, -n** Disable loading `tsconfig.json` (also `process.env.TS_NODE_NO_PROJECT`)
* **--compiler, -c** Use a custom, require-able TypeScript compiler compatible with `typescript@>=1.5.0-alpha` (also `process.env.TS_NODE_COMPILER`)
* **--ignoreWarnings, -i** Set an array of TypeScript diagnostic codes to ignore (also `process.env.TS_NODE_IGNORE_WARNINGS`)
* **--disableWarnings, -d** Ignore all TypeScript errors (also `process.env.TS_NODE_DISABLE_WARNINGS`)
* **--compilerOptions, -o** Set compiler options using JSON (E.g. `--compilerOptions '{"target":"es6"}'`) (also `process.env.TS_NODE_COMPILER_OPTIONS`)
* **--fast, -f** Use TypeScript's `transpileModule` mode (no type checking, but faster compilation) (also `process.env.TS_NODE_FAST`)

### Programmatic Usage

```js
require('ts-node').register({ /* options */ })

// Or using the shortcut file.
require('ts-node/register')
```

## License

MIT

[npm-image]: https://img.shields.io/npm/v/ts-node.svg?style=flat
[npm-url]: https://npmjs.org/package/ts-node
[downloads-image]: https://img.shields.io/npm/dm/ts-node.svg?style=flat
[downloads-url]: https://npmjs.org/package/ts-node
[travis-image]: https://img.shields.io/travis/TypeStrong/ts-node.svg?style=flat
[travis-url]: https://travis-ci.org/TypeStrong/ts-node
[coveralls-image]: https://img.shields.io/coveralls/TypeStrong/ts-node.svg?style=flat
[coveralls-url]: https://coveralls.io/r/TypeStrong/ts-node?branch=master
