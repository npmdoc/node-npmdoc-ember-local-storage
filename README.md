# api documentation for  [ember-local-storage (v1.3.6)](https://github.com/funkensturm/ember-local-storage#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-ember-local-storage.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-ember-local-storage) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-ember-local-storage.svg)](https://travis-ci.org/npmdoc/node-npmdoc-ember-local-storage)
#### The addon provides an ember-data adapter and a storageFor computed property that persists the changes to localStorage or sessionStorage.

[![NPM](https://nodei.co/npm/ember-local-storage.png?downloads=true)](https://www.npmjs.com/package/ember-local-storage)

[![apidoc](https://npmdoc.github.io/node-npmdoc-ember-local-storage/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-ember-local-storage_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-ember-local-storage/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-ember-local-storage/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-ember-local-storage/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Manuel Wiedenmann"
    },
    "bugs": {
        "url": "https://github.com/funkensturm/ember-local-storage/issues"
    },
    "dependencies": {
        "broccoli-stew": "^1.4.0",
        "ember-cli-babel": "^5.2.1",
        "ember-cli-string-utils": "^1.0.0",
        "ember-cli-version-checker": "^1.1.7",
        "ember-getowner-polyfill": "^1.1.1"
    },
    "description": "The addon provides an ember-data adapter and a storageFor computed property that persists the changes to localStorage or sessionStorage.",
    "devDependencies": {
        "broccoli-asset-rev": "^2.5.0",
        "ember-ajax": "^2.5.2",
        "ember-cli": "^2.11.1",
        "ember-cli-app-version": "^2.0.0",
        "ember-cli-dependency-checker": "^1.3.0",
        "ember-cli-github-pages": "0.1.2",
        "ember-cli-htmlbars": "^1.1.1",
        "ember-cli-htmlbars-inline-precompile": "^0.3.6",
        "ember-cli-inject-live-reload": "^1.4.1",
        "ember-cli-inuitcss": "0.1.2",
        "ember-cli-jshint": "^2.0.1",
        "ember-cli-qunit": "^3.0.2",
        "ember-cli-release": "^0.2.9",
        "ember-cli-sass": "6.1.0",
        "ember-cli-shims": "^1.0.2",
        "ember-cli-sri": "^2.1.0",
        "ember-cli-test-loader": "^1.1.0",
        "ember-cli-uglify": "^1.2.0",
        "ember-data": "^2.11.0",
        "ember-disable-prototype-extensions": "^1.1.0",
        "ember-export-application-global": "^1.1.1",
        "ember-load-initializers": "^0.6.3",
        "ember-one-way-controls": "2.0.0",
        "ember-resolver": "^2.1.0",
        "ember-source": "~2.11.0",
        "loader.js": "^4.1.0"
    },
    "directories": {
        "doc": "doc",
        "test": "tests"
    },
    "dist": {
        "shasum": "98adf5bf69a7eeda77a6ef957ff480f587245fe5",
        "tarball": "https://registry.npmjs.org/ember-local-storage/-/ember-local-storage-1.3.6.tgz"
    },
    "ember-addon": {
        "configPath": "tests/dummy/config"
    },
    "engines": {
        "node": ">= 4"
    },
    "gitHead": "e283378e63a6e22e60b0faf57521c4ff3f33418c",
    "homepage": "https://github.com/funkensturm/ember-local-storage#readme",
    "keywords": [
        "ember-addon",
        "localStorage",
        "sessionStorage",
        "local-storage",
        "local-storage array",
        "local-storage object",
        "session-storage",
        "session-storage array",
        "session-storage object",
        "localStorage adapter",
        "local-storage adapter"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "fsmanuel",
            "email": "manuel@funkensturm.de"
        }
    ],
    "name": "ember-local-storage",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/funkensturm/ember-local-storage.git"
    },
    "scripts": {
        "build": "ember build",
        "start": "ember server",
        "test": "ember try:each"
    },
    "version": "1.3.6"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module ember-local-storage](#apidoc.module.ember-local-storage)
1.  [function <span class="apidocSignatureSpan">ember-local-storage.</span>included (app)](#apidoc.element.ember-local-storage.included)
1.  [function <span class="apidocSignatureSpan">ember-local-storage.</span>treeForAddon (tree)](#apidoc.element.ember-local-storage.treeForAddon)
1.  [function <span class="apidocSignatureSpan">ember-local-storage.</span>treeForApp (tree)](#apidoc.element.ember-local-storage.treeForApp)
1.  string <span class="apidocSignatureSpan">ember-local-storage.</span>name



# <a name="apidoc.module.ember-local-storage"></a>[module ember-local-storage](#apidoc.module.ember-local-storage)

#### <a name="apidoc.element.ember-local-storage.included"></a>[function <span class="apidocSignatureSpan">ember-local-storage.</span>included (app)](#apidoc.element.ember-local-storage.included)
- description and source-code
```javascript
function included(app) {
  // determine if ember-data is present
  var checker = new VersionChecker(this);
  var bowerDep = checker.for('ember-data', 'bower');
  var npmDep = checker.for('ember-data', 'npm');

  if (
    (
      bowerDep.version && (
        bowerDep.satisfies('>= 1.13.0') ||
        bowerDep.satisfies('>= 2.0.0') ||
        bowerDep.gt('2.0.0')
      )
    ) ||
    (
      npmDep.version  && (
        npmDep.satisfies('>= 1.13.0') ||
        npmDep.satisfies('>= 2.0.0') ||
        npmDep.gt('2.0.0')
      )
    )
  ) {
    this.hasEmberData = true;
  }

  // determin if saveAs and Blob should be imported
  var projectConfig = this.project.config(app.env);

  if (projectConfig) {
    var options = projectConfig['ember-local-storage'] || {};

    if (options.fileExport && this.hasEmberData) {
      app.import('vendor/save-as.js');
      app.import(app.bowerDirectory + '/blob-polyfill/Blob.js');
    }
  }

  this._super.included.apply(this, arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.ember-local-storage.treeForAddon"></a>[function <span class="apidocSignatureSpan">ember-local-storage.</span>treeForAddon (tree)](#apidoc.element.ember-local-storage.treeForAddon)
- description and source-code
```javascript
treeForAddon = function (tree) {
  if (!this.hasEmberData) {
    [
      'adapters/adapter.js',
      'adapters/base.js',
      'adapters/local.js',
      'adapters/session.js',
      'initializers/local-storage-adapter.js',
      'mixins/adapters/import-export.js',
      'serializers/serializer.js'
    ].forEach(function(file) {
      tree = stew.rm(tree, file);
    });
  }

  return this._super.treeForAddon.call(this, tree);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.ember-local-storage.treeForApp"></a>[function <span class="apidocSignatureSpan">ember-local-storage.</span>treeForApp (tree)](#apidoc.element.ember-local-storage.treeForApp)
- description and source-code
```javascript
treeForApp = function (tree) {
  if (!this.hasEmberData) {
    [
      'initializers/local-storage-adapter.js'
    ].forEach(function(file) {
      tree = stew.rm(tree, file);
    });
  }

  return tree;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
