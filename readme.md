# Perspective to_json Output Mismatch Reproduction

This repository demonstrates an issue in the [Perspective](https://github.com/finos/perspective) library where two views with identical configurations produce differing outputs when the `to_json` method is called within an `on_update` callback. The issue highlights an unexpected behavior during view updates.

## **Issue Description**

Given two views created with identical configurations and listening for updates, the `to_json` outputs are inconsistent. Specifically:

### **Expected Behavior**:

Both views should return identical `to_json` outputs.

```js
[
  {
    __ROW_PATH__: [],
    field: 200,
  },

  {
    __ROW_PATH__: [1733036764909],
    field: 100,
  },

  {
    __ROW_PATH__: [1733123175339],
    field: 100,
  },
];
```

### **Actual Behavior**:

One view produces the expected output, while the other returns an incorrect result with `null` values.

```js
[
  {
    __ROW_PATH__: [],
    field: null,
  },
];
```

## **Code Reproduction**

To reproduce the issue, clone this repository and open `index.html` in your browser.

### **Setup Instructions**

1. `git clone`
2. Run the code by opening index.html in a browser.
3. Check console and see the actual output is not expected
