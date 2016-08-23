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
		Function === Function.prototype.constructor,
		Object === Object.prototype.constructor,
		Number === Number.prototype.constructor
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

### 7. Explain the result of output:

```javascript
(function () {
	var fn = function () {
		return this * 2;
	};

	console.log(fn.apply(undefined));
	console.log(fn.apply(null));
	console.log(fn.apply(1));
})();
```

```javascript
(function () {
    'use strict';
    var fn = function () {
        return this * 2;
    };

    console.log(fn.apply(undefined));
    console.log(fn.apply(null));
    console.log(fn.apply(1));
})();
```