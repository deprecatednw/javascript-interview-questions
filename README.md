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
	console.log(arguments[0]);
})(100);
```

```javascript
(function test () {
    var arguments;
	console.log(arguments[0]);
})(200);
```

### 3. Explain the result of output:

```javascript
(function test() {
	console.log(
		function () {} instanceof Object,
		function () {} instanceof Function,
		Function instanceof Object,
		Object instanceof Function
	);
})();
```

### 4. Explain the result of output:

```javascript
(function test() {
	console.log(
		function () {}.apply.length
	);
})();
```

### 5. Explain the result of output:

```javascript
(function test() {
    console.log(
        Function === Function.prototype.constructor
    );
})();
```

### 6. Explain the result of output:

```javascript
(function test() {
	console.log(
		Object,
		Function,
		String,
		RegExp,
		typeof Object.prototype,
		typeof Function.prototype,
		typeof String.prototype,
		typeof RegExp.prototype
	);
})();
```