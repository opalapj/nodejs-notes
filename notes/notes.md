# Internals

## Packages

A package is a file or directory that is described by a `package.json` file.
A package must contain a `package.json` file in order to be published to the
`npm` registry.

More:
- https://docs.npmjs.com/about-packages-and-modules#about-packages

## Modules

A module is any file or directory in the `node_modules` directory that can be
loaded by the `Node.js` `require()` function.

To be loaded by the `Node.js` `require()` function, a module must be one of the
following:

- a folder with a `package.json` file containing a `main` field,
- a `JavaScript` file.

> Since modules are not required to have a `package.json` file, not all modules
are packages. Only modules that have a `package.json` file are also packages.

In the context of a Node program, the module is also the thing that was loaded
from a file. For example, in the following program:

```js
var req = require('request')
```

The `req` variable refers to the `request` module returned by the `require()`
function.

More:
- https://docs.npmjs.com/about-packages-and-modules#about-modules

# Software packaging

Packages are the idiomatic way to package software in `Node.js`.

## `npm`

`npm` is the world's largest software registry. Open source developers from
every continent use `npm` to share and borrow packages, and many organizations
use `npm` to manage private development as well.

Useful commnads for non-`js` developers:

- `npm config edit --location project` - create `.npmrc` for project
- `npm install` - install a package and any packages that it depends on, works
only in a package directory with `package.json` file
- `npm install <package>` - install a package and any packages that it depends
on
- `npx <package>` - run package locally installed only
- `npm exec <package>` - alternative for above
- `npm uninstall <package>` - uninstall a package and any packages that it
depends on

### Folders structures used by `npm` (local vs global)

More:
- https://docs.npmjs.com/cli/v11/configuring-npm/folders

## `package.json`

A `package.json` file:

- lists the packages your project depends on,
- specifies versions of a package that your project can use using semantic
versioning rules,
- makes your build reproducible, and therefore easier to share with other
developers.

Useful fields for non-`js` developers:

- `dependencies` 

    More:
    - https://docs.npmjs.com/cli/v11/configuring-npm/package-json#dependencies

- `engines` - specify the version of node

    More:
    - https://docs.npmjs.com/cli/v11/configuring-npm/package-json#engines

    > Unless the user has set the `engine-strict` config flag, this field is
    advisory only and will only produce warnings when your package is installed
    as a dependency.

More:
- https://docs.npmjs.com/creating-a-package-json-file
- https://docs.npmjs.com/cli/v11/configuring-npm/package-json

## `.npmrc`

`npm` configuration files.

Run `npm config edit --location project` in project root to create `.npmrc`.

More:
- https://docs.npmjs.com/cli/v11/configuring-npm/npmrc

## `npx`

Run package locally installed only.

More:
- https://docs.npmjs.com/cli/v11/commands/npx

## Versioning

More:
- https://docs.npmjs.com/cli/v11/configuring-npm/package-json#dependencies
