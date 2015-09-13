# Tern Emacs/Reactjs problem

## To install
```
npm install
```

## To replicate the problem
Open `src/main.js` in emacs, move the point to the end of the require statement (after the closing paren), and type `M-.` (tern-find-definition).

*Expected result:*

Tern should jump to file `src/MyComponent.js`.

*Actual result:*

Tern jumps to the react sourcecode (`ReactClass.js`).

The server debug looks like this:

```
Request: {
  "query": {
    "end": 44,
    "file": "main.js",
    "type": "definition",
    "variable": null
  }
}
Response: {
  "doc": "Legacy hook",
  "origin": "src/MyComponent.js",
  "start": 25936,
  "end": 27597,
  "file": "node_modules/react/lib/ReactClass.js",
  "contextOffset": 50,
  "context": "eateClass: function(spec) {\n    var Constructor = "
}
```
