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

```javascript
(function test() {
	function sum() {
		var sum = 0, i;
		for (i in arguments) {
			sum += i;
		}
		return sum;
	}

	console.log(sum(10, 20, 30, 40, 50));
})();
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

```javascript
(function test() {
	console.log(
		typeof Infinity,
		typeof NaN,
		typeof {null: null}.null,
		typeof {NaN: NaN}.NaN,
		typeof {Infinity: Infinity}.Infinity
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

```javascript
(function test() {
	(function () {
		var a = b = 3;
	})();

	console.log(
		typeof a,
		typeof b
	);
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

### 13. Explain the result of output:

```javascript
(function test() {
	var a = [];

	console.log(
		a.length,
		[,].length,
		[, ,].length
	);

	a.length = -1;
	console.log(a.length);
})();
```

```javascript
(function test() {
	var a = [1, 2, 3, 4, 5];
	a.length = null;

	console.log(a[4]);
})();
```

```javascript
(function test() {
	var a = [1, 2, 3, 4, 5];
	a.length = undefined;

	console.log(a[4]);
})();
```

```javascript
(function test() {
	var a = [[[1], 2], 3];

	console.log(a.length);
})();
```

```javascript
(function test() {
	console.log(
	    [1,2,[3,4]] + [[5,6], 7, 8]
	);
})();
```

### 14. Explain the result of output:

```javascript
(function test() {
	console.log(
		9 < 5 < 1,
		2 < 6 < 1,
		1 < 3 < 4
	);
})();
```

### 15. Explain the result of output:

```javascript
(function test() {
	function fn() {
		return
		{
			value: "test"
		}
	}

	console.log(
		typeof fn()
	);
})();
```

### 16. Explain the result of output:

```javascript
(function test() {
	function sum(a, b) {
		return a + b;
	}

	function sum(c) {
		return c;
	}

	console.log(sum(3));
	console.log(sum(2, 4));
})();
```

### 17. Explain the result of output:

```javascript
(function test() {
	a = 1;
	window.b = 2;
	this.c = 3;
	var d = 4;

	delete a;
	delete b;
	delete c;
	delete d;

	console.log(typeof a, typeof b, typeof c, typeof d);
})();
```

### 18. Explain the result of output:

```javascript
(function test() {
	var a = 1;

	setTimeout(function () {
		a = 0;
		console.log('Hi!');
	}, 0);

	while (a) {
	}
	console.log('Hello!');
})();
```

### 19. Explain the result of output:

```javascript
(function test() {
	console.log(
		[] - [],
		[] + [],
		{} - {},
		{} + {}
	);
})();
```

### 20. Explain the result of output:

```javascript
(function test() {
	var holder = {value: 1},
		holder2 = holder;

	holder.result = holder = {value: 0};

	console.log(
		holder.result,
		holder2
	);
})();
```

### 21. Explain the result of output:

```javascript
(function test() {
	var test = {
		property: 'Value',

		getPropertyValue: function () {
			return this.property;
		}
	};

	var getPropertyValue = test.getPropertyValue;

	console.log(
		getPropertyValue(),
		test.getPropertyValue()
	);
})();
```

```javascript
(function test () {
	"use strict";
	
	var holder, fn;
	holder = {
		holderFn: function () {
			console.log(this);
		}
	};
	fn = holder.holderFn;
	
	holder.holderFn();
	fn();
})();
```

### 22. What is the maximum depth of the stack, starting with the "test" function?

```javascript
var a = [1, 2, 3, 4, 5];

(function test() {
    console.log((new Error()).stack);

    var item = a.pop();
    item && setTimeout(arguments.callee, 0);
})();
```

```javascript
var a = [1, 2, 3, 4, 5];

(function test() {
    console.log((new Error()).stack);

    var item = a.pop();
    item && arguments.callee();
})();
```

### 23. Explain the result of output:

```javascript
(function test() {
	function fn() {
		arguments.callee.count = arguments.callee.count || 0;
		return arguments.callee.count++;
	}

	console.log(
		fn(),
		fn(),
		fn()
	);
})();
```

### 24. Explain the result of output:

```javascript
(function test() {
	var a = '5', b = 2, c = a+++b;
	console.log(c);
})();
```

### 25. Explain the result of output:

```javascript
console.log(
	016 * 2,
	0x16 * 2
);
```

```javascript
console.log(
	Math.floor(999.99) === ~~999.99,
	Math.floor(-999.99) === ~~-999.99,
	~function(){}(),
	~~function(){}(),
	~~null,
	~~undefined,
	~~[],
	~~{},
	~~'Test'
);
```

```javascript
console.log(
	1 + "2" + "2",
	1 + +"2" + "2",
	1 + -"1" + "2",
	+"1" + "1" + "2",
	"2" * 3,
	"6" / 2,
	"A" - "B" + "2",
	"A" - "B" + 2
);
```

```javascript
console.log(0.1 + 0.2);
console.log(0.1 + 0.2 === 0.3);
console.log(
	(0.1 + 0.2) + 0.3 === 0.1 + (0.2 + 0.3)
);
```

```javascript
console.log(
	Number('Test!'),
	Number(''),
	Number('00010'),
	Number(true),
	Number(NaN),
	parseInt('2', 2),
	parseInt('011', 8),
	parseInt('011', 10),
	parseInt('00C', 16),
	parseInt([10, 9, 8, 7, 6, 5, 4, 3, 2, 1]),
	1 / -0,
	isNaN(1 / -0),
	isFinite(1 / -0),
	0 / -0,
	isNaN(0 / -0),
	isFinite(0 / -0),
	1 / 0,
	isNaN(1 / 0),
	isFinite(1 / 0),
	0 / 0,
	isNaN(0 / 0),
	isFinite(0 / 0),
	NaN === NaN,
	Infinity === Infinity
);
```

### 26. Explain the result of output:

```javascript
console.log(true == [1] && true == [2]);
```

```javascript
console.log(
	new Boolean() == true,
	new Boolean("") == true,
	new Boolean("0") == true,
	new Boolean("1") == true,
	new Boolean("true") == true
);
```

```javascript
console.log(
	false == '0',
	false === '0',
	true == '1',
	true === '1',
	true == '2',
	true === '2'
);
```

### 27. Explain the result of output:

```javascript
(function () {
    var fn = function () {
        console.log(typeof this);
    };
    fn.call("Hello World!");
})();

(function () {
    "use strict";
    var fn = function () {
        console.log(typeof this);
    };
    fn.call("Hello World!");
})();
```

```javascript
console.log(
	(function () {
		return (new this).stack;
	}).apply(Error)
);
```

### 28. Explain the result of output:

```javascript
(function test() {
	var a = {},
		b = {value: 'test1'},
		c = {value: 'test2'};

	a[b] = 'test3';
	a[c] = 'test4';

	console.log(a[b]);
})();
```

### 29. Explain the result of output:

```javascript
console.log(
	Date(),
	new Date,
	+Date(),
	+new Date,
	+new Date(),
	+new Date() === +new Date
);
```

### 30. Explain the result of output:

```javascript
console.log(typeof confirm('Do you like JavaScript?'));
```

### 31. Eliminate non-existent state of promise.

1. fulfilled  
2. awaiting  
3. pending  
4. refused  
5. rejected  
6. interrupted
  
### 32. Explain the result of output:

```javascript
(function test() {
	console.log(
		[1, 2, 3, 4, 5].map(function (n) {
			return n === 1 && 1 || arguments.callee(n - 1) * n;
		})
	);
})();
```

```javascript
(function test() {
	"use strict";
	console.log(
		[1, 2, 3, 4, 5].map(function (n) {
			return n === 1 && 1 || arguments.callee(n - 1) * n;
		})
	);
})();
```

### 33. Explain the result of output:

```javascript
(function test() {
	var s1 = 'test',
		s2 = new String('test'),
		s3 = String('test');

	console.log(
		s1 == s2,
		s1 === s2,
		s1 == s3,
		s1 === s3,
		s1.constructor === s2.constructor,
		s1.constructor === s3.constructor,
		typeof s1,
		typeof s2,
		typeof s3
	);

	console.log(
		s1.slice() == s1,
		s1.slice() == s2,
		s1.slice() == s3,
		s1.slice() === s1,
		s1.slice() === s2,
		s1.slice() === s3
	);

	s1[2] = 'w';
	console.log(s1);
})();
```