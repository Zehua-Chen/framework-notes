# Event Handlers

When building with webpack, functions would be put into modules, causing
HTML elements to not be able to find them.

To solve this issue

```js
window.func = function() {
  console.log("hello world")
}
```
