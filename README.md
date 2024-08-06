# nwm-type-declaration-example
Type Declaration Example

The below example shows how to use mjs and mts files.

# Creating .d.ts file


## Description

This project has a src/math.mjs file

```js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}
```

The src/math.d.mts file is a declaration file which can be generated using the below command
```bash
npx -p typescript tsc src/*.mjs --declaration --allowJs --emitDeclarationOnly --outDir types/
```

Declaration file sample `math.d.ts`
```js
export declare function add(a: number, b: number): number;
export declare function subtract(a: number, b: number): number;
```

## Installation

To install the dependencies, run the following command:

```bash
npm i
```

## Run

To run src/test.js
```bash
node "./src/test.js"
```

Expected output:
```
Hello World!
add(1, 2): 3
subtract(1, 2): -1
multiply(1, 2): 2
div(1, 2): 2.5
```

To run src/use-math.ts

```bash
node --trace-warnings --import 'data:text/javascript,import { register } from "node:module"; import { pathToFileURL } from "node:url"; register("ts-node/esm", pathToFileURL("./"));' ./src/use-math.ts

```

Expected output
```
add = 3
diff = 8
```
