# Scalefast editor tools

[![npm version](https://badge.fury.io/js/editor-tools-scalefast.svg)](https://badge.fury.io/js/editor-tools-scalefast)

Tools that help developing code in Scalefast and are easy can be integrated in Sublime, VS Code, Atom and Vim in Windows and Linux.

In this first versions it only includes the eslint linter.

## Installation

```sh
npx install-peerdeps editor-tools-scalefast --global #global installation (requires privileges: sudo or administrator terminal)
npx install-peerdeps editor-tools-scalefast # local installation
```

We use [install-peerdeps](https://www.npmjs.com/package/install-peerdeps), this way eslint and its plugins are installed like normal packages instead of dependencies of our package, some IDEs extensions depend on eslint being installed this way.

It also simplifies having multiple packages and configurations globally installed.

## Global installation

We recommend installing this package globally to make it easier for IDEs extensions to find eslint but it's possible to install it locally and point the extension to the local eslint version avoiding potential conflicts.

## Local installation

If you are interested in a local installation it may be more helpful to add the peer dependencies of this package to your own project package.json, many extensions and tools support per project installations out of the box.

A local installation is also necessary to automatically run these tools before committing or pushing code to ensure the environment is reproducible and identical for all developers.

## Updates

To update the editor tools run the same installation command

```sh
npx install-peerdeps editor-tools-





--global #global installation (requires privileges: sudo or administrator terminal)
npx install-peerdeps editor-tools-scalefast # local installation
```

It's also possible to update each tool separately running `npm update <package-name>` but the npx command will ensure that new dependencies are installed.

## Test editor configuration

### VS Code

Install the ESLint (dbaeumer.vscode-eslint) extension.

### Sublime

__NOT TESTED YET__ Install the `SublimeLinter` and `SublimeLinter-eslint` extensions.

### Atom

Install the `linter` and `linter-eslint` package.

### Vim

Should use [syntastic](https://github.com/vim-syntastic/syntastic) but not tested yet

### PhpStorm

__NOT TESTED YET__

## Usage

### Eslint

To use this package in a project we need to create a [eslint configuration file](https://eslint.org/docs/user-guide/configuring) in the project path or point our IDE extension to the configuration file.

We include a sample .eslintrc configuration file in root of this package. Our configuration extends [eslint-config-scalefast](https://www.npmjs.com/package/eslint-config-scalefast) and will inherit all the rules defined in that package. Specific .eslintrc files per project are desirable so certain rules can be adapted to each project.

### Stylelint

## Contributing

This package aims to automatize installing and configuring any npm tool we want to integrate with different IDEs. This should simplify using editor extensions and having a unified configuration.

It's important that the tools can be adapted to different projects, the preferred way to achieve this is to include standard linter configuration (i.e. .eslintrc) files in each repository. This allows us to grant exceptions to general rules for specific projects and set specific settings and rules that don't apply to all the code. These files must extend our generic configuration using the extend features provided by the different linters.

A default configuration file for each tool is included in this package root directory, these files should be used as a template to create each project configurations and can be used directly for projects that don't have a specific configuration yet. Most editor extensions allow to specify a hardcoded configuration file instead of auto-detecting the project specific file.

To add new tools to this package it's recommended to find out if they have the following set of features:

* Can be integrated with our CI and development machines
* Have good support across different editors requiring minimal manual configuration
* Are extensible and can be adapted to our use case
