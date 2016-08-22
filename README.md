# Essential JavaScript Interview Questions

### 1. Explain the result of output:

```javascript
(function test () {
	console.log({}.constructor === arguments.constructor);
})();
```

### 2. Explain the result of output:

```javascript
(function test (arguments) {
	console.log(arguments);
})(2);
```