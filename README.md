# vscode-apollo-relay

[![npm](https://img.shields.io/npm/v/vscode-apollo-relay.svg)](https://www.npmjs.com/package/vscode-apollo-relay)
[![build](https://img.shields.io/travis/relay-tools/vscode-apollo-relay/master.svg)](https://travis-ci.org/relay-tools/vscode-apollo-relay/builds)

Simple configuration of vscode-apollo for Relay projects.

[Changelog](https://github.com/relay-tools/vscode-apollo-relay/blob/master/CHANGELOG.md)

## Install

```sh
# using npm
npm install --save vscode-apollo-relay

# using yarn
yarn add vscode-apollo-relay
```

## Usage

In your `apollo.config.js` file:

```js
const { config } = require("vscode-apollo-relay").generateConfig()
module.exports = config
```

Or, if you don’t use `relay-config` yet and the default values don’t work for you:

```js
const path = require("path")
const { config, directivesFile, includesGlobPattern } = require("vscode-apollo-relay").generateConfig()

module.exports = {
  ...config,
  service: {
    ...config.service,
    localSchemaFile: "./path/to/schema.graphql",
  },
  includes: [directivesFile, path.join("./path/to/source", includesGlobPattern)],
  excludes: ["./path/to/exclude"],
}
```

## Development

```sh
# lint
yarn run lint

# build
yarn run build

# test
yarn run test
```

## License

MIT © [Eloy Durán](https://github.com/alloy)