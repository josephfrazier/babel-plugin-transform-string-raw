babel-plugin-transform-string-raw
---

<p align="right">
  <a href="https://npmjs.org/package/babel-plugin-transform-string-raw">
    <img src="https://img.shields.io/npm/v/babel-plugin-transform-string-raw.svg?style=flat-square">
  </a>
  <a href="https://travis-ci.org/josephfrazier/babel-plugin-transform-string-raw">
    <img src="http://img.shields.io/travis/josephfrazier/babel-plugin-transform-string-raw.svg?style=flat-square">
  </a>
  <a href="https://gemnasium.com/josephfrazier/babel-plugin-transform-string-raw">
    <img src="https://img.shields.io/gemnasium/josephfrazier/babel-plugin-transform-string-raw.svg?style=flat-square">
  </a>
</p>

Installation
---
```bash
npm install babel-plugin-transform-string-raw --save
```

replace `String.raw` with an [ponyfill function](https://github.com/59naga/string-raw).

Requirement
---
> https://github.com/59naga/babel-plugin-transform-array-from

Installation
---
```bash
npm install babel-plugin-transform-string-raw --save
```

Example
---

**In**

```js
String.raw`hoge${arg1}fuga${arg2}piyo`;
```

**Out**

```js
var _stringRaw = String.raw || function(){...};
_stringRaw`hoge${arg1}fuga${arg2}piyo`;
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["babel-plugin-transform-string-raw"]
}
```

### Via CLI

```bash
$ babel --plugins babel-plugin-transform-string-raw script.js
```

### Via Node API

```js
require("babel-core").transform("code", {
  plugins: ["babel-plugin-transform-string-raw"]
});
```

Development
---
Requirement global
* NodeJS v0.12.13
* Npm v3.7.1

```bash
git clone https://github.com/josephfrazier/babel-plugin-transform-string-raw
cd babel-plugin-transform-string-raw
npm install

npm test
```

License
---
MIT
