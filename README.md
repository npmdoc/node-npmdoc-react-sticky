# api documentation for  [react-sticky (v5.0.5)](https://github.com/captivationsoftware/react-sticky)  [![npm package](https://img.shields.io/npm/v/npmdoc-react-sticky.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-react-sticky) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-react-sticky.svg)](https://travis-ci.org/npmdoc/node-npmdoc-react-sticky)
#### Sticky component for React

[![NPM](https://nodei.co/npm/react-sticky.png?downloads=true)](https://www.npmjs.com/package/react-sticky)

[![apidoc](https://npmdoc.github.io/node-npmdoc-react-sticky/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-react-sticky%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-react-sticky/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-react-sticky/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-react-sticky/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Captivation Software"
    },
    "bugs": {
        "url": "https://github.com/captivationsoftware/react-sticky/issues"
    },
    "dependencies": {},
    "description": "Sticky component for React",
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
    },
    "directories": {},
    "dist": {
        "shasum": "995871273f8a001fa4d462d3b96f381ee54b2649",
        "tarball": "https://registry.npmjs.org/react-sticky/-/react-sticky-5.0.5.tgz"
    },
    "gitHead": "10f61e98642c39ca890f5addb07ad1d040894b3c",
    "homepage": "https://github.com/captivationsoftware/react-sticky",
    "keywords": [
        "react-component",
        "React",
        "Sticky"
    ],
    "license": "MIT",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "dbarbalato",
            "email": "dbarbalato@gmail.com"
        }
    ],
    "name": "react-sticky",
    "optionalDependencies": {},
    "peerDependencies": {
        "react": "^0.14.0 || ^15.0.0",
        "react-dom": "^0.14.0 || ^15.0.0"
    },
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/captivationsoftware/react-sticky.git"
    },
    "scripts": {
        "build": "npm run transpile && npm run dist",
        "clean": "rimraf lib dist",
        "dist": "webpack lib/index.js dist/react-sticky.js --display-modules --progress && NODE_ENV=production webpack lib/index.js dist/react-sticky.min.js --display-modules --progress",
        "prepublish": "npm run clean && npm run build",
        "test": "mocha --compilers js:babel-core/register test/unit",
        "transpile": "babel src --loose --out-dir lib"
    },
    "version": "5.0.5"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module react-sticky](#apidoc.module.react-sticky)
1.  [function <span class="apidocSignatureSpan">react-sticky.</span>Channel (data)](#apidoc.element.react-sticky.Channel)
1.  [function <span class="apidocSignatureSpan">react-sticky.</span>Sticky (props)](#apidoc.element.react-sticky.Sticky)
1.  [function <span class="apidocSignatureSpan">react-sticky.</span>StickyContainer (props)](#apidoc.element.react-sticky.StickyContainer)
1.  [function <span class="apidocSignatureSpan">react-sticky.</span>default (props)](#apidoc.element.react-sticky.default)



# <a name="apidoc.module.react-sticky"></a>[module react-sticky](#apidoc.module.react-sticky)

#### <a name="apidoc.element.react-sticky.Channel"></a>[function <span class="apidocSignatureSpan">react-sticky.</span>Channel (data)](#apidoc.element.react-sticky.Channel)
- description and source-code
```javascript
function Channel(data) {
  _classCallCheck(this, Channel);

  var listeners = [];
  data = data || {};

  this.subscribe = function (fn) {
    listeners.push(fn);
  };

  this.unsubscribe = function (fn) {
    var idx = listeners.indexOf(fn);
    if (idx !== -1) listeners.splice(idx, 1);
  };

  this.update = function (fn) {
    if (fn) fn(data);
    listeners.forEach(function (l) {
      return l(data);
    });
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.react-sticky.Sticky"></a>[function <span class="apidocSignatureSpan">react-sticky.</span>Sticky (props)](#apidoc.element.react-sticky.Sticky)
- description and source-code
```javascript
function Sticky(props) {
  _classCallCheck(this, Sticky);

  var _this = _possibleConstructorReturn(this, Object.getPrototypeOf(Sticky).call(this, props));

  _this.updateContext = function (_ref) {
    var inherited = _ref.inherited;
    var node = _ref.node;

    _this.containerNode = node;
    _this.setState({
      containerOffset: inherited,
      distanceFromBottom: _this.getDistanceFromBottom()
    });
  };

  _this.recomputeState = function () {
    var isSticky = _this.isSticky();
    var height = _this.getHeight();
    var width = _this.getWidth();
    var xOffset = _this.getXOffset();
    var distanceFromBottom = _this.getDistanceFromBottom();
    var hasChanged = _this.state.isSticky !== isSticky;

    _this.setState({ isSticky: isSticky, height: height, width: width, xOffset: xOffset, distanceFromBottom: distanceFromBottom });

    if (hasChanged) {
      if (_this.channel) {
        _this.channel.update(function (data) {
          data.offset = isSticky ? _this.state.height : 0;
        });
      }

      _this.props.onStickyStateChange(isSticky);
    }
  };

  _this.state = {};
  return _this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.react-sticky.StickyContainer"></a>[function <span class="apidocSignatureSpan">react-sticky.</span>StickyContainer (props)](#apidoc.element.react-sticky.StickyContainer)
- description and source-code
```javascript
function Container(props) {
  _classCallCheck(this, Container);

  var _this = _possibleConstructorReturn(this, Object.getPrototypeOf(Container).call(this, props));

  _this.updateOffset = function (_ref) {
    var inherited = _ref.inherited;
    var offset = _ref.offset;

    _this.channel.update(function (data) {
      data.inherited = inherited + offset;
    });
  };

  _this.channel = new _channel2.default({ inherited: 0, offset: 0, node: null });
  return _this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.react-sticky.default"></a>[function <span class="apidocSignatureSpan">react-sticky.</span>default (props)](#apidoc.element.react-sticky.default)
- description and source-code
```javascript
function Sticky(props) {
  _classCallCheck(this, Sticky);

  var _this = _possibleConstructorReturn(this, Object.getPrototypeOf(Sticky).call(this, props));

  _this.updateContext = function (_ref) {
    var inherited = _ref.inherited;
    var node = _ref.node;

    _this.containerNode = node;
    _this.setState({
      containerOffset: inherited,
      distanceFromBottom: _this.getDistanceFromBottom()
    });
  };

  _this.recomputeState = function () {
    var isSticky = _this.isSticky();
    var height = _this.getHeight();
    var width = _this.getWidth();
    var xOffset = _this.getXOffset();
    var distanceFromBottom = _this.getDistanceFromBottom();
    var hasChanged = _this.state.isSticky !== isSticky;

    _this.setState({ isSticky: isSticky, height: height, width: width, xOffset: xOffset, distanceFromBottom: distanceFromBottom });

    if (hasChanged) {
      if (_this.channel) {
        _this.channel.update(function (data) {
          data.offset = isSticky ? _this.state.height : 0;
        });
      }

      _this.props.onStickyStateChange(isSticky);
    }
  };

  _this.state = {};
  return _this;
}
```
- example usage
```shell
...
    var offset = _ref.offset;

    _this.channel.update(function (data) {
      data.inherited = inherited + offset;
    });
  };

  _this.channel = new _channel2.default({ inherited: 0, offset: 0, node: null });
  return _this;
}

_createClass(Container, [{
  key: 'getChildContext',
  value: function getChildContext() {
    return { 'sticky-channel': this.channel };
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
