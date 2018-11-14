# Scalefast editor tools

[![npm version](https://badge.fury.io/js/editor-tools-scalefast.svg)](https://badge.fury.io/js/editor-tools-scalefast)

Tools that help developing code in Scalefast and are easy can be integrated in Sublime, VS Code, Atom and Vim in Windows and Linux.

In this first versions it only includes the eslint linter.

Installation:

```sh
npx install-peerdeps editor-tools-scalefast --global #global installation (requires privileges: sudo or administrator terminal)
npx install-peerdeps editor-tools-scalefast # local installation
```

We use [install-peerdeps](https://www.npmjs.com/package/install-peerdeps), this way eslint and its plugins are installed as normal packages as IDEs expect them to be installed.

It also simplifies having multiple packages and configurations globally installed.

## Global installation

We recommend installing this package globally to make it easier for IDEs extensions to find eslint but it's possible to install it locally and point the extension to the local eslint version avoiding potential conflicts.

## Local installation

If you are interested in a local installation it may be more helpful to add the peer dependencies of this package to your own project package.json, many extensions and tools support per project installations out of the box.

A local installation is also necessary to automatically run these tools before committing or pushing code to ensure the environment is reproducible and identical for all developers.

## Test editor configuration

### VS Code

Install the ESLint (dbaeumer.vscode-eslint) extension.

### Sublime

__NOT TESTED YET__ Install the `SublimeLinter` and `SublimeLinter-eslint` extensions.

### Atom

Install the `linter` and `linter-eslint` package.

### Vim

Should use [syntastic](https://github.com/vim-syntastic/syntastic) but not tested yet

### Usage

To use this package in a project we need to create a [eslint configuration file](https://eslint.org/docs/user-guide/configuring) in the project path or point our IDE extension to the configuration file.

We include a sample .eslintrc configuration file in root of this package. Our configuration extends [eslint-config-scalefast](https://www.npmjs.com/package/eslint-config-scalefast) and will inherit all the rules defined in that package. Specific .eslintrc files per project are desirable so certain rules can be adapted to each project.
