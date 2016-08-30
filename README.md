# Essential JavaScript Interview Questions

### 1. Explain the result of output:

```javascript
(function test () {
	console.log(
		{}.constructor === arguments.constructor,
		[].constructor === arguments.constructor
	);
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
		Function === Object.constructor,
		Function === Number.constructor,
		Function === Function.constructor,
		Function === Window.constructor,
		Function === Function.prototype.constructor,
		Object === Object.prototype.constructor,
		Number === Number.prototype.constructor,
		Array === Array.prototype.constructor,
		Window === Window.prototype.constructor
	);
})();
```

### 6. Explain the result of output:

```javascript
(function test() {
	console.log(
		typeof Object.prototype,
		typeof String.prototype,
		typeof RegExp.prototype,
		typeof Function.prototype
	);
})();
```

```javascript
(function test() {
	console.log(
		typeof undefined,
		typeof typeof undefined,
		typeof null,
		typeof 1 / null,
		typeof [],
		typeof {},
		typeof document
	);
})();
```

### 7. Explain the result of output:

```javascript
(function test() {
	var fn = function () {
		return this * 2;
	};

	console.log(fn.apply(undefined));
	console.log(fn.apply(null));
	console.log(fn.apply(1));
})();
```

```javascript
(function test() {
	'use strict';
	var fn = function () {
		return this * 2;
	};

	console.log(fn.apply(undefined));
	console.log(fn.apply(null));
	console.log(fn.apply(1));
})();
```

### 8. Explain the result of output:

```javascript
(function test() {
	console.log(
		Object.prototype.toString.call([]),
		Object.prototype.toString.call({}),
		Object.prototype.toString.call(Window),
		(16).toString(16),
		(true).toString(16),
		(false).toString(16)
	);
})();
```

### 9. Explain the result of output:

```javascript
(function test() {
	var sum = function (a, b) {
		return a + b;
	};
	console.log(typeof sum.call.apply);
	console.log(sum.call.apply(null, [1, 2]));
})();
```

### 10. Explain the result of output:

```javascript
(function test() {
	console.log(void (p = 1 / ""), p);
})();
```

### 11. Explain the result of output:

```javascript
(function test() {
	(function () {
		a = 1;
		var a = 2;
	})();
	console.log(a);
})();
```

```javascript
(function test() {
	var a = 1;
	function test() {
		if (!a) {
			var a = 10;
		}
		console.log(a);
	}
	test();
	console.log(a);
})();
```

### 12. Which a variant is preferable and why?

```javascript
(function test() {
	console.log(error !== undefined && error.x);
})();
```

```javascript
(function test() {
	console.log(typeof error !== 'undefined' && error.x);
})();
```