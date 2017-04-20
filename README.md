# npmdoc-react-sticky

#### api documentation for  [react-sticky (v5.0.8)](https://github.com/captivationsoftware/react-sticky)  [![npm package](https://img.shields.io/npm/v/npmdoc-react-sticky.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-react-sticky) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-react-sticky.svg)](https://travis-ci.org/npmdoc/node-npmdoc-react-sticky)

#### Sticky component for React

[![NPM](https://nodei.co/npm/react-sticky.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/react-sticky)

- [https://npmdoc.github.io/node-npmdoc-react-sticky/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-react-sticky/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-react-sticky/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-react-sticky/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-react-sticky/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-react-sticky/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "react-sticky",
    "version": "5.0.8",
    "description": "Sticky component for React",
    "main": "lib/index.js",
    "scripts": {
        "clean": "rimraf lib dist",
        "transpile": "babel src --loose --out-dir lib",
        "dist": "webpack lib/index.js dist/react-sticky.js --display-modules --progress && NODE_ENV=production webpack lib/index.js dist/react-sticky.min.js --display-modules --progress",
        "build": "npm run transpile && npm run dist",
        "prepublish": "npm run clean && npm run build",
        "test": "mocha --compilers js:babel-core/register test/unit"
    },
    "repository": {
        "type": "git",
        "url": "https://github.com/captivationsoftware/react-sticky"
    },
    "keywords": [
        "react-component",
        "React",
        "Sticky"
    ],
    "author": "Captivation Software",
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/captivationsoftware/react-sticky/issues"
    },
    "homepage": "https://github.com/captivationsoftware/react-sticky",
    "dependencies": {
        "prop-types": "^15.5.8"
    },
    "peerDependencies": {
        "react": "^0.14.0 || ^15.0.0",
        "react-dom": "^0.14.0 || ^15.0.0"
    },
    "devDependencies": {
        "babel-cli": "^6.6.0",
        "babel-core": "^6.6.0",
        "babel-plugin-add-module-exports": "^0.1.2",
        "babel-plugin-transform-object-assign": "^6.5.0",
        "babel-preset-es2015": "^6.5.0",
        "babel-preset-react": "^6.5.0",
        "babel-preset-stage-0": "^6.5.0",
        "chai": "^3.2.0",
        "jsdom": "8.0.4",
        "mocha": "^2.2.5",
        "react": "^0.14.0 || ^15.0.0",
        "react-addons-test-utils": "^0.14.0 || ^15.0.0",
        "react-dom": "^0.14.0 || ^15.0.0",
        "rimraf": "^2.5.2",
        "webpack": "^1.12.14"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
