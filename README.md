<h1 align="center">@openinf/util-md-table</h1>

<p align="center">Common Markdown table-related utilities</p>

<br />

<p align="center">
  <a href="https://www.npmjs.com/package/@openinf/util-md-table"><img src="https://img.shields.io/npm/v/@openinf/util-md-table?style=plastic" alt="view on npm" /></a>
  <img src="https://img.shields.io/github/languages/top/openinf/util-md-table?color=blue&style=plastic" />
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/github/license/openinf/util-md-table?color=blue&style=plastic" alt="License: MIT" /></a>
</p>

<br />

_The high-level goal of `@openinf/util-md-table` is to serve as a Node.js
package containing utilities for **common operations on Markdown tables**
allowing users to make use of them in new ways. As is the case with any
software project in continuous development, omissions and errors may exist, for
which contributions are welcome._

<br />

---

<br />

## Installation

`@openinf/util-md-table` runs on Node.js and is available via `npm`.

```shell
npm install @openinf/util-md-table
```

## Usage

```ts
import { mdTable2json } from '@openinf/util-md-table';

const sampleTable = [
'| Col1  | Col2  | Col3  | Col4  |',
'|:-----:|:-----:|:-----:|:-----:|',
'| one   | two   | three | four  |',
'| Fee   | Fie   | Foe   | Fum   |',
].join('\n');

const sampleTableObject = mdTbl2json(sampleTable, (v) => v.toLowerCase());

console.log(sampleTableObject);
```

```console
[
  { col1: 'one', col2: 'two', col3: 'three', col4: 'four' },
  { col1: 'fee', col2: 'fie', col3: 'foe', col4: 'fum' }
]
```

<br />

---

<br />

<a name="mdTbl2json"></a>

## mdTbl2json(mdTbl, cellTransform, attribCellTransform) ⇒ <code>Array.&lt;Object&gt;</code>
**Kind**: global function  

| Param | Type | Description |
| --- | --- | --- |
| mdTbl | <code>string</code> | A markdown table as a string. |
| cellTransform | <code>function</code> \| <code>undefined</code> | A function run on contents of each cell. |
| attribCellTransform | <code>function</code> \| <code>undefined</code> | A transform only for attribute cells. |


<br />

---

<br />

<p align="center">&copy; The OpenINF Authors</center></p>
<p align="center"><img height="32px" width="32px" src="https://raw.githubusercontent.com/openinf/openinf.github.io/live/logo.svg" /></p>
