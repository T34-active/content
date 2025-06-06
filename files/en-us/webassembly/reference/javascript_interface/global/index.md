---
title: WebAssembly.Global
slug: WebAssembly/Reference/JavaScript_interface/Global
page-type: webassembly-interface
browser-compat: webassembly.api.Global
sidebar: webassemblysidebar
---

A **`WebAssembly.Global`** object represents a global variable instance, accessible from both JavaScript and importable/exportable across one or more [`WebAssembly.Module`](/en-US/docs/WebAssembly/Reference/JavaScript_interface/Module) instances. This allows dynamic linking of multiple modules.

## Constructor

- [`WebAssembly.Global()`](/en-US/docs/WebAssembly/Reference/JavaScript_interface/Global/Global)
  - : Creates a new `Global` object.

## Global instances

All `Global` instances inherit from the `Global()` constructor's prototype object — this can be modified to affect all `Global` instances.

### Instance properties

- `Global.prototype.constructor`
  - : Returns the function that created this object's instance. By default this is the [`WebAssembly.Global()`](/en-US/docs/WebAssembly/Reference/JavaScript_interface/Global/Global) constructor.
- `Global.prototype[Symbol.toStringTag]`
  - : The initial value of the [`[Symbol.toStringTag]`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag) property is the String value "WebAssembly.Global".
- `Global.prototype.value`
  - : The value contained inside the global variable — this can be used to directly set and get the global's value.

### Instance methods

- `Global.prototype.valueOf()`
  - : Old-style method that returns the value contained inside the global variable.

## Examples

### Creating a new Global instance

The following example shows a new global instance being created using the `WebAssembly.Global()` constructor. It is being defined as a mutable `i32` type, with a value of 0.

The value of the global is then changed, first to `42` using the `Global.value` property, and then to 43 using the `incGlobal()` function exported out of the `global.wasm` module (this adds 1 to whatever value is given to it and then returns the new value).

```js
const output = document.getElementById("output");

function assertEq(msg, got, expected) {
  const result =
    got === expected
      ? `SUCCESS! Got: ${got}\n`
      : `FAIL!\nGot: ${got}\nExpected: ${expected}\n`;
  output.innerText += `Testing ${msg}: ${result}`;
}

assertEq("WebAssembly.Global exists", typeof WebAssembly.Global, "function");

const global = new WebAssembly.Global({ value: "i32", mutable: true }, 0);

WebAssembly.instantiateStreaming(fetch("global.wasm"), { js: { global } }).then(
  ({ instance }) => {
    assertEq(
      "getting initial value from wasm",
      instance.exports.getGlobal(),
      0,
    );
    global.value = 42;
    assertEq(
      "getting JS-updated value from wasm",
      instance.exports.getGlobal(),
      42,
    );
    instance.exports.incGlobal();
    assertEq("getting wasm-updated value from JS", global.value, 43);
  },
);
```

> [!NOTE]
> You can see the example [running live on GitHub](https://mdn.github.io/webassembly-examples/js-api-examples/global.html); see also the [source code](https://github.com/mdn/webassembly-examples/blob/main/js-api-examples/global.html).

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [WebAssembly](/en-US/docs/WebAssembly) overview
- [WebAssembly concepts](/en-US/docs/WebAssembly/Guides/Concepts)
- [Using the WebAssembly JavaScript API](/en-US/docs/WebAssembly/Guides/Using_the_JavaScript_API)
- [Import/Export mutable globals proposal](https://github.com/WebAssembly/mutable-global/blob/master/proposals/mutable-global/Overview.md)
