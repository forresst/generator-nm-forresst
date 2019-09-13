# <%= repoName %>

<%= repoName %> : <%= moduleDescription %>

[![Travis Build Status](https://travis-ci.org/<%= githubUsername %>/<%= repoName %>.svg?branch=master)](https://travis-ci.org/<%= githubUsername %>/<%= repoName %>)
[![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/4movr98t9uephfyg?svg=true)](https://ci.appveyor.com/project/<%= githubUsername %>/<%= repoName %>)
<% if (coveralls) { %> [![Coverage Status](https://coveralls.io/repos/github/<%= githubUsername %>/<%= repoName %>/badge.svg)](https://coveralls.io/github/<%= githubUsername %>/<%= repoName %>)<% } %>

[![version](https://img.shields.io/npm/v/<%= repoName %>.svg?style=flat-square)](https://www.npmjs.com/package/<%= repoName %>)
[![node-version](https://img.shields.io/badge/node-%3E%3D%208.0-orange.svg?style=flat-square)](https://nodejs.org)
[![downloads](https://img.shields.io/npm/dm/<%= repoName %>.svg?style=flat-square)](http://npm-stat.com/charts.html?package=<%= repoName %>)

[![MIT License](https://img.shields.io/npm/l/<%= repoName %>.svg?style=flat-square)](https://github.com/<%= githubUsername %>/<%= repoName %>/blob/master/license)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Code of Conduct](https://img.shields.io/badge/code%20of-conduct-ff69b4.svg?style=flat-square)](https://github.com/<%= githubUsername %>/<%= repoName %>/blob/master/CODE_OF_CONDUCT.md)
[![XO code style](https://img.shields.io/badge/code_style-XO-5ed9c7.svg)](https://github.com/xojs/xo)

[![Watch on GitHub](https://img.shields.io/github/watchers/<%= githubUsername %>/<%= repoName %>.svg?style=social)](https://github.com/<%= githubUsername %>/<%= repoName %>/watchers)
[![Star on GitHub](https://img.shields.io/github/stars/<%= githubUsername %>/<%= repoName %>.svg?style=social)](https://github.com/<%= githubUsername %>/<%= repoName %>/stargazers)

## Table of Contents

<!-- ⛔️ AUTO-GENERATED-CONTENT:START (TOC) -->

<!-- ⛔️ AUTO-GENERATED-CONTENT:END -->

## Install

This module is distributed via [npm](https://www.npmjs.com/) which is bundled with [node](https://nodejs.org) and should be installed as one of your project's `devDependencies`:

```console
npm install --save-dev <%= moduleName %>
```

## Usage

```js
const <%= camelModuleName %> = require('<%= moduleName %>');

<%= camelModuleName %>('unicorns');
//=> 'unicorns & rainbows'
```

## API

### <%= camelModuleName %>.foo(input)

Parse the content of the string. Returns a `object` with the metadata (key/value pairs).

#### input

Type: `string`

The string to parse.

#### return

Type: `object`

The object with the metadata as key\value pairs.

> Note: If the string does not contain metadata, the function returns an empty object.

#### Example

`index.js`:

> ```js
>
> <%= camelModuleName %> = require('<%= moduleName %>');
>
> const inputString = `
> [a]: # (1)
> [b]: # (Hello)
>
> # Doc
>
> Hello world
> `;
>
> console.log(<%= camelModuleName %>.foo(inputString));
> //=> { a: '1', b: 'Hello' }
> ```

### <%= camelModuleName %>.bar(input, objectAfter)

Add/change/remove the content of the `input` string with the object `objectAfter`. Returns a `string` with the modified content.

> Notes:
>
> - If a key does not exist in the `input` string and exists in object `objectAfter`, the key/value pair is appended to the content with the value of `objectAfter`.
> - If a key exists in the `input` string and exists in object `objectAfter` and the value is changed, the key/value pair is changed in the content with the value of `objectAfter`.
> - If a key exists in the `input` string and exists in object `objectAfter` and the value is not changed, the content is not changed.
> - If a key exists in the `input` string but does not exist in object `objectAfter`, the key/value pair is removed.

#### input

Type: `string`

The string to stringify.

#### objectAfter

Type: `object`

The object with all metadata as key\value pairs.

#### return

Type: `string`

The string with the content changed.

#### Example

`index.js`:

> ```js
>
> <%= camelModuleName %> = require('<%= moduleName %>');
>
> const inputString = `
> [a]: # (1)
> [b]: # (Hello)
> [c]: # (3)
>
> # Doc
>
> Hello world
> `;
>
> console.log(<%= camelModuleName %>.bar(inputString, { a: '1', b: 'World', d: '4' }));
> //=> `
> // [d]: # (4)
> // [a]: # (1)
> // [b]: # (World)
> //
> // # Doc
> //
> // Hello world
> // `
> ```
