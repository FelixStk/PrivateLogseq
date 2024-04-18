- based on: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/
- # 1. Grammar and types
  collapsed:: true
	- How can you write a comment?
	  collapsed:: true
		- in C++ style
		- use // or /* text text text */
		- nested comments: /* You can /* nest comments *\/ by escaping slashes */
	- What are the tree kinds of variable declarations?
	  collapsed:: true
		- var: Declares a variable, optionally initializing it to a value.
		- let: Declares a block-scoped, local variable, optionally initializing it to a value.
		- const: Declares a block-scoped, read-only named constant.
	- Are Destructuring assignment allowed?
	  collapsed:: true
		- Yes, examples:
			- const [a, b] = array;
			- const { a, b } = obj;
	- What are the variables scops?
	  collapsed:: true
		- Global scope: The default scope for all code running in script mode.
		- Module scope: The scope for code running in module mode.
		- Function scope: The scope created with a function
		- For `let` and `const`: Block scope: The scope created with a pair of curly braces (a block)
	- What are the eight data types defined in ECMAScript?
	  collapsed:: true
		- Seven data types that are [primitives](https://developer.mozilla.org/en-US/docs/Glossary/Primitive):
			- [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean). `true` and `false`.
			- [null](https://developer.mozilla.org/en-US/docs/Glossary/Null). A special keyword denoting a null value. (Because JavaScript is case-sensitive, `null` is not the same as `Null`, `NULL`, or any other variant.)
			- [undefined](https://developer.mozilla.org/en-US/docs/Glossary/Undefined). A top-level property whose value is not defined.
			- [Number](https://developer.mozilla.org/en-US/docs/Glossary/Number). An integer or floating point number. For example: `42` or `3.14159`.
			- [BigInt](https://developer.mozilla.org/en-US/docs/Glossary/BigInt). An integer with arbitrary precision. For example: `9007199254740992n`.
			- [String](https://developer.mozilla.org/en-US/docs/Glossary/String). A sequence of characters that represent a text value. For example: `"Howdy"`.
			- [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol). A data type whose instances are unique and immutable.
		- and [Object](https://developer.mozilla.org/en-US/docs/Glossary/Object)
	- How to convert strings to numbers?
	  collapsed:: true
		- [`parseInt("101",2)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
		- [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
	- What are six different kinds of literals?
	  collapsed:: true
		- [Array literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types#array_literals)
		- [Boolean literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types#boolean_literals)
		- [Numeric literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types#numeric_literals)
		- [Object literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types#object_literals)
		- [RegExp literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types#regexp_literals)
		- [String literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types#string_literals)
	- What are Tailing commas and why do you want to use them?
	  collapsed:: true
		- Reason: Clean git diffs
		  collapsed:: true
			- ```
			  const myList = [
			    "home",
			    "school",
			  + "hospital",
			  ];
			  ```
		- Example: `const myList = ["home", , "school", undefined ,];`
	- What are prefix and suffixes for Integer literals?
	  collapsed:: true
		- A leading `0` (zero) on an integer literal, or a leading `0o` (or `0O`) indicates it is in *octal*. Octal integer literals can include only the digits `0` – `7`.
		- A leading `0x` (or `0X`) indicates a *hexadecimal* integer literal. Hexadecimal integers can include digits (`0` – `9`) and the letters `a` – `f` and `A` – `F`. (The case of a character does not change its value. Therefore: `0xa` = `0xA` = `10` and `0xf` = `0xF` = `15`.)
		- A leading `0b` (or `0B`) indicates a *binary* integer literal. Binary integer literals can only include the digits `0` and `1`.
		- A trailing `n` suffix on an integer literal indicates a [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) literal. The integer literal can use any of the above bases. Note that leading-zero octal syntax like `0123n` is not allowed, but `0o123n` is fine.
	- What is the syntax for a floating-point literal?
	  collapsed:: true
		- `[digits].[digits][(E|e)[(+|-)]digits]`
	- How is it possible to do String interpolation with template literals?
	  collapsed:: true
		- ```
		  const name = 'Lev', time = 'today';
		  `Hello ${name}, how are you ${time}?`
		  ```
	- How do you use Latin-1 and unicode characters?
	  collapsed:: true
		- use \ in a string
		- | `\XXX` | The character with the Latin-1 encoding specified by up to three octal digits `XXX` between `0` and `377`. For example, `\251` is the octal sequence for the copyright symbol. |
		  | `\xXX` | The character with the Latin-1 encoding specified by the two hexadecimal digits `XX` between `00` and `FF`. For example, `\xA9` is the hexadecimal sequence for the copyright symbol. |
		  | `\uXXXX` | The Unicode character specified by the four hexadecimal digits `XXXX`. For example, `\u00A9` is the Unicode sequence for the copyright symbol. See [Unicode escape sequences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#string_literals). |
		  | `\u{XXXXX}` | Unicode code point escapes. For example, `\u{2F804}` is the same as the simple Unicode escapes `\uD87E\uDC04`. |
- # 2. Control flow and error handling
  collapsed:: true
	- What happens when var is used in a block?
	  collapsed:: true
		- ```
		  var x = 1;
		  {
		    var x = 2;
		  }
		  console.log(x); // 2
		  ```
	- What are the Conditional statements?
	  collapsed:: true
		- If
		  collapsed:: true
			- ```
			  if (condition1) {
			    statement1;
			  } else if (condition2) {
			    statement2;
			  } else if (conditionN) {
			    statementN;
			  } else {
			    statementLast;
			  }
			  ```
		- switch
		  collapsed:: true
			- ```
			  switch (expression) {
			    case label1:
			      statements1;
			      break;
			    case label2:
			      statements2;
			      break;
			    // …
			    default:
			      statementsDefault;
			  }
			  ```
	- What values evaluate to `false`?
	  collapsed:: true
		- `false`
		- `undefiend`
		- `null`
		- `0`
		- `NaN`
		- the empty string (`""`)
	- Where do you find some specifically created exception types?
	  collapsed:: true
		- [ECMAScript exceptions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error#error_types)
		- [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) and [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)
	- How does error handling work?
	  collapsed:: true
		- ```
		  openMyFile();
		  try {
		    writeMyFile(theData); // This may throw an error
		  } catch (e) {
		    handleError(e); // If an error occurred, handle it
		  } finally {
		    closeMyFile(); // Always close the resource
		  }
		  ```
		- If the `finally` block returns a value, this value becomes the return value of the entire `try…catch…finally` production, regardless of any `return` statements in the `try` and `catch` blocks
		- Overwriting of return values by the `finally` block also applies to exceptions thrown or re-thrown inside of the `catch` block
	- How can you utilize error objects?
	  collapsed:: true
		- use `e.name` and `e. message`
		- ```
		  function doSomethingErrorProne() {
		  	if (ourCodeMakesAMistake()) {
		  		throw new Error("The message");
		  	} else {
		  		doSomethingToGetAJavaScriptError();
		  	}
		  }
		  
		  try {
		  	doSomethingErrorProne();
		  } catch (e) {
		  	// Now, we actually use `console.error()`
		  	console.error(e.name); // 'Error'
		  	console.error(e.message); // 'The message', or a JavaScript error message
		  }
		  ```
- # 3. Loops and iteration
  collapsed:: true
	- What are the three most basic statements in JS-loops?
	  collapsed:: true
		- for statement
			- ```
			  for (initialization; condition; afterthought)
			    statement
			  ```
		- do...while statement
			- ```
			  do
			    statement
			  while (condition);
			  ```
		- while statement
			- ```
			  while (condition)
			    statement
			  ```
	- What is a labeled statement?
	  collapsed:: true
		- A [`label`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label) provides a statement with an identifier that lets you refer to it elsewhere in your program.
		- It can be used together with [`continue`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue) and [`break`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break)
	- What does `break` do?
	  collapsed:: true
		- When you use `break` without a label, it terminates the innermost enclosing `while`, `do-while`, `for`, or `switch` immediately and transfers control to the following statement.
		- When you use `break` with a label, it terminates the specified labeled statement.
		- ```
		  break;
		  break label;
		  ```
	- What does `continue` do?
	  collapsed:: true
		- When you use `continue` without a label, it terminates the current iteration of the innermost enclosing `while`, `do-while`, or `for` statement and continues execution of the loop with the next iteration. In contrast to the `break` statement, `continue` does not terminate the execution of the loop entirely. In a `while` loop, it jumps back to the condition. In a `for` loop, it jumps to the `increment-expression`.
		- When you use `continue` with a label, it applies to the looping statement identified with that label.
		- ```
		  continue;
		  continue label;
		  ```
	- What is the difference between the for..in and the for...of statement?
	  collapsed:: true
		- [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
		  collapsed:: true
			- iterates a specified variable over all the **enumerable properties of an object**. For each distinct property, JavaScript executes the specified statements. A `for...in` statement looks as follows:
			- ```
			  for (variable in object)
			  	statement
			  ```
		- [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
		  collapsed:: true
			- creates a loop Iterating over [iterable objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) (including [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map), [`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set), [`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments) object and so on), invoking a **custom iteration hook** with statements to be executed for the value of each distinct property.
			- ```
			  for (variable of object)
			  statement
			  ```
		- Example
		  collapsed:: true
			- ```
			  const arr = [3, 5, 7];
			  arr.foo = "hello";
			  
			  for (const i in arr) {
			  	console.log(i);
			  }
			  // "0" "1" "2" "foo"
			  
			  for (const i of arr) {
			  	console.log(i);
			  }
			  // Logs: 3 5 7
			  ```
	- How can you do destructuring with a for each loop?
	  collapsed:: true
		- [`Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)
		- ```
		  const obj = { foo: 1, bar: 2 };
		  	for (const [key, val] of Object.entries(obj)) {
		  	console.log(key, val);
		  }
		  // "foo" 1
		  // "bar" 2
		  ```
- # 4. Functions
  collapsed:: true
	- How can you define a function?
	  collapsed:: true
		- [Function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_declarations)
			- ```
			  function square(number) {
			    return number * number;
			  }
			  ```
		- [Function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_expressions)
			- ```
			  const square = function (number) {
			    return number * number;
			  };
			  const x = square(4); // x gets the value 16
			  ```
		- [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#arrow_functions)
			- ```
			  const a = ["Hydrogen", "Helium", "Lithium", "Beryllium"];
			  const b = a.map((s) => s.length);
			  console.log(b); // [8, 6, 7, 9]
			  ```
	- What is function hoisting?
	  collapsed:: true
		- JavaScript interpreter hoists the entire function declaration to the top of the current scope
		- Function hoisting only works with function **declarations** — not with function **expressions**
		- This means the following two codes are equivalent:
			- ```
			  console.log(square(5)); // 25
			  - function square(n) {
			  return n * n;
			  }
			  ```
			- ```
			  // All function declarations are effectively at the top of the scope
			  function square(n) {
			  return n * n;
			  }
			  - console.log(square(5)); // 25
			  ```
		-
	- What are Closures?
	  collapsed:: true
		- Explanation
			- Closures are one of the most powerful features of JavaScript. JavaScript allows for the **nesting of functions** and *grants the inner function full access to all the variables and functions defined inside the outer function* (and all other variables and functions that the outer function has access to).
			- However, the outer function does *not* have access to the variables and functions defined inside the inner function. This provides a sort of **encapsulation** for the variables of the inner function.
			- Also, since the inner function has access to the scope of the outer function, the variables and functions defined in the outer function will live longer than the duration of the outer function execution, if the inner function manages to survive beyond the life of the outer function. *A closure is created when the inner function is somehow made available to any scope outside the outer function.*
		- Example:
		  collapsed:: true
			- ```
			  const createPet = function (name) {
			  let sex;
			  const pet = {
			      // setName(newName) is equivalent to setName: function (newName)
			      // in this context
			      setName(newName) {
			        name = newName;
			      },
			      getName() {
			        return name;
			      },
			      getSex() {
			        return sex;
			      },
			      setSex(newSex) {
			        if (
			          typeof newSex === "string" &&
			          (newSex.toLowerCase() === "male" || newSex.toLowerCase() === "female")
			        ) {
			          sex = newSex;
			        }
			      },
			    };
			    return pet;
			  };
			  
			  const pet = createPet("Vivie");
			  pet.getName(); // Vivie
			  pet.setName("Oliver");
			  pet.setSex("male");
			  pet.getSex(); // male
			  pet.getName(); // Oliver
			  ```
	- How can you control parameters of functions?
	  collapsed:: true
		- Parameter names
		- Arguments object (an array-like object)
		  collapsed:: true
			- `arguments[i];`
			- ```
			  function myConcat(separator) {
			    let result = ""; // initialize list
			    // iterate through arguments
			    for (let i = 1; i < arguments.length; i++) {
			      result += arguments[i] + separator;
			    }
			    return result;
			  }
			  
			  
			  // returns "red, orange, blue, "
			  myConcat(", ", "red", "orange", "blue");
			  ```
		- Default parameters
		  collapsed:: true
			- ```
			  function multiply(a, b = 1) {
			  return a * b;
			  }
			  - multiply(5); // 5
			  ```
		- Rest parameters (represent an indefinite number of arguments as an array)
		  collapsed:: true
			- ```
			  function multiply(multiplier, ...theArgs) {
			  return theArgs.map((x) => multiplier * x);
			  }
			  - const arr = multiply(2, 1, 2, 3);
			  console.log(arr); // [2, 4, 6]
			  ```
	- Why do we use arrow functions?
	  collapsed:: true
		- shorter functions
		- no separate `this`
			- Until arrow functions, every new function defined its own `this` value
			- This proved to be less than ideal with an object-oriented style of programming => use [`bind()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind) or arrow functions
	- What do these predefined functions do?
	  collapsed:: true
		- [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval)
		  collapsed:: true
			- The **`eval()`** method evaluates JavaScript code represented as a string.
		- [`isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isFinite)
		  collapsed:: true
			- The global **`isFinite()`** function determines whether the passed value is a finite number. If needed, the parameter is first converted to a number.
		- [`isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN)
		  collapsed:: true
			- The **`isNaN()`** function determines whether a value is [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or not. Note: coercion inside the `isNaN` function has [interesting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN#description) rules; you may alternatively want to use [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN) to determine if the value is Not-A-Number.
		- [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
		  collapsed:: true
			- The **`parseFloat()`** function parses a string argument and returns a floating point number.
		- [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
		  collapsed:: true
			- The **`parseInt()`** function parses a string argument and returns an integer of the specified radix (the base in mathematical numeral systems).
		- [`decodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURI)
		  collapsed:: true
			- The **`decodeURI()`** function decodes a Uniform Resource Identifier (URI) previously created by [`encodeURI`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) or by a similar routine.
		- [`decodeURIComponent()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent)
		  collapsed:: true
			- The **`decodeURIComponent()`** method decodes a Uniform Resource Identifier (URI) component previously created by [`encodeURIComponent`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) or by a similar routine.
		- [`encodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)
		  collapsed:: true
			- The **`encodeURI()`** method encodes a Uniform Resource Identifier (URI) by replacing each instance of certain characters by one, two, three, or four escape sequences representing the UTF-8 encoding of the character (will only be four escape sequences for characters composed of two "surrogate" characters).
		- [`encodeURIComponent()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent)
		  collapsed:: true
			- The **`encodeURIComponent()`** method encodes a Uniform Resource Identifier (URI) component by replacing each instance of certain characters by one, two, three, or four escape sequences representing the UTF-8 encoding of the character (will only be four escape sequences for characters composed of two "surrogate" characters).
		- [`escape()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/escape)
		  collapsed:: true
			- The deprecated **`escape()`** method computes a new string in which certain characters have been replaced by a hexadecimal escape sequence. Use [`encodeURI`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) or [`encodeURIComponent`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) instead.
		- [`unescape()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/unescape)
		  collapsed:: true
			- The deprecated **`unescape()`** method computes a new string in which hexadecimal escape sequences are replaced with the character that it represents. The escape sequences might be introduced by a function like [`escape`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/escape). Because `unescape()` is deprecated, use [`decodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURI) or [`decodeURIComponent`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent) instead.
- # 5. Expressions and operators
  collapsed:: true
	- What is an expression? Name two kind of expressions with examples.
	  collapsed:: true
		- an *expression* is a valid unit of code that resolves to a value
		- kinds:
			- expressions with side effects, e.g. `x=7`
			- expression that purely evaluate, e.g. `3+7`
	- How many assignment operators are in JS?
	  collapsed:: true
		- 1 Basic assignment `=`
		- 6 Math assignments `+=`, `-=`, `*=`, `/=`, `%=`, `**=`
		- 3 shift assignments `<<`, `>>`, `>>=`
		- 3 bitwise assignments `&=` `|=` `^=`
		- 3 logical assignments `&&=` `||=` `??=`
		- 16 in total
	- What is the difference between a right shift assignment and an unsigned right shift assignment?
	  collapsed:: true
		- `>>` is arithmetic shift right, `>>>` is logical shift right.
		- In an arithmetic shift, the sign bit is extended to preserve the signedness of the number.
		- ```
		  let a = 5; //  00000000000000000000000000000101
		  a >>>= 2;  //  00000000000000000000000000000001
		  console.log(a);
		  ```
		-
		- What is the difference between a logical AND assignment and a bitwise AND assignment?
		  collapsed:: true
			- Logical AND assignment
				- The **logical AND assignment (`x &&= y`)** operator only assigns if `x` is [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).
				- ```
				  let a = 1;
				  let b = 0;
				  
				  a &&= 2;
				  console.log(a);
				  // Expected output: 2
				  
				  b &&= 2;
				  console.log(b);
				  // Expected output: 0
				  ```
			- Bitwise AND assignment
				- The **bitwise AND assignment (`&=`)** operator uses the binary representation of both operands, does a bitwise AND operation on them and assigns the result to the variable.
				- ```
				  let a = 5;      // 00000000000000000000000000000101
				  a &= 3;         // 00000000000000000000000000000011
				  
				  console.log(a); // 00000000000000000000000000000001
				  // Expected output: 1
				  ```
		- What does the Nullish coalescing assignment operator?
		  collapsed:: true
			- The **nullish coalescing assignment (`x ??= y`)** operator, also known as the **logical nullish assignment** operator, only assigns if `x` is [nullish](https://developer.mozilla.org/en-US/docs/Glossary/Nullish) (`null` or `undefined`).
			- ```const a = { duration: 50 };
			  const a = { duration: 50 };
			  
			  a.duration ??= 10;
			  console.log(a.duration);
			  // Expected output: 50
			  
			  a.speed ??= 25;
			  console.log(a.speed);
			  // Expected output: 25
			  ```
		- How are operators evaluated (left to right or right to left)?
		  collapsed:: true
			- For expressions without parentheses or other grouping operators like array literals,
				- the assignment expressions are **grouped right to left** (they are [right-associative](https://en.wikipedia.org/wiki/Operator_associativity)),
				- but they are **evaluated left to right**.
			- Examples: [Evaluation and nesting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#evaluation_and_nesting)
	- How many comparison operators are in JS?
	  collapsed:: true
		- [Equal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) (`==`) , [Not equal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality) (`!=`)
		- [Strict equal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality) (`===`), [Strict not equal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality) (`!==`)
		- Comparison operators (`>`, `>=`, `<`, `<=`)
		- 8 in total
	- What is the difference between  the equal operator and the strict equal operator?
	  collapsed:: true
		- the strict equality operator always considers operands of different types to be different
		- normally JavaScript attempts to convert them to an appropriate type for the comparison
	- How may arithmetic operators are there in JS?
	  collapsed:: true
		- 4 standard arithmetic operations (`+`, `-`, `*`, `/`)
		- Remainder (`%`)
		- Increment (`++`), Decrement (`--`)
		- Unary negation (`-` like in `-x`), Unary plus (`+`)
		- Exponentiation operator (**)
		- 10 in total
	- What is the difference between `++x` and `x++`?
	  collapsed:: true
		- If used as a prefix operator (`++x`), returns the value of its operand after adding one;
		- if used as a postfix operator (`x++`), returns the value of its operand before adding one.
	- What does a division by zero produce?
	  collapsed:: true
		- [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)
		- The same number value as [`Number.POSITIVE_INFINITY`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY).
		-
	- How may bitwise operators are there in JS?
	  collapsed:: true
		- [Bitwise AND](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_AND) `&`, [Bitwise OR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR) `|`, [Bitwise XOR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR) `^`, [Bitwise NOT](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_NOT) `~`
		- [Left shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Left_shift) `<<`,  [Sign-propagating right shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Right_shift) `>>`, [Zero-fill right shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unsigned_right_shift) `>>>`
		- 7 in total
	- What do bitwise operators treat their operands as?
	  collapsed:: true
		- as a set of 32 bits
	- How many logical operators are there in JS?
	  collapsed:: true
		- [Logical AND](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND) (`&&`), [Logical OR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR)(`||`), [Logical NOT](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT) (`!`)
		- [Nullish coalescing operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing) (`??`)
		- 4 in total
	- What do the Locial AND and Logical OR operators return?
	  collapsed:: true
		- `expr1 && expr2` Returns `expr1` if it can be converted to `false`; otherwise, returns `expr2`
		- `expr1 || expr2` Returns `expr1` if it can be converted to `true`; otherwise, returns `expr2
	- Does short-circuit evaluation exist in JS?
	  collapsed:: true
		- Yes,
			- `false && anything` is short-circuit evaluated to false.
			- `true || anything` is short-circuit evaluated to true.
		- Note that the *anything* part of the above expressions is not evaluated, so any side effects of doing so do not take effect.
		- Note that for the second case, in modern code you can use the [Nullish coalescing operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing) (`??`) that works like `||`, but it only returns the second expression, when the first one is "[nullish](https://developer.mozilla.org/en-US/docs/Glossary/Nullish)", i.e. [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)
	- What is a operator you cannot use with [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) values?
	  collapsed:: true
		- [unsigned right shift (`>>>`)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unsigned_right_shift), because a BigInt does not have a fixed width, so technically it does not have a "highest bit".
	- Can you use addition between `BigInt` values ` and numbers?
	  collapsed:: true
		- No, use:
		- ```
		  const a = Number(1n) + 2; // 3
		  const b = 1n + BigInt(2); // 3n
		  ```
	- Is there a special operator to use in the context of strings?
	  collapsed:: true
		- Yes, the two concatenation operators:
		- ```
		  console.log("my " + "string"); // console logs the string "my string".
		  
		  let mystring = "alpha";
		  mystring += "bet"; // evaluates to "alphabet" and assigns this value to mystring.
		  ```
	- What is the syntax of the conditional operator do?
	  collapsed:: true
		- `condition ? val1 : val2`
		- If `condition` is true, the operator has the value of `val1`. Otherwise it has the value of `val2`.
	- What does the comma operator do?
	  collapsed:: true
		- The [comma operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator) (`,`) evaluates both of its operands and returns the value of the last operand.
	- When is the comma operator used?
	  collapsed:: true
		- This operator is primarily used inside a `for` loop, to allow multiple variables to be updated each time through the loop.
		- ```
		  const x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
		  const a = [x, x, x, x, x];
		  for (let i = 0, j = 9; i <= j; i++, j--) {
		    //                              ^
		    console.log(`a[${i}][${j}]= ${a[i][j]}`);
		  }
		  ```
	- What are the different unary operators in JS?
	  collapsed:: true
		- The [`delete`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete) operator deletes an object's property. It returns if the operation was successful.
			- ```
			  delete object.property;
			  delete object[propertyKey];
			  delete objectName[index];
			  ```
		- The [`typeof` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) returns a string indicating the type of the unevaluated operand.
		- The [`void` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void) specifies an expression to be evaluated without returning a value.
		  collapsed:: true
			- ```
			  const output = void 1;
			  console.log(output);
			  // Expected output: undefined
			  
			  void console.log('expression evaluated');
			  // Expected output: "expression evaluated"
			  
			  void function iife() {
			    console.log('iife is executed');
			  }();
			  // Expected output: "iife is executed"
			  
			  void function test() {
			    console.log('test function executed');
			  };
			  try {
			    test();
			  } catch (e) {
			    console.log('test function is not defined');
			    // Expected output: "test function is not defined"
			  }
			  ```
	- How do delete elements from arrays?
	  collapsed:: true
		- Do not use `delete`. It is bad practice (, because of the array length and indexing does not refresh).
		- Do,
			- overwrite the element with the value `undefined`
			- use array methods such as [`splice`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice).
	- What are the relation operators in JS?
	  collapsed:: true
		- The [`in` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) returns `true` if the specified property is in the specified object
			- ```
			  // Arrays
			  const trees = ["redwood", "bay", "cedar", "oak", "maple"];
			  0 in trees; // returns true
			  3 in trees; // returns true
			  6 in trees; // returns false
			  "bay" in trees; // returns false
			  // (you must specify the index number, not the value at that index)
			  "length" in trees; // returns true (length is an Array property)
			  
			  // built-in objects
			  "PI" in Math; // returns true
			  const myString = new String("coral");
			  "length" in myString; // returns true
			  
			  // Custom objects
			  const mycar = { make: "Honda", model: "Accord", year: 1998 };
			  "make" in mycar; // returns true
			  "model" in mycar; // returns true
			  ```
		- The [`instanceof` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) returns `true` if the specified object is of the specified object type
			- ```
			  const theDay = new Date(1995, 12, 17);
			  if (theDay instanceof Date) {
			    // statements to execute
			  }
			  ```
	- What are the common expressions in JS?
	  collapsed:: true
		- *Basic expression*: identifiers (`let`, `const`, `var`), 6 literals (`Array`, `Boolean`, `Numeric`, `Object`, `RegExp`, `String`)
		- The [`this` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) to refer to the current object.
		  collapsed:: true
			- ```
			  this["propertyName"];
			  this.propertyName;
			  ```
		- The `grouping operator ( )` controls the precedence of evaluation in expressions.
		- The [`new` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) creates an instance of a user-defined object type or of one of the built-in object types.
		  collapsed:: true
			- ```
			  const objectName = new objectType(param1, param2, /* …, */ paramN);
			  ```
		- The [`super` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super) is used to call functions on an object's parent.
		  collapsed:: true
			- It is useful with [classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) to call the parent constructor, for example.
			- ```
			  super(args); // calls the parent constructor.
			  super.functionOnParent(args);
			  ```
- # 6. Numbers and dates
  collapsed:: true
	- What is the numeric precision of floating point numbers and integers?
	  collapsed:: true
		- ±2^−1022 and ±2^+1023, or about ±10^−308 to ±10^+308 (floating point numbers)
		- ±2^53 − 1 (integers)
	- What are three additional symbolic values?
	  collapsed:: true
		- `+`[`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity),
		- `-`[`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity), and
		- [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) (not-a-number).
	- How do you write decimal, binary, octal, and hexadecimal numbers?
	  collapsed:: true
		- Decimal numbers:
			- normal digits
			- can start with a 0, but only if where is a 8 or 9 in it! (see octal numbers)
		- Binary numbers:
			- use `0b` or `0B` prefix
		- Octal numbers:
			- use `0o` prefix
			- legacy syntax: prefixing with zero (`0644 === 420`)
		- Hexadecimal numbers:
			- use prefix: `0x` or `0X`
		- If the digits are outside the range, the following [`SyntaxError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError) is thrown: "Identifier starts immediately after numeric literal".
	- How to you write exponentiation?
	  collapsed:: true
		- ```
		  0e-5   // 0
		  0e+5   // 0
		  5e1    // 50
		  175e-2 // 1.75
		  1e3    // 1000
		  1e-3   // 0.001
		  1E3    // 1000
		  ```
	- What properties has the `Number` object?
	  collapsed:: true
		- | Property | Description |
		  | ---- | ---- | ---- |
		  | [`Number.MAX_VALUE`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_VALUE) | The largest positive representable number (`1.7976931348623157e+308`) |
		  | [`Number.MIN_VALUE`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_VALUE) | The smallest positive representable number (`5e-324`) |
		  | [`Number.NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN) | Special "not a number" value |
		  | [`Number.NEGATIVE_INFINITY`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NEGATIVE_INFINITY) | Special negative infinite value; returned on overflow |
		  | [`Number.POSITIVE_INFINITY`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY) | Special positive infinite value; returned on overflow |
		  | [`Number.EPSILON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/EPSILON) | Difference between `1` and the smallest value greater than `1` that can be represented as a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) (`2.220446049250313e-16`) |
		  | [`Number.MIN_SAFE_INTEGER`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER) | Minimum safe integer in JavaScript (−2^53 + 1, or `−9007199254740991`) |
		  | [`Number.MAX_SAFE_INTEGER`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_SAFE_INTEGER) | Maximum safe integer in JavaScript (+2^53 − 1, or `+9007199254740991`) |
	- What methods has the `Number` object? (without methods for retrieving information in various formats)
	  collapsed:: true
		- | Method | Description |
		  | ---- | ---- | ---- |
		  | [`Number.parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat) | Parses a string argument and returns a floating point number. Same as the global [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) function. |
		  | [`Number.parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt) | Parses a string argument and returns an integer of the specified radix or base. Same as the global [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) function. |
		  | [`Number.isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isFinite) | Determines whether the passed value is a finite number. |
		  | [`Number.isInteger()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger) | Determines whether the passed value is an integer. |
		  | [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN) | Determines whether the passed value is [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN). More robust version of the original global [`isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN). |
		  | [`Number.isSafeInteger()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isSafeInteger) | Determines whether the provided value is a number that is a *safe integer*. |
	- What methods for retrieving informations from `Number` objects in various formats does the `Number` protoype provide?
	  collapsed:: true
		- | Method | Description |
		  | ---- | ---- | ---- |
		  | [`toExponential()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toExponential) | Returns a string representing the number in exponential notation. |
		  | [`toFixed()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed) | Returns a string representing the number in fixed-point notation. |
		  | [`toPrecision()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toPrecision) | Returns a string representing the number to a specified precision in fixed-point notation. |
	- What are some common properties and Methods of the `Math` object?
	  collapsed:: true
		- `Math.PI` and `Math.E`
		- | Method | Description |
		  | ---- | ---- | ---- |
		  | [`abs()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs) | Absolute value |
		  | [`sin()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sin), [`cos()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cos), [`tan()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/tan) | Standard trigonometric functions; with the argument in radians. |
		  | [`asin()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/asin), [`acos()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/acos), [`atan()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atan), [`atan2()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atan2) | Inverse trigonometric functions; return values in radians. |
		  | [`sinh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sinh), [`cosh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cosh), [`tanh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/tanh) | Hyperbolic functions; argument in hyperbolic angle. |
		  | [`asinh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/asinh), [`acosh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh), [`atanh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atanh) | Inverse hyperbolic functions; return values in hyperbolic angle. |
		  | [`pow()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/pow), [`exp()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/exp), [`expm1()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/expm1), [`log()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log), [`log10()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log10), [`log1p()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log1p), [`log2()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log2) | Exponential and logarithmic functions. |
		  | [`floor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor), [`ceil()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) | Returns the largest/smallest integer less/greater than or equal to an argument. |
		  | [`min()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min), [`max()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max) | Returns the minimum or maximum (respectively) value of a comma separated list of numbers as arguments. |
		  | [`random()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) | Returns a random number between 0 and 1. |
		  | [`round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round), [`fround()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/fround), [`trunc()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc), | Rounding and truncation functions. |
		  | [`sqrt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt), [`cbrt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cbrt), [`hypot()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot) | Square root, cube root, Square root of the sum of square arguments. |
		  | [`sign()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sign) | The sign of a number, indicating whether the number is positive, negative or zero. |
		  | [`clz32()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/clz32),[`imul()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/imul) | Number of leading zero bits in the 32-bit binary representation. The result of the C-like 32-bit multiplication of the two arguments. |
	- Who do you initialize `BigInt` correctly?
	  collapsed:: true
		- A BigInt can be defined as an integer literal suffixed by `n`
		- Use [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/BigInt) constructor with a **string** argument
		- *Note:* `BigInt` does not function with `Math` (at the moment)
	- What does the `Date` object count?
	  collapsed:: true
		- the number of milliseconds since January 1, 1970, 00:00:00
	- In what ways can you use the `parameters` in `const dateObjectName = new Date([parameters]);`
	  collapsed:: true
		- Nothing: creates today's date and time. For example, `today = new Date();`.
		- A string representing a date in the following form: "Month day, year hours:minutes:seconds." For example, `let Xmas95 = new Date("December 25, 1995 13:30:00")`. If you omit hours, minutes, or seconds, the value will be set to zero.
		- A set of integer values for year, month, and day. For example, `let Xmas95 = new Date(1995, 11, 25)`.
		- A set of integer values for year, month, day, hour, minute, and seconds. For example, `let Xmas95 = new Date(1995, 11, 25, 9, 30, 0);`.
	- What methods are there in the `Date` object?
	  collapsed:: true
		- "set" methods, for setting date and time values in `Date` objects.
		- ```
		  const time = new Date();
		  const hour = time.getHours();
		  const ms_since_1970 = time.getTime();
		  ```
		- "get" methods, for getting date and time values from `Date` objects.
		- "to" methods, for returning string values from `Date` objects.
		- parse and UTC methods, for parsing `Date` strings.
		  collapsed:: true
			- ```
			  const ipoDate = new Date();
			  ipoDate.setTime(Date.parse("Aug 9, 1995"));
			  ```
		-
		-
- # 7. Text formatting
  collapsed:: true
	- How do you input string literals?
	  collapsed:: true
		- Use either single or double quotes:
		- ```
		  'foo'
		  "bar"
		  ```
	- As what is a element of a string processed in JS?
	  collapsed:: true
		- as a UTF-16 code units
	- What are three advanced methods use escape sequences in string?
	  collapsed:: true
		- Hexadecimal escape sequence: `"\xA9" // "©"`
		- Unicode point excapes: `"\u{2F804}"` (it's possible to represent unicode points up to `0x10FFFF`.)
			- Note: `'\u{1F600}'.length` is `2`
			- Use [String.fromCodePoint()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCodePoint) or [String.prototype.codePointAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/codePointAt) for conversions
	- Are string objects immutable?
	  collapsed:: true
		- Yes, they are!
	- What are some methods for String Objects?
	  collapsed:: true
		- | Method | Description |
		  | ---- | ---- | ---- |
		  | [charAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt), [charCodeAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt), [codePointAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/codePointAt) | Return the character or character code at the specified position in string. |
		  | [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf), [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf) | Return the position of specified substring in the string or last position of specified substring, respectively. |
		  | [startsWith()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith), [endsWith()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith), [includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes) | Returns whether or not the string starts, ends or contains a specified string. |
		  | [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat) | Combines the text of two strings and returns a new string. |
		  | [split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) | Splits a String object into an array of strings by separating the string into substrings. |
		  | [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice) | Extracts a section of a string and returns a new string. |
		  | [substring()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring), [substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr) | Return the specified subset of the string, either by specifying the start and end indexes or the start index and a length. |
		  | [match()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match), [matchAll()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/matchAll), [replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace), [replaceAll()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll), [search()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search) | Work with regular expressions. |
		  | [toLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase), [toUpperCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) | Return the string in all lowercase or all uppercase, respectively. |
		  | [normalize()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize) | Returns the Unicode Normalization Form of the calling string value. |
		  | [repeat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) | Returns a string consisting of the elements of the object repeated the given times. |
		  | [trim()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim) | Trims whitespace from the beginning and end of the string. |
	- What are two special things you can do with template literals?
	  collapsed:: true
		- You can write multi-line literals without `\n`
		- You can use embedded expressions
		- ```
		  console.log(`string text line 1
		  string text line 2`);
		  
		  const five = 5;
		  const ten = 10;
		  console.log(`Fifteen is ${five + ten} and not ${2 * five + ten}.`);
		  // "Fifteen is 15 and not 20."
		  ```
	- What do you use for the internationalization of dates and times?
	  collapsed:: true
		- The [Intl.DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat) object
		- ```
		  // July 17, 2014 00:00:00 UTC:
		  const july172014 = new Date("2014-07-17");
		  
		  const options = {
		    year: "2-digit",
		    month: "2-digit",
		    day: "2-digit",
		    hour: "2-digit",
		    minute: "2-digit",
		    timeZoneName: "short",
		  };
		  const americanDateTime = new Intl.DateTimeFormat("en-US", options).format;
		  
		  // Local timezone vary depending on your settings
		  // In CEST, logs: 07/17/14, 02:00 AM GMT+2
		  // In PDT, logs: 07/16/14, 05:00 PM GMT-7
		  console.log(americanDateTime(july172014));
		  ```
	- What do you use for the internationalization of number formatting?
	  collapsed:: true
		- The [Intl.NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat) object
		- ```
		  const gasPrice = new Intl.NumberFormat("en-US", {
		    style: "currency",
		    currency: "USD",
		    minimumFractionDigits: 3,
		  });
		  
		  console.log(gasPrice.format(5.259)); // $5.259
		  
		  const hanDecimalRMBInChina = new Intl.NumberFormat("zh-CN-u-nu-hanidec", {
		    style: "currency",
		    currency: "CNY",
		  });
		  
		  console.log(hanDecimalRMBInChina.format(1314.25)); // ￥ 一,三一四.二五
		  ```
	- What is an useful object for the comparison and sorting of strings?
	  collapsed:: true
		- The [Intl.Collator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator) object
		- ```
		  const names = ["Hochberg", "Hönigswald", "Holzman"];
		  
		  const germanPhonebook = new Intl.Collator("de-DE-u-co-phonebk");
		  console.log(names.sort(germanPhonebook.compare).join(", "));
		  // "Hochberg, Hönigswald, Holzman"
		  
		  const germanDictionary = new Intl.Collator("de-DE-u-co-dict");
		  console.log(names.sort(germanDictionary.compare).join(", "));
		  // "Hochberg, Holzman, Hönigswald"
		  ```
- # 8. Regular expressions
  collapsed:: true
	- What are two ways of creating a regular expression?
	  collapsed:: true
		- slashes \rarr provide compilation of regular expressions when the script is loaded \rarr  may improve performance
			- `const re = /ab+c/;`
		- constructor (for changing expressions or them being user input)
			- `const re = new RegExp("ab+c");`
	- What are the special characters in regular expression?
	  collapsed:: true
		- | Characters / constructs | Corresponding article |
		  | ---- | ---- | ---- |
		  | `[xyz]`, `[^xyz]`, `.`, `\d`, `\D`, `\w`, `\W`, `\s`, `\S`, `\t`, `\r`, `\n`, `\v`, `\f`, `[\b]`, `\0`, `\c*X*`, `\x*hh*`, `\u*hhhh*`, `\u*{hhhh}*`, *x*\vert*y* | [Character classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes) |
		  | `^`, `$`, `\b`, `\B`, `x(?=y)`, `x(?!y)`, `(?<=y)x`, `(?<!y)x` | [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions) |
		  | `(x)`, `(?<Name>x)`, `(?:x)`, `\n`, `\k<Name>` | [Groups and backreferences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Groups_and_Backreferences) |
		  | `x*`, `x+`, `x?`, `x{n}`, `x*{n,}`, `x{n,m}` | [Quantifiers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Quantifiers) |
		  | `\p{*UnicodeProperty*}`, `\P{*UnicodeProperty*}` | [Unicode property escapes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Unicode_Property_Escapes) |
	- Do you need to escape `\` and `/`?
	  collapsed:: true
		- Yes, examples:
			- C:\ \rarr `/[A-Z]:\\/`
			- `/a\*b/` using the constructor \rarr `new RegExp("a\\*b")`
	- What do parentheses do in js regular expression?
	  collapsed:: true
		- they that part of the matched substring to be remembered.
		- Once remembered, the substring can be recalled for other use.
		- See [Groups and backreferences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Groups_and_Backreferences#using_groups) for more details.
			- Example: `const re = /^(?:\d{3}|\(\d{3}\)) ([-/.]) \d{3} \1 \d{4}$/;` for a phone number ###-###-####
	- What are methods that use regular expressions?
	  collapsed:: true
		- | Method | Description |
		  | ---- | ---- | ---- |
		  | [`exec()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec) | Executes a search for a match in a string. It returns an array of information or `null` on a mismatch. |
		  | [`test()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test) | Tests for a match in a string. It returns `true` or `false`. |
		  | [`match()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match) | Returns an array containing all of the matches, including capturing groups, or `null` if no match is found. |
		  | [`matchAll()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/matchAll) | Returns an iterator containing all of the matches, including capturing groups. |
		  | [`search()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search) | Tests for a match in a string. It returns the index of the match, or `-1` if the search fails. |
		  | [`replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) | Executes a search for a match in a string, and replaces the matched substring with a replacement substring. |
		  | [`replaceAll()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll) | Executes a search for all matches in a string, and replaces the matched substrings with a replacement substring. |
		  | [`split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) | Uses a regular expression or a fixed string to break a string into an array of substrings. |
	- What is the result of a regular expression execution?
	  collapsed:: true
		- ```
		  const myRe = new RegExp("d(b+)d", "g");
		  const myArray = myRe.exec("cdbbdbsbz");
		  ```
		- Value of `myArray`?
		  collapsed:: true
			- | Property or index | Description | In this example |
			  | `myArray` |The matched string and all remembered substrings. | `['dbbd', 'bb', index: 1, input: 'cdbbdbsbz']` |
			  | `index` | The 0-based index of the match in the input string. | `1` |
			  | `input` | The original string. | `'cdbbdbsbz'` |
			  | `[0]` | The last matched characters. | `'dbbd'` |
		- Value of `myRe`?
		  collapsed:: true
			- | Property or index | Description | In this example |
			  | `lastIndex` | The index at which to start the next match. (This property is set only if the regular expression uses the g option, described in [Advanced Searching With Flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#advanced_searching_with_flags).) | `5` |
			  | `source` | The text of the pattern. Updated at the time that the regular expression is created, not executed. | `'d(b+)d'` |
	- What are the search options via flags?
	  collapsed:: true
		- | Flag | Description | Corresponding property |
		  | ---- | ---- | ---- |
		  | `d` | Generate indices for substring matches. | [`hasIndices`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/hasIndices) |
		  | `g` | Global search. | [`global`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/global) |
		  | `i` | Case-insensitive search. | [`ignoreCase`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/ignoreCase) |
		  | `m` | Allows `^` and `$` to match newline characters. | [`multiline`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/multiline) |
		  | `s` | Allows `.` to match newline characters. | [`dotAll`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/dotAll) |
		  | `u` | "Unicode"; treat a pattern as a sequence of Unicode code points. | [`unicode`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/unicode) |
		  | `y` | Perform a "sticky" search that matches starting at the current position in the target string. | [`sticky`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/sticky) |
	- How do you add a flag to a regular expression?
	  collapsed:: true
		- Flags are an integral part of a regular expression. They cannot be added or removed later.
		- `const re = /pattern/flags;`
		- `const re = new RegExp("pattern", "flags");`
	- What happens when you use the global search flag with exec()?
	  collapsed:: true
		- It returns each match and its position iteratively.
		- ```
		  const str = "fee fi fo fum";
		  const re = /\w+\s/g;
		  - console.log(re.exec(str)); // ["fee ", index: 0, input: "fee fi fo fum"]
		  console.log(re.exec(str)); // ["fi ", index: 4, input: "fee fi fo fum"]
		  console.log(re.exec(str)); // ["fo ", index: 7, input: "fee fi fo fum"]
		  console.log(re.exec(str)); // null
		  
		  console.log(str.match(re)); // ["fee ", "fi ", "fo "]
		  ```
	- How can you use unicode text in regular expressions?
	  collapsed:: true
		- use u flag
		- use of [Unicode property escapes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Unicode_Property_Escapes) `\p{ }`, which are supported only within "unicode" regular expressions
		- Example: `/\p{L}*/u;`
	- What are some Tools for js regular expressions?
	  collapsed:: true
		- [RegExr](https://regexr.com/) An online tool to learn, build, & test Regular Expressions.
		- [Regex tester](https://regex101.com/): An online regex builder/debugger
		- [Regex interactive tutorial](https://regexlearn.com/): An online interactive tutorials, Cheat sheet, & Playground.
		- [Regex visualizer](https://extendsclass.com/regex-tester.html): An online visual regex tester.
- # 9. Indexed collections
  collapsed:: true
	- What are the different ways to create Arrays?
	  collapsed:: true
		- ```
		  const arr1 = new Array(element0, element1, /* … ,*/ elementN);
		  const arr2 = Array(element0, element1, /* … ,*/ elementN);
		  const arr3 = [element0, element1, /* … ,*/ elementN];
		  const arr4 = new Array(arrayLength);
		  const arr5 = [];
		  
		  const wisenArray = Array.of(9.3); // wisenArray contains only one element 9.3
		  ```
	- How do you refer to array elements?
	  collapsed:: true
		- ```
		  const arr = ["one", "two", "three"];
		  arr[2]; // three
		  arr["length"]; // 3
		  ```
	- What the the `length` of an Array?
	  collapsed:: true
		- Its value is always a positive integer greater than the index of the last element if one exists.
		- You can also assign to the `length` property. This can change the array!
		- ```
		  const cats = [];
		  cats[30] = ["Dusty"];
		  console.log(cats.length); // 31
		  ```
	- What are the different ways to iterate over an array?
	  collapsed:: true
		- for loop with length
		  collapsed:: true
			- ```
			  const colors = ["red", "green", "blue"];
			  for (let i = 0; i < colors.length; i++) {
			    console.log(colors[i]);
			  }
			  ```
		- for loop when none of the elements in the array evaluate to `false`
		  collapsed:: true
			- ```
			  const divs = document.getElementsByTagName("div");
			  for (let i = 0, div; (div = divs[i]); i++) {
			    /* Process div in some way */
			  }
			  ```
		- [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) method
		  collapsed:: true
			- ```
			  const sparseArray = ["first", "second", , "fourth"];
			  - sparseArray.forEach((element) => {
			  console.log(element);
			  });
			  // Logs:
			  // first
			  // second
			  // fourth
			  - if (sparseArray[2] === undefined) {
			  console.log("sparseArray[2] is undefined"); // true
			  }
			  - const nonsparseArray = ["first", "second", undefined, "fourth"];
			  - nonsparseArray.forEach((element) => {
			  console.log(element);
			  });
			  // Logs:
			  // first
			  // second
			  // undefined
			  // fourth
			  ```
	- What are common array methods?
	  collapsed:: true
		- The [`concat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat) method joins two or more arrays and returns a new array.
		- The [`join()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) method joins all elements of an array into a string.
		- The [`push()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) method adds one or more elements to the end of an array and returns the resulting `length` of the array.
		- The [`pop()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) method removes the last element from an array and returns that element.
		- The [`shift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) method removes the first element from an array and returns that element.
		- The [`unshift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) method adds one or more elements to the front of an array and returns the new length of the array.
		- The [`slice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) method extracts a section of an array and returns a new array.
		- The [`at()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/at) method returns the element at the specified index in the array, or `undefined` if the index is out of range.
		- The [`splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) method removes elements from an array and (optionally) replaces them.
		- The [`reverse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse) method transposes the elements of an array, in place.
		- The [`flat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat) method returns a new array with all sub-array elements concatenated into it recursively up to the specified depth.
		- The [`sort()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) method sorts the elements of an array in place, and returns a reference to the array.
		- The [`indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) method searches the array for `searchElement` and returns the index of the first match.
		- The [`lastIndexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf) method works like `indexOf`, but starts at the end and searches backwards.
		- The [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) method executes `callback` on every array item and returns `undefined`.
		- The [`map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) method returns a new array of the return value from executing `callback` on every array item.
		- The [`flatMap()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flatMap) method runs `map()` followed by a `flat()` of depth 1.
		- The [`filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) method returns a new array containing the items for which `callback` returned `true`.
		- The [`find()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) method returns the first item for which `callback` returned `true`.
		- The [`findLast()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLast) method returns the last item for which `callback` returned `true`.
		- The [`findIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) method returns the index of the first item for which `callback` returned `true`.
		- The [`findLastIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLastIndex) method returns the index of the last item for which `callback` returned `true`.
		- The [`every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every) method returns `true` if `callback` returns `true` for every item in the array.
		- The [`some()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some) method returns `true` if `callback` returns `true` for at least one item in the array.
		- The [`reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) method applies `callback(accumulator, currentValue, currentIndex, array)` for each value in the array for the purpose of reducing the list of items down to a single value. You can specify a `initialValue`
		- The [`reduceRight()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceRight) method works like `reduce()`, but starts with the last element.
	- What is the special thing about sparse arrays in javascript?
	  collapsed:: true
		- Arrays can contain "empty slots", which are not the same as slots filled with the value `undefined`.
		  collapsed:: true
			- ```
			  // Array constructor:
			  const a = Array(5); // [ <5 empty items> ]
			  
			  // Consecutive commas in array literal:
			  const b = [1, 2, , , 5]; // [ 1, 2, <2 empty items>, 5 ]
			  
			  // Directly setting a slot with index greater than array.length:
			  const c = [1, 2];
			  c[4] = 5; // [ 1, 2, <2 empty items>, 5 ]
			  
			  // Elongating an array by directly setting .length:
			  const d = [1, 2];
			  d.length = 5; // [ 1, 2, <3 empty items> ]
			  
			  // Deleting an element:
			  const e = [1, 2, 3, 4, 5];
			  delete e[2]; // [ 1, 2, <1 empty item>, 4, 5 ]
			  ```
		- In some operations, empty slots behave as if they are filled with `undefined`.
		  collapsed:: true
			- indexed access
			- for...of
			- spreading into an array
		- But in others (most notably array iteration methods), empty slots are skipped.
		  collapsed:: true
			- forEach
			- filter, some, etc.
			- property enumeration
			- spreading into a object
	- How are multi-dimensional arrays created?
	  collapsed:: true
		- ```
		  const a = new Array(4);
		  for (let i = 0; i < 4; i++) {
		    a[i] = new Array(4);
		    for (let j = 0; j < 4; j++) {
		      a[i][j] = `[${i}, ${j}]`;
		    }
		  }
		  
		  Output:
		  Row 0: [0, 0] [0, 1] [0, 2] [0, 3]
		  Row 1: [1, 0] [1, 1] [1, 2] [1, 3]
		  Row 2: [2, 0] [2, 1] [2, 2] [2, 3]
		  Row 3: [3, 0] [3, 1] [3, 2] [3, 3]
		  ```
		-
	- Can you store other properties using an array?
	  collapsed:: true
		- Yes, for example, when an array is the result of a match between a regular expression and a string, the array returns properties and elements that provide information about the match
		- ```
		  const arr = [1, 2, 3];
		  arr.property = "value";
		  console.log(arr.property); // "value"
		  ```
	- What do you need to keep in mind when working with array-like objects?
	  collapsed:: true
		- they look and behave like arrays on the surface but do not share all of their methods.
			- Example: The `arguments` object provides a [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length) attribute but does not implement array methods like [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
		- [`Function.prototype.call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call) may help
			- ```
			  function printArguments() {
			    Array.prototype.forEach.call(arguments, (item) => {
			      console.log(item);
			    });
			  }
			  ```
			- ```
			  Array.prototype.forEach.call("a string", (chr) => {
			    console.log(chr);
			  });
			  ```
		-
- # 10. Keyed collections
  collapsed:: true
	- How do you work with a `Map`? Fill & delete elements of `Map` and iterate through it.
	  collapsed:: true
		- ```
		  const sayings = new Map();
		  sayings.set("dog", "woof");
		  sayings.set("cat", "meow");
		  sayings.set("elephant", "toot");
		  sayings.size; // 3
		  sayings.get("dog"); // woof
		  sayings.get("fox"); // undefined
		  sayings.has("bird"); // false
		  sayings.delete("dog");
		  sayings.has("dog"); // false
		  
		  for (const [key, value] of sayings) {
		    console.log(`${key} goes ${value}`);
		  }
		  
		  // "cat goes meow"
		  // "elephant goes toot"
		  sayings.clear();
		  sayings.size; // 0
		  ```
		-
	- What are the different advantages of `Map` when comparing it with`Object`?
	  collapsed:: true
		- The keys of an `Object` are [`Strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) or [`Symbols`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol), where they can be of any value for a `Map`.
		- You can get the `size` of a `Map` easily, while you have to manually keep track of size for an `Object`.
		- The iteration of maps is in insertion order of the elements.
		- An `Object` has a prototype, so there are default keys in the map. (This can be bypassed using `map = Object.create(null)`.)
		-
	- How do you decide whether to use a `Map` or an `Object`?
	  collapsed:: true
		- Use maps over objects when keys are unknown until run time, and when all keys are the same type and all values are the same type.
		- Use maps if there is a need to store primitive values as keys because object treats each key as a string whether it's a number value, boolean value or any other primitive value.
		- Use objects when there is logic that operates on individual elements.
	- What is the special thing about a [`WeakMap`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) ?
	  collapsed:: true
		- it's a collection of key/value pairs whose keys must be objects or [non-registered symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol#shared_symbols_in_the_global_symbol_registry), with values of any arbitrary [JavaScript type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures), and which does not create strong references to its keys.
			- That is, an object's presence as a key in a `WeakMap` does not prevent the object from being garbage collected. Once an object used as a key has been collected, its corresponding values in any `WeakMap` become candidates for garbage collection as well — as long as they aren't strongly referred to elsewhere.
			- The only primitive type that can be used as a `WeakMap` key is symbol — more specifically, [non-registered symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol#shared_symbols_in_the_global_symbol_registry) — because non-registered symbols are guaranteed to be unique and cannot be re-created.
	- What is a use case of `WeakMap`?
	  collapsed:: true
		- ["Hiding Implementation Details with ECMAScript 6 WeakMaps](https://fitzgeraldnick.com/2014/01/13/hiding-implementation-details-with-e6-weakmaps.html)
			- ```
			  const privates = new WeakMap();
			  
			  function Public() {
			  const me = {
			      // Private data goes here
			    };
			    privates.set(this, me);
			  }
			  
			  Public.prototype.method = function () {
			    const me = privates.get(this);
			    // Do stuff with private data in `me`
			    // …
			  };
			  
			  module.exports = Public;
			  ```
		- For more information and example code, see also "Why WeakMap?" on the [`WeakMap`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) reference page.
	- How do you fill, remove and check existence of elements in a `Set`?
	  collapsed:: true
		- [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) objects are collections of unique values. You can iterate its elements in insertion order. A value in a `Set` may only occur once; it is unique in the `Set`'s collection.
		- ```
		  const mySet = new Set();
		  mySet.add(1);
		  mySet.add("some text");
		  mySet.add("foo");
		  
		  mySet.has(1); // true
		  mySet.delete("foo");
		  mySet.size; // 2
		  
		  for (const item of mySet) {
		    console.log(item);
		  }
		  // 1
		  // "some text"
		  ```
	- How do you convert between `Array` and `Set`?
	  collapsed:: true
		- You can create an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) from a Set using [`Array.from`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) or the [spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax).
		- Also, the `Set` constructor accepts an `Array` to convert in the other direction.
		- ```
		  Array.from(mySet);
		  [...mySet2];
		  
		  mySet2 = new Set([1, 2, 3, 4]);
		  ```
	- What are some advantages of `Set` over `Arrays`?
	  collapsed:: true
		- Deleting Array elements by value (`arr.splice(arr.indexOf(val), 1)`) is very slow.
		- `Set` objects let you delete elements by their value. With an array, you would have to `splice` based on an element's index.
		- The value [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) cannot be found with `indexOf` in an array.
		- `Set` objects store unique values. You don't have to manually keep track of duplicates.
	- How is a `WeakSet` object different to a `Set`?
	  collapsed:: true
		- [WeakSet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet) objects are collections of garbage-collectable values, including objects and [non-registered symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol#shared_symbols_in_the_global_symbol_registry). A value in the `WeakSet` may only occur once. It is unique in the `WeakSet`'s collection.
		- Differences:
			- In contrast to `Sets`, `WeakSets` are **collections of _objects or symbols only_**, and not of arbitrary values of any type.
			- The `WeakSet` is *weak*: References to objects in the collection are held weakly. If there is no other reference to an object stored in the `WeakSet`, they can be garbage collected. That also means that there is no list of current objects stored in the collection.
			- `WeakSets` are not enumerable.
		- The use cases of `WeakSet` objects are limited. They will not leak memory, so it can be safe to use DOM elements as a key and mark them for tracking purposes, for example.
	- On what is key and value equality of `Map` and `Set` based on?
	  collapsed:: true
		- [SameValueZero algorithm](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value-zero_equality):
			- Equality works like the identity comparison operator `===`.
			- `-0` and `+0` are considered equal.
			- [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) is considered equal to itself (contrary to `===`).
- # 11. Working with objects
  collapsed:: true
	- What are the three different ways to create objects?
	  collapsed:: true
		- Using object initializers
		  collapsed:: true
			- ```
			  const obj = {
			    property1: value1, // property name may be an identifier
			    2: value2, // or a number
			    "property n": value3, // or a string
			  };
			  ```
		- Using a constructor function
		  collapsed:: true
			- ```
			  function Car(make, model, year) {
			    this.make = make;
			    this.model = model;
			    this.year = year;
			  }
			  
			  const myCar = new Car("Eagle", "Talon TSi", 1993);
			  ```
		- Using the [Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create) method
		  collapsed:: true
			- It allows you to choose the [prototype](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) object for the object you want to create, without having to define a constructor function)
			- ```
			  // Animal properties and method encapsulation
			  const Animal = {
			    type: "Invertebrates", // Default value of properties
			    displayType() {
			      // Method which will display type of Animal
			      console.log(this.type);
			    },
			  };
			  
			  // Create new animal type called animal1
			  const animal1 = Object.create(Animal);
			  animal1.displayType(); // Logs: Invertebrates
			  
			  // Create new animal type called fish
			  const fish = Object.create(Animal);
			  fish.type = "Fishes";
			  fish.displayType(); // Logs: Fishes
			  ```
	- What are the two ways for accessing properties?
	  collapsed:: true
		- Dot notation
			- ```
			  // Dot notation
			  myCar.make = "Ford";
			  myCar.model = "Mustang";
			  myCar.year = 1969;
			  ```
		- Bracket notation
			- ```
			  // Bracket notation
			  myCar["make"] = "Ford";
			  myCar["model"] = "Mustang";
			  myCar["year"] = 1969;
			  ```
			- properties are strings or symbols (other literals might be automatically converted to sting via `toString()`)
	- What is a important security consideration when working with square brackets to access properties?
	  collapsed:: true
		- [object injection attacks](https://github.com/nodesecurity/eslint-plugin-security/blob/main/docs/the-dangers-of-square-bracket-notation.md). Possible solutions:
			- avoid the use of user input in property name fields
			- create a allowlist of allowed property names, and filter each user input through a helper function to check before allowing it to be used
			- use [ECMAScript 6 direct proxies](http://wiki.ecmascript.org/doku.php?id=harmony:direct_proxies), which can stand in front of your real object ( private API ) and expose a limited subset of the object (public API)
	- What are the three options for enumerating properties of objects?
	  collapsed:: true
		- [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loops. This method traverses all of the enumerable string properties of an object as well as its prototype chain.
		  collapsed:: true
			- ```
			  function showProps(obj, objName) {
			    let result = "";
			    for (const i in obj) {
			      // Object.hasOwn() is used to exclude properties from the object's
			      // prototype chain and only show "own properties"
			      if (Object.hasOwn(obj, i)) {
			        result += `${objName}.${i} = ${obj[i]}\n`;
			      }
			    }
			    console.log(result);
			  }
			  ```
		- [`Object.keys(myObj)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys). This method returns an array with only the enumerable own string property names ("keys") in the object `myObj`, but not those in the prototype chain.
		  collapsed:: true
			- ```
			  function showProps(obj, objName) {
			    let result = "";
			    Object.keys(obj).forEach((i) => {
			      result += `${objName}.${i} = ${obj[i]}\n`;
			    });
			    console.log(result);
			  }
			  ```
		- [`Object.getOwnPropertyNames(myObj)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames). This method returns an array containing all the own string property names in the object `myObj`, regardless of if they are enumerable or not.
		  collapsed:: true
			- ```
			  function listAllProperties(myObj) {
			    let objectToInspect = myObj;
			    let result = [];
			    while (objectToInspect !== null) {
			      result = result.concat(Object.getOwnPropertyNames(objectToInspect));
			      objectToInspect = Object.getPrototypeOf(objectToInspect);
			    }
			    return result;
			  }
			  ```
		-
	- How can you delete properties?
	  collapsed:: true
		- You can remove a non-inherited property using the [`delete`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete) operator.
			- ```
			  // Creates a new object, myobj, with two properties, a and b.
			  const myobj = new Object();
			  myobj.a = 5;
			  myobj.b = 12;
			  
			  // Removes the a property, leaving myobj with only the b property.
			  delete myobj.a;
			  console.log("a" in myobj); // false
			  ```
	- What is a `prototype` in Javascript?
	  collapsed:: true
		- All objects in JavaScript inherit from at least one other object.
		- The object being inherited from is known as the prototype, and the inherited properties can be found in the `prototype` object of the constructor.
		- See [Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) for more information.
	- How can you define a properties for all objects of one type?
	  collapsed:: true
		- [prototype](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/prototype) property
			- ```
			  Car.prototype.color = "red";
			  console.log(car1.color); // "red
			  ```
	- How do you define methods for an object (two notations)? Where are methods typically defined?
	  collapsed:: true
		- Two notations: with and without the keyword function
			- ```
			  objectName.methodName = functionName;
			  
			  const myObj = {
			    myMethod: function (params) {
			      // do something
			    },
			    
			    // this works too!
			    myOtherMethod(params) {
			      // do something else
			    },
			  };
			  ```
		- Methods are typically defined on the `prototype` object of the constructor, so that all objects of the same type share the same method.
		  collapsed:: true
			- For example, you can define a function that formats and displays the properties of the previously-defined `Car` objects.
			- ```
			  Car.prototype.displayCar = function () {
			    const result = `A Beautiful ${this.year} ${this.make} ${this.model}`;
			    console.log(result);
			  };
			  ```
	- What does the keyword `this` do?
	  collapsed:: true
		- `this` is a "hidden parameter" of a function call that's passed in by specifying the object before the function that was called
		- it can use within a method to refer to the current object
		  collapsed:: true
			- ```
			  const Manager = {
			    name: "Karina",
			    age: 27,
			    job: "Software Engineer",
			  };
			  
			  const Intern = {
			    name: "Tyrone",
			    age: 21,
			    job: "Software Engineer Intern",
			  };
			  function sayHi() {
			    console.log(`Hello, my name is ${this.name}`);
			  }
			  
			  // add sayHi function to both objects
			  Manager.sayHi = sayHi;
			  Intern.sayHi = sayHi;
			  
			  Manager.sayHi(); // Hello, my name is Karina
			  Intern.sayHi(); // Hello, my name is Tyrone
			  ```
		-
	- Can you call a function with another object as `this`?
	  collapsed:: true
		- Yes,
			- [`Function.prototype.call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call) or
			- [`Reflect.apply()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/apply)
	- What are the two ways for defining getters and setters?
	  collapsed:: true
		- defined within [object initializers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#using_object_initializers) with `set` and `get`
		  collapsed:: true
			- ```
			  const myObj = {
			    a: 7,
			    get b() {
			      return this.a + 1;
			    },
			    set c(x) {
			      this.a = x / 2;
			    },
			  };
			  
			  console.log(myObj.a); // 7
			  console.log(myObj.b); // 8, returned from the get b() method
			  myObj.c = 50; // Calls the set c(x) method
			  console.log(myObj.a); // 25
			  ```
		- added them later to any existing object with the [`Object.defineProperties()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperties) method
		  collapsed:: true
			- ```
			  const myObj = { a: 0 };
			  
			  Object.defineProperties(myObj, {
			  b: {
			    get() {
			      return this.a + 1;
			    },
			  },
			  c: {
			    set(x) {
			      this.a = x / 2;
			    },
			  },
			  });
			  
			  myObj.c = 10; // Runs the setter, which assigns 10 / 2 (5) to the 'a' property
			  console.log(myObj.b); // Runs the getter, which yields a + 1 or 6
			  ```
			-
			-
	- When are two `objects` equal?
	  collapsed:: true
		- objects are a reference type. \rArr
			- Two distinct objects are never equal, even if they have the same properties.
			- Only comparing the **same object reference** with itself yields true
- # 12. Using classes
  collapsed:: true
	- How do JavaScript classes differ from classes in other languages like C++?
	  collapsed:: true
		- In many other languages, *classes*, or constructors, are clearly distinguished from *objects*, or instances.
		- In JavaScript, classes are mainly an abstraction over the existing prototypical inheritance mechanism - all patterns are convertible to prototype-based inheritance.
			- JavaScript is a prototype-based language — an object's behaviors are specified by its own properties and its prototype's properties
	- How do you declare a typical class?
	  collapsed:: true
		- ```
		  class MyClass {
		    // Constructor
		    constructor() {
		      // Constructor body
		    }
		    
		    // Instance field
		    myField = "foo";
		    // Instance method
		    myMethod() {
		      // myMethod body
		    }
		    
		    // Static field
		    static myStaticField = "bar";
		    // Static method
		    static myStaticMethod() {
		      // myStaticMethod body
		    }
		    
		    // Static block
		    static {
		      // Static initialization code
		    }
		    
		    // Fields, methods, static fields, and static methods all have
		    // "private" forms
		    #myPrivateField = "bar";
		  }
		  ```
		-
	- How do you create a instance of a class?
	  collapsed:: true
		- use the [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) operator
		- ```
		  const myInstance = new MyClass();
		  console.log(myInstance.myField); // 'foo'
		  myInstance.myMethod();
		  ```
		-
	- Does hoisting work for classes?
	  collapsed:: true
		- No!
			- Unlike function declarations, class declarations are not [hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) (or, in some interpretations, hoisted but with the temporal dead zone restriction), which means you cannot use a class before it is declared.
			- ```
			  new MyClass(); // ReferenceError: Cannot access 'MyClass' before initialization
			  
			  class MyClass {}
			  ```
	- Can you imagine an example for creating an instant with a class expression?
	  collapsed:: true
		- ```
		  const MyClass = class MyClassLongerName {
		    // Class body. Here MyClass and MyClassLongerName point to the same class.
		  };
		  new MyClassLongerName(); // ReferenceError: MyClassLongerName is not defined
		  new MyClass();
		  ```
	- Can class methods read the private fields of other instances, when they belong to the same class?
	  collapsed:: true
		- Yes, example:
		- ```
		  class Color {
		    #values;
		    constructor(r, g, b) {
		      this.#values = [r, g, b];
		    }
		    redDifference(anotherColor) {
		      // #values doesn't necessarily need to be accessed from this:
		      // you can access private fields of other instances belonging
		      // to the same class.
		      return this.#values[0] - anotherColor.#values[0];
		    }
		  }
		  - const red = new Color(255, 0, 0);
		  const crimson = new Color(220, 20, 60);
		  red.redDifference(crimson); // 35
		  ```
			-
	- How to you define accessor fields in classes?
	  collapsed:: true
		- ```
		  class Color {
		    constructor(r, g, b) {
		      this.values = [r, g, b];
		    }
		    get red() {
		      return this.values[0];
		    }
		    set red(value) {
		      this.values[0] = value;
		    }
		  }
		  
		  const red = new Color(255, 0, 0);
		  red.red = 0;
		  console.log(red.red); // 0
		  ```
		- If a field only has a getter but no setter, it will be effectively read-only.
		-
	- What does the keyword `static` mean?
	  collapsed:: true
		- It indicates [*static properties*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static). These are a group of class features that are defined on the class itself, rather than on individual instances of the class. These features include:
			- Static methods
			- Static fields
			- Static getters and setters
	- How can implement  inheritance (`ColorWithAlpha` inherits from `Color`)?
	  collapsed:: true
		- use the keyword [extends](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends),
		- use [super()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super) before any `this` in the constructor
		- ```
		  class ColorWithAlpha extends Color {
		    #alpha;
		    constructor(r, g, b, a) {
		      super(r, g, b);
		      this.#alpha = a;
		    }
		    get alpha() {
		      return this.#alpha;
		    }
		    set alpha(value) {
		      if (value < 0 || value > 1) {
		        throw new RangeError("Alpha value must be between 0 and 1");
		      }
		      this.#alpha = value;
		    }
		  }
		  ```
		-
	- Can a class overwrite its parents methods or static methods?
	  collapsed:: true
		- Yes
	- Do derived classes have access to the parent class's private fields?
	  collapsed:: true
		- No, they don't have access.
	- How is the [diamond problem](https://en.wikipedia.org/wiki/Multiple_inheritance#The_diamond_problem) in JavaScript solved?
	  collapsed:: true
		- There isn't a multiple inheritance
		- But you can achive the effect of multiple inheritance through class composition and [mixins](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends#mix-ins)
	- Are derived classes instance of the base class?
	  collapsed:: true
		- Yes.
			- ```
			  const color = new ColorWithAlpha(255, 0, 0, 0.5);
			  console.log(color instanceof Color); // true
			  console.log(color instanceof ColorWithAlpha); // true
			  ```
	- What is a infamous example for how classes can cause problems, because they are mutable?
	  collapsed:: true
		- `Date` objects
			- ```
			  function incrementDay(date) {
			    return date.setDate(date.getDate() + 1);
			  }
			  const date = new Date(); // 2019-06-19
			  const newDay = incrementDay(date);
			  console.log(newDay); // 2019-06-20
			  // The old date is modified as well!?
			  console.log(date); // 2019-06-20
			  ```
- # 13. Using promises
  collapsed:: true
	- What is a `Promis`?
	  collapsed:: true
		- A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is an object representing the eventual completion or failure of an asynchronous operation.
			- Example: For `createAudioFileAsync()`, which asynchronously generates a sound file given a configuration record
			- ```
			  function successCallback(result) {
			    console.log(`Audio file ready at URL: ${result}`);
			  }
			  
			  function failureCallback(error) {
			    console.error(`Error generating audio file: ${error}`);
			  }
			  
			  createAudioFileAsync(audioSettings).then(successCallback, failureCallback);
			  ```
	- How do promises avoid the classic callback pyramid of doom?
	  collapsed:: true
		- the `then()` function returns a **new promise**, different from the original
			- ```
			  const promise = doSomething();
			  const promise2 = promise.then(successCallback, failureCallback);
			  ```
		- This second promise (`promise2`) represents the completion not just of `doSomething()`, but also of the `successCallback` or `failureCallback` you passed in — which can be other asynchronous functions returning a promise. When that's the case, any callbacks added to `promise2` get queued behind the promise returned by either `successCallback` or `failureCallback`.
	- What can you shorten the promise chaining code?
	  collapsed:: true
		- you don't have to use the long form of `then(successCallback, failureCallback)`
			- the second argument of `then` is optional
			- `catch(failureCallback)` is short for `then(null, failureCallback)`
			- ```
			  doSomething()
			    .then(function (result) {
			      return doSomethingElse(result);
			    })
			    .then(function (newResult) {
			      return doThirdThing(newResult);
			    })
			    .then(function (finalResult) {
			      console.log(`Got the final result: ${finalResult}`);
			    })
			    .catch(failureCallback);
			  ```
		- use [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
		  collapsed:: true
			- ```
			  doSomething()
			    .then((result) => doSomethingElse(result))
			    .then((newResult) => doThirdThing(newResult))
			    .then((finalResult) => {
			      console.log(`Got the final result: ${finalResult}`);
			    })
			    .catch(failureCallback);
			  ```
			- Always return results, otherwise callbacks won't catch the result of a previous promise (with arrow functions, `() => x` is short for `() => { return x; }`
	- What is a floating promise?
	  collapsed:: true
		- a promise you forgot to return
		- as a rule of thumb, whenever your operation encounters a promise, return it and defer its handling to the next `then` handler.
	- When is it a good idea to nest promises?
	  collapsed:: true
		- Nesting is a control structure to limit the scope of `catch` statements.
		- Specifically, a nested `catch` only catches failures in its scope and below, not errors higher up in the chain outside the nested scope. When used correctly, this gives greater precision in error recovery:
		  collapsed:: true
			- ```
			  doSomethingCritical()
			    .then((result) =>
			      doSomethingOptional(result)
			        .then((optionalResult) => doSomethingExtraNice(optionalResult))
			        .catch((e) => {}),
			    ) // Ignore if optional stuff fails; proceed.
			    .then(() => moreCriticalStuff())
			    .catch((e) => console.error(`Critical failure: ${e.message}`));
			  ```
			- The inner error-silencing `catch` handler only catches failures from `doSomethingOptional()` and `doSomethingExtraNice()`, after which the code resumes with `moreCriticalStuff()`. Importantly, if `doSomethingCritical()` fails, its error is caught by the final (outer) `catch` only, and does not get swallowed by the inner `catch` handler.
	- Can you chain after a catch?
	  collapsed:: true
		- Yes, which is useful to accomplish new actions even after an action failed in the chain.
			- Read the following example:
			  ```
			  new Promise((resolve, reject) => {
			    console.log("Initial");
			    resolve();
			  })
			    .then(() => {
			      throw new Error("Something failed");
			      
			      console.log("Do this");
			    })
			    .catch(() => {
			      console.error("Do that");
			    })
			    .then(() => {
			      console.log("Do this, no matter what happened before");
			    });
			  ```
			- Output:
			  ```
			  Initial
			  Do that
			  Do this, no matter what happened before
			  ```
	- Can you find three errors in the following Code?
	  collapsed:: true
		- ```
		  // Bad example! Spot 3 mistakes!
		  doSomething()
		    .then(function (result) {
		      doSomethingElse(result).then((newResult) => doThirdThing(newResult));
		    })
		    .then(() => doFourthThing());
		  ```
		- Error 1
		  collapsed:: true
			- The first mistake is to not chain things together properly. This happens when we create a new promise but forget to return it. As a consequence, the chain is broken — or rather, we have two independent chains racing. This means `doFourthThing()` won't wait for `doSomethingElse()` or `doThirdThing()` to finish, and will run concurrently with them — which is likely unintended. Separate chains also have separate error handling, leading to uncaught errors.
		- Error 2
		  collapsed:: true
			- The second mistake is to nest unnecessarily, enabling the first mistake. Nesting also limits the scope of inner error handlers, which—if unintended—can lead to uncaught errors. A variant of this is the [promise constructor anti-pattern](https://stackoverflow.com/questions/23803743/what-is-the-explicit-promise-construction-antipattern-and-how-do-i-avoid-it), which combines nesting with redundant use of the promise constructor to wrap code that already uses promises.
		- Error 3
		  collapsed:: true
			- The third mistake is forgetting to terminate chains with `catch`. Unterminated promise chains lead to uncaught promise rejections in most browsers. See [error handling](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#error_handling) below.
		- Correction
		  collapsed:: true
			- ```
			  doSomething()
			    .then(function (result) {
			      // If using a full function expression: return the promise
			      return doSomethingElse(result);
			    })
			    // If using arrow functions: omit the braces and implicitly return the result
			    .then((newResult) => doThirdThing(newResult))
			    // Even if the previous chained promise returns a result, the next one
			    // doesn't necessarily have to use it. You can pass a handler that doesn't
			    // consume any result.
			    .then((/* result ignored */) => doFourthThing())
			    // Always end the promise chain with a catch handler to avoid any
			    // unhandled rejections!
			    .catch((error) => console.error(error));
			  ```
			- Note that `() => x` is short for `() => { return x; }`.
	- What is a cleaner way to implement asynchronous, promise-based behaviour?
	  collapsed:: true
		- use [async functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
		- The [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) operator is used to wait for a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) and get its fulfillment value. It can only be used inside an [async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) or at the top level of a [module](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules).
		- ```
		  function resolveAfter2Seconds() {
		    return new Promise(resolve => {
		      setTimeout(() => {
		        resolve('resolved');
		      }, 2000);
		    });
		  }
		  
		  async function asyncCall() {
		    console.log('calling');
		    const result = await resolveAfter2Seconds();
		    console.log(result);
		    // Expected output: "resolved"
		  }
		  
		  asyncCall();
		  ```
		-
		-
	- What are the two easy ways of Error handling (for asynchronous operations)?
	  collapsed:: true
		- one general `catch` at the end of the promise chain
			- ```
			  doSomething()
			    .then((result) => doSomethingElse(result))
			    .then((newResult) => doThirdThing(newResult))
			    .then((finalResult) => console.log(`Got the final result: ${finalResult}`))
			    .catch(failureCallback);
			  ```
		- `try`/`catch` block in the [`async`/`await`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) syntax:
			- ```
			  async function foo() {
			    try {
			      const result = await doSomething();
			      const newResult = await doSomethingElse(result);
			      const finalResult = await doThirdThing(newResult);
			      console.log(`Got the final result: ${finalResult}`);
			    } catch (error) {
			      failureCallback(error);
			    }
			  }
			  ```
	- What are the two events that bubble to the top of the call stack because promises are rejected and not handled by any handler?
	  collapsed:: true
		- the type of the events is [`PromiseRejectionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent)
			- it has as members a [`promise`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/promise) property indicating the promise that was rejected,
			- and a [`reason`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/reason) property that provides the reason given for the promise to be rejected.
			- \rarr helpful for debugging issus and for **offering a fallback handling** for promises
		- [`unhandledrejection`](https://developer.mozilla.org/en-US/docs/Web/API/Window/unhandledrejection_event): Sent when a promise is rejected but there is no rejection handler available.
		- [`rejectionhandled`](https://developer.mozilla.org/en-US/docs/Web/API/Window/rejectionhandled_event): Sent when a handler is attached to a rejected promise that has already caused an `unhandledrejection` event.
	- How do you handle promise rejections in Node.js?
	  collapsed:: true
		- You capture unhandled rejections by adding a handler for the Node.js `unhandledRejection` event
			- ```
			  process.on("unhandledRejection", (reason, promise) => {
			    // Add code here to examine the "promise" and "reason" values
			  });
			  ```
	- How can you concurrently compose the execution of promises?
	  collapsed:: true
		- There are four [composition tools](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#promise_concurrency) for running asynchronous operations concurrently:
			- [`Promise.all()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all): Fulfills when **all** of the promises fulfill; rejects when **any** of the promises rejects.
			- [`Promise.allSettled()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled): Fulfills when **all** promises settle.
			- [`Promise.any()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/any): Fulfills when **any** of the promises fulfills; rejects when **all** of the promises reject.
			- [`Promise.race()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/race): Settles when **any** of the promises settles. In other words, fulfills when any of the promises fulfills; rejects when any of the promises rejects.
		- Example:
			- ```
			  Promise.all([func1(), func2(), func3()]).then(([result1, result2, result3]) => {
			    // use result1, result2 and result3
			  });
			  ```
	- How can you sequentially compose the execution of promises?
	  collapsed:: true
		- Write a promise chain out:
			- ```
			  Promise.resolve()
			    .then(func1)
			    .then(func2)
			    .then(func3)
			    .then((result3) => {
			      /* use result3 */
			    });
			  ```
		- [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) an array of asynchronous functions down to a promise chain
			- ```
			  [func1, func2, func3]
			    .reduce((p, f) => p.then(f), Promise.resolve())
			    .then((result3) => {
			      /* use result3 */
			    });
			  ```
		- do functional programming:
			- ```
			  const applyAsync = (acc, val) => acc.then(val);
			  const composeAsync =
			    (...funcs) =>
			    (x) =>
			      funcs.reduce(applyAsync, Promise.resolve(x));
			  ```
			- ```
			  const transformData = composeAsync(func1, func2, func3);
			  const result3 = transformData(data);
			  ```
		- more succinctly via async/await:
			- ```
			  let result;
			  for (const f of [func1, func2, func3]) {
			    result = await f(result);
			  }
			  /* use last result (i.e. result3) */
			  ```
		- Advice: Before you compose promises sequentially, consider if it's really necessary — it's always better to run promises concurrently so that they don't unnecessarily block each other unless one promise's execution depends on another's result.
	- How can you create a new Promise around an old callback API? Why would you do it?
	  collapsed:: true
		- A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) can be created from scratch using its [constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/Promise).
			- ```
			  const wait = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
			  
			  wait(10 * 1000)
			    .then(() => saySomething("10 seconds"))
			    .catch(failureCallback);
			  ```
		- Why do it:
			- Mixing old-style callbacks and promises is problematic. Programming errors or asynchronous code may fail and nothing catches it.
	- What is a state you should avoid when designing an API?
	  collapsed:: true
		- state of Zalgo (mixing synchronous and asynchronous callbacks [Designing APIs for Asynchrony](https://blog.izs.me/2013/08/designing-apis-for-asynchrony/))
		- BAD CODE:
			- ```
			  function doSomething(callback) {
			    if (Math.random() > 0.5) {
			      callback();
			    } else {
			      setTimeout(() => callback(), 1000);
			    }
			  }
			  
			  let value = 1;
			  doSomething(() => {
			    value = 2;
			  });
			  console.log(value); // 1 or 2?
			  ```
			-
	- What are some strong semantic guarantees both the API user and the API developer get (from Promises as a form of inversion of control)?
	  collapsed:: true
		- Callbacks added with [`then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) will never be invoked before the [completion of the current run](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop#run-to-completion) of the JavaScript event loop.
		- These callbacks will be invoked even if they were added *after* the success or failure of the asynchronous operation that the promise represents.
		- Multiple callbacks may be added by calling [`then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) several times. They will be invoked one after another, in the order in which they were inserted.
	- Are functions passed to `then()` called asynchronously or synchronously?
	  collapsed:: true
		- always asynchronously
		- Instead of running immediately, the passed-in function is put on a microtask queue, which means it runs later (only after the function which created it exits, and when the JavaScript execution stack is empty), just before control is returned to the event loop; i.e. pretty soon:
		- ```
		  const wait = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
		  
		  wait(0).then(() => console.log(4));
		  Promise.resolve()
		    .then(() => console.log(2))
		    .then(() => console.log(3));
		  
		  console.log(1); // 1, 2, 3, 4
		  ```
	- Are `setTimeout()` callbacks handled as microtasks or as task queues?
	  collapsed:: true
		- [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout) callbacks are handled as task queues.
		- for details see
			- [Microtask_guide](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide/In_depth#tasks_vs_microtasks)
			- [The event loop](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide/In_depth#tasks_vs_microtasks)
	- What is a possibility to debug unpredictable orders for firing promises and tasks?
	  collapsed:: true
		- use a microtask to check status or balance out your promises when promises are created conditionally
		- see the [microtask guide](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide) to learn more about how to use [`queueMicrotask()`](https://developer.mozilla.org/en-US/docs/Web/API/queueMicrotask) to enqueue a function as a microtask
- # 14. Iterators and generators
  collapsed:: true
	- What do you need to specify in a iterator?
	  collapsed:: true
		- [Iterator protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols#the_iterator_protocol): A `next()` method that returns an object with two properties
			- `value`: The next value in the iteration sequence
			- `done`: This is `true` if the last value in the sequence has already been consumed. If `value` is present alongside `done`, it is the iterator's return value.
		- Example:
			- ```
			  function makeRangeIterator(start = 0, end = Infinity, step = 1) {
			    let nextIndex = start;
			    let iterationCount = 0;
			    
			    const rangeIterator = {
			      next() {
			        let result;
			        if (nextIndex < end) {
			          result = { value: nextIndex, done: false };
			          nextIndex += step;
			          iterationCount++;
			          return result;
			        }
			        return { value: iterationCount, done: true };
			      },
			    };
			    return rangeIterator;
			  }
			  ```
			- ```
			  const it = makeRangeIterator(1, 10, 2);
			  
			  let result = it.next();
			  while (!result.done) {
			    console.log(result.value); // 1 3 5 7 9
			    result = it.next();
			  }
			  
			  console.log("Iterated over sequence of size:", result.value); // [5 numbers returned, that took interval in between: 0 to 10]
			  ```
		-
	- What are generator functions?
	  collapsed:: true
		- generator functions allow you to define an iterative algorithm by writing a single function whose execution is not continuous
			- Generator functions are written using the [`function*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*) syntax.
			- When called, generator functions do not initially execute their code. Instead, they return a special type of iterator, called a **Generator**.
			- When the iterator's `next()` method is called, the generator function's body is executed until the first [`yield`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield) expression, which specifies the value to be returned from the iterator or, with [`yield*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield*), delegates to another generator function
		- Example:
			- ```
			  function* makeRangeIterator(start = 0, end = Infinity, step = 1) {
			    let iterationCount = 0;
			    for (let i = start; i < end; i += step) {
			      iterationCount++;
			      yield i;
			    }
			    return iterationCount;
			  }
			  ```
	- What is an iterable object and what does it have?
	  collapsed:: true
		- An object is *iterable* if it defines its iteration behavior, such as what values are looped over in a [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) construct. Some built-in types, such as [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) or [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map), have a default iteration behavior, while other types (such as [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)) do not.
		- In order to be **iterable**, an object must implement the **@@iterator** method. This means that the object (or one of the objects up its [prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)) must have a property with a [`Symbol.iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator) key.
	- How many times can you iterate over an iterable?
	  collapsed:: true
		- Depends on implementation:
			- iterables which can iterate only once (such as Generators) customarily return `this` from their **@@iterator** method
			- iterables which can be iterated many times must return a new iterator on each invocation of **@@iterator**.
		- Example:
			- ```
			  function* makeIterator() {
			  yield 1;
			  yield 2;
			  }
			  
			  const it = makeIterator();
			  
			  for (const itItem of it) {
			    console.log(itItem);
			  }
			  
			  console.log(it[Symbol.iterator]() === it); // true
			  
			  // This example show us generator(iterator) is iterable object,
			  // which has the @@iterator method return the it (itself),
			  // and consequently, the it object can iterate only _once_.
			  
			  // If we change it's @@iterator method to a function/generator
			  // which returns a new iterator/generator object, (it)
			  // can iterate many times
			  
			  it[Symbol.iterator] = function* () {
			  yield 2;
			  yield 1;
			  };
			  ```
			-
	- How can you code user-defined iterables?
	  collapsed:: true
		- ```
		  const myIterable = {
		    *[Symbol.iterator]() {
		      yield 1;
		      yield 2;
		      yield 3;
		    },
		  };
		  
		  for (const value of myIterable) {
		    console.log(value);
		  }
		  // 1
		  // 2
		  // 3
		  
		  [...myIterable]; // [1, 2, 3]
		  ```
		-
	- What are some build-in iterables?
	  collapsed:: true
		- the following object have prototype objects with a [`Symbol.iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator) method:
			- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String),
			- [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array),
			- [`TypedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray),
			- [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) and
			- [`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
	- What syntaxes expect iterables?
	  collapsed:: true
		- the [`for-of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loops, [`yield*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield*).
		- ```
		  for (const value of ["a", "b", "c"]) {
		  console.log(value);
		  }
		  // "a"
		  // "b"
		  // "c"
		  - [..."abc"];
		  // ["a", "b", "c"]
		  - function* gen() {
		  yield* ["a", "b", "c"];
		  }
		  - gen().next();
		  // { value: "a", done: false }
		  - [a, b, c] = new Set(["a", "b", "c"]);
		  a;
		  // "a"
		  ```
	- How can you modify the internal state of a generator?
	  collapsed:: true
		- The [`next()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/next) method accepts a value, which can be used to modify the internal state of the generator. A value passed to `next()` will be received by `yield`.
		- A value passed to the *first* invocation of `next()` is always ignored
		- ```
		  function* fibonacci() {
		    let current = 0;
		    let next = 1;
		    while (true) {
		      const reset = yield current;
		      [current, next] = [next, next + current];
		      if (reset) {
		        current = 0;
		        next = 1;
		      }
		    }
		  }
		  
		  const sequence = fibonacci();
		  console.log(sequence.next().value); // 0
		  console.log(sequence.next().value); // 1
		  console.log(sequence.next().value); // 1
		  console.log(sequence.next().value); // 2
		  console.log(sequence.next().value); // 3
		  console.log(sequence.next().value); // 5
		  console.log(sequence.next().value); // 8
		  console.log(sequence.next(true).value); // 0
		  console.log(sequence.next().value); // 1
		  console.log(sequence.next().value); // 1
		  console.log(sequence.next().value); // 2
		  ```
		-
	- What happens when you throw a exception by calling [`throw()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/throw) inside a generator?
	  collapsed:: true
		- This exception will be thrown from the current suspended context of the generator, as if the `yield` that is currently suspended were instead a `throw value` statement.
	- Do generators have a `return()` method?
	  collapsed:: true
		- Yes, see [return(value)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/return). It returns the given value and finishes the generator itself.
- # 15. Meta programming
  collapsed:: true
	- What is a `Proxy` in JavaScript?
	  collapsed:: true
		- [Proxy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy) objects allow you to intercept certain operations and to implement custom behaviors.
	- How do you implement a `Proxy`?
	  collapsed:: true
		- The `Proxy` object defines a `target` (an empty object here) and a `handler` object, in which a `get` *trap* is implemented.
		- ```
		  const handler = {
		    get(target, name) {
		      return name in target ? target[name] : 42;
		    },
		  };
		  
		  const p = new Proxy({}, handler);
		  p.a = 1;
		  console.log(p.a, p.b); // 1, 42
		  ```
			- Additional examples are available on the [Proxy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy) reference page.
	- What is a handler, a trap, a target and an invariant?
	  collapsed:: true
		- [handler](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy): Placeholder object which contains traps.
		- traps: The methods that provide property access. (This is analogous to the concept of *traps* in operating systems.)
		- target: Object which the proxy virtualizes. It is often used as storage backend for the proxy. Invariants (semantics that remain unchanged) regarding object non-extensibility or non-configurable properties are verified against the target.
		- invariants: Semantics that remain unchanged when implementing custom operations are called *invariants*. If you violate the invariants of a handler, a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) will be thrown.
	- What are the available traps of the `Proxy` object?
	  collapsed:: true
		- see the [reference pages](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy) for detailed explanations and examples.
		- [`handler.getPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/getPrototypeOf)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.getPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)
				  [`Reflect.getPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getPrototypeOf)
				  [`__proto__`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/proto)
				  [`Object.prototype.isPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isPrototypeOf)
				  [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof)
			- **Invariants**:
				- `getPrototypeOf` method must return an object or `null`.
				- If target is not extensible, `Object.getPrototypeOf(proxy)` method must return the same value as `Object.getPrototypeOf(target)`.
		- [`handler.setPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/setPrototypeOf)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.setPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf)
				  [`Reflect.setPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/setPrototypeOf)
			- **Invariants:**
				- If target is not extensible, the `prototype` parameter must be the same value as `Object.getPrototypeOf(target)`.
		- [`handler.isExtensible()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/isExtensible)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.isExtensible()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible)
				  [`Reflect.isExtensible()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/isExtensible)
			- **Invariants:**
				- `Object.isExtensible(proxy)` must return the same value as `Object.isExtensible(target)`.
		- [`handler.preventExtensions()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/preventExtensions)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.preventExtensions()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions)
				  [`Reflect.preventExtensions()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/preventExtensions)
			- **Invariants:**
				- `Object.preventExtensions(proxy)` only returns `true` if `Object.isExtensible(proxy)` is `false`.
		- [`handler.getOwnPropertyDescriptor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/getOwnPropertyDescriptor)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.getOwnPropertyDescriptor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor)
				  [`Reflect.getOwnPropertyDescriptor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getOwnPropertyDescriptor)
			- **Invariants:**
				- `getOwnPropertyDescriptor` must return an object or `undefined`.
				- A property cannot be reported as non-existent if it exists as a non-configurable own property of target.
				- A property cannot be reported as non-existent if it exists as an own property of target and target is not extensible.
				- A property cannot be reported as existent if it does not exists as an own property of target and target is not extensible.
				- A property cannot be reported as non-configurable if it does not exist as an own property of target or if it exists as a configurable own property of target.
				- The result of `Object.getOwnPropertyDescriptor(target)` can be applied to target using `Object.defineProperty` and will not throw an exception.
		- [`handler.defineProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/defineProperty)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.defineProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)
				  [`Reflect.defineProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/defineProperty) |
			- **Invariants:**
				- A property cannot be added if target is not extensible.
				- A property cannot be added as (or modified to be) non-configurable if it does not exist as a non-configurable own property of target.
				- A property may not be non-configurable if a corresponding configurable property of target exists.
				- If a property has a corresponding target object property, then `Object.defineProperty(target, prop, descriptor)` will not throw an exception.
				- In strict mode, a `false` value returned from the `defineProperty` handler will throw a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception.
		- [`handler.has()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/has)
		  collapsed:: true
			- **Interceptions**:
				- Property query: `foo in proxy`
				- Inherited property query: `foo in Object.create(proxy)`
				- [`Reflect.has()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/has)
			- **Invariants:**
				- A property cannot be reported as non-existent, if it exists as a non-configurable own property of target.
				- A property cannot be reported as non-existent if it exists as an own property of target and target is not extensible.
		- [`handler.get()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/get)
		  collapsed:: true
			- **Interceptions**:
				- Property access: `proxy[foo]` `proxy.bar`
				- Inherited property access: `Object.create(proxy)[foo]`
				- [`Reflect.get()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/get)
			- **Invariants:**
				- The value reported for a property must be the same as the value of the corresponding target property if target's property is a non-writable, non-configurable data property.
				- The value reported for a property must be `undefined` if the corresponding target property is non-configurable accessor property that has undefined as its `[[Get]]` attribute.
		- [`handler.set()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/set)
		  collapsed:: true
			- **Interceptions**:
				- Property assignment: `proxy[foo] = bar` `proxy.foo = bar`
				- Inherited property assignment: `Object.create(proxy)[foo] = bar`
				- [`Reflect.set()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/set)
			- **Invariants:**
				- Cannot change the value of a property to be different from the value of the corresponding target property if the corresponding target property is a non-writable, non-configurable data property.
				- Cannot set the value of a property if the corresponding target property is a non-configurable accessor property that has `undefined` as its `[[Set]]` attribute.
				- In strict mode, a `false` return value from the `set` handler will throw a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception.
		- [`handler.deleteProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/deleteProperty)
		  collapsed:: true
			- **Interceptions**:
				- Property deletion: `delete proxy[foo]` `delete proxy.foo`
				- [`Reflect.deleteProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/deleteProperty)
			- **Invariants:**
				- A property cannot be deleted if it exists as a non-configurable own property of `target`.
		- [`handler.ownKeys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/ownKeys)
		  collapsed:: true
			- **Interceptions**:
				- [`Object.getOwnPropertyNames()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames)
				- [`Object.getOwnPropertySymbols()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertySymbols)
				- [`Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
				- [`Reflect.ownKeys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/ownKeys)
			- **Invariants:**
				- The result of `ownKeys` is a List.
				- The Type of each result List element is either [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) or [`Symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol).
				- The result List must contain the keys of all non-configurable own properties of target.
				- If the target object is not extensible, then the result List must contain all the keys of the own properties of target and no other values.
		- [`handler.apply()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/apply)
		  collapsed:: true
			- **Interceptions**:
				- `proxy(..args)`
				- [`Function.prototype.apply()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) and [`Function.prototype.call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
				- [`Reflect.apply()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/apply)
			- **Invariants:**
				- There are no invariants for the handler.apply method.
		- [`handler.construct()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/construct)
		  collapsed:: true
			- **Interceptions**:
				- `new proxy(...args)`
				  [`Reflect.construct()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/construct)
			- **Invariants:**
				- The result must be an `Object`.
	- What is a revocable `Proxy`?
	  collapsed:: true
		- [`Proxy.revocable()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/revocable) is used to create a revocable `Proxy` object. the proxy can be revoked via the function `revoke` and switches the proxy off.
		- Afterwards, any operation on the proxy leads to a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).
		- ```
		  const revocable = Proxy.revocable(
		    {},
		    {
		      get(target, name) {
		        return `[[${name}]]`;
		      },
		    },
		  );
		  const proxy = revocable.proxy;
		  console.log(proxy.foo); // "[[foo]]"
		  
		  revocable.revoke();
		  
		  console.log(proxy.foo); // TypeError: Cannot perform 'get' on a proxy that has been revoked
		  proxy.foo = 1; // TypeError: Cannot perform 'set' on a proxy that has been revoked
		  delete proxy.foo; // TypeError: Cannot perform 'deleteProperty' on a proxy that has been revoked
		  console.log(typeof proxy); // "object", typeof doesn't trigger any trap
		  ```
	- What does`Reflection` do?
	  collapsed:: true
		- [`Reflect`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect) is a built-in object that provides methods for interceptable JavaScript operations. The methods are the same as those of the [proxy handlers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy).
		- `Reflect` is not a function object.
		- `Reflect` helps with forwarding default operations from the handler to the `target`.
		- Example: With [`Reflect.has()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/has) you get the [`in` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) as a function:
		  collapsed:: true
			- ```
			  Reflect.has(Object, "assign"); // true
			  ```
	- What a two good practices that use `Reflection`?
	  collapsed:: true
		- Easier to understand `apply()` function:
			- ```
			  Function.prototype.apply.call(Math.floor, undefined, [1.75]);
			  
			  Reflect.apply(Math.floor, undefined, [1.75]); // 1
			  Reflect.apply(String.fromCharCode, undefined, [104, 101, 108, 108, 111]); // "hello"
			  Reflect.apply(RegExp.prototype.exec, /ab/, ["confabulation"]).index; // 4
			  Reflect.apply("".charAt, "ponies", [3]); // "i"
			  ```
		- Checking if property definition has been successful
			- With [`Object.defineProperty`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty), which returns an object if successful, or throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) otherwise, you would use a [`try...catch`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) block to catch any error that occurred while defining a property.
			- Because [`Reflect.defineProperty`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/defineProperty) returns a Boolean success status, you can just use an [`if...else`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) block here:
			  ```
			  if (Reflect.defineProperty(target, property, attributes)) {
			    // success
			  } else {
			    // failure
			  }
			  ```
- # 16. JavaScript modules
  collapsed:: true
	- What is the recommended file extension for JavaScript objects?
	  collapsed:: true
		- `.mjs` - see [V8's documentation ](https://v8.dev/features/modules#mjs)
		- Reasons:
			- It is good for clarity, i.e. it makes it clear which files are modules, and which are regular JavaScript.
			- It ensures that your module files are parsed as a module by runtimes such as [Node.js](https://nodejs.org/api/esm.html#esm_enabling), and build tools such as [Babel](https://babeljs.io/docs/en/options#sourcetype).
		- Because of combability issues`.js` is common
	- How do you export a module?
	  collapsed:: true
		- use the [export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) statement
		  ```
		  export const name = "square";
		  
		  export function draw(ctx, length, x, y, color) {
		    ctx.fillStyle = color;
		    ctx.fillRect(x, y, length, length);
		    return { length, x, y, color };
		  }
		  ```
	- How do you import a module?
	  collapsed:: true
		- You use the [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) statement, followed by a comma-separated list of the features you want to import wrapped in curly braces, followed by the keyword `from`, followed by the *module specifier*.
		  ```
		  import { name, draw, reportArea, reportPerimeter } from "./modules/square.js";
		  ```
		- You can see such lines in action in [`main.js`](https://github.com/mdn/js-examples/blob/master/module-examples/basic-modules/main.js).
	- How do you import modules using import maps?
	  collapsed:: true
		- The import map is defined using a [JSON object](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script/type/importmap#import_map_json_representation) inside a `<script>` element with the `type` attribute set to [`importmap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script/type/importmap).
		- Only one import map per document
		- ```
		  <script type="importmap">
		    {
		      "imports": {
		        "shapes": "./shapes/square.js",
		        "shapes/square": "./modules/shapes/square.js",
		        "https://example.com/shapes/": "/shapes/square/",
		        "https://example.com/shapes/square.js": "./shapes/square.js",
		        "../shapes/square": "./shapes/square.js"
		      }
		    }
		  </script>
		  ```
		- ```
		  // Bare module names as module specifiers
		  import { name as squareNameOne } from "shapes";
		  import { name as squareNameTwo } from "shapes/square";
		  
		  // Remap a URL to another URL
		  import { name as squareNameThree } from "https://example.com/shapes/moduleshapes/square.js";
		  
		  // Remap a URL as a prefix ( https://example.com/shapes/)
		  import { name as squareNameFour } from "https://example.com/shapes/square.js";
		  ```
		-
	- How can you check if `importmap` is supported?
	  collapsed:: true
		- use the [HTMLScriptElement.supports()](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement/supports) static method
		  ```
		  if (HTMLScriptElement.supports?.("importmap")) {
		    console.log("Browser supports import maps.");
		  }
		  ```
	- How can you import a module using a bare name?
	  collapsed:: true
		- you need an import map, which provides the information needed by the browser to resolve module specifiers to URLs
			- (JavaScript will throw a `TypeError` if it attempts to import a module specifier that can't be resolved to a module location).
		- ```
		  <script type="importmap">
		    {
		      "imports": {
		        "square": "./shapes/square.js"
		      }
		    }
		  </script>
		  ```
		- ```
		  import { name as squareName, draw } from "square";
		  ```
		-
		-
	- How can you remap module paths?
	  collapsed:: true
		- Use forward slash `/` for packages of modules
			- ```
			  {
			    "imports": {
			      "lodash": "/node_modules/lodash-es/lodash.js",
			      "lodash/": "/node_modules/lodash-es/"
			    }
			  }
			  ```
			- ```
			  import _ from "lodash";
			  import fp from "lodash/fp.js";
			  ```
		- Use general url remapping
			- A module specifier key doesn't have to be path — it can also be an absolute URL (or a URL-like relative path like `./`, `../`, `/`).
			- This may be useful if you want to remap a module that has absolute paths to a resource with your own local resources.
			- ```
			  {
			    "imports": {
			      "https://www.unpkg.com/moment/": "/node_modules/moment/"
			    }
			  }
			  ```
	- How does a scoped module import work?
	  collapsed:: true
		- You implement this with the `scopes` key, which allows you to provide module specifier maps that will be used depending on the path of the script performing the import. The example below demonstrates this
		- ```
		  {
		    "imports": {
		      "coolmodule": "/node_modules/coolmodule/index.js"
		    },
		    "scopes": {
		      "/node_modules/dependency/": {
		        "coolmodule": "/node_modules/some/other/location/coolmodule/index.js"
		      }
		    }
		  }
		  ```
			- With this mapping, if a script with an URL that contains `/node_modules/dependency/` imports `coolmodule`, the version in `/node_modules/some/other/location/coolmodule/index.js` will be used.
			- The map in `imports` is used as a fallback if there is no matching scope in the scoped map, or the matching scopes don't contain a matching specifier. For example, if `coolmodule` is imported from a script with a non-matching scope path, then the module specifier map in `imports` will be used instead, mapping to the version in `/node_modules/coolmodule/index.js`.
		-
	- How can you improve caching by mapping away hashed filenames?
	  collapsed:: true
		- Rather than depending on specific hashed filenames, applications and scripts instead depend on an un-hashed version of the module name (address).
		- ```
		  {
		    "imports": {
		      "main_script": "/node/srcs/application-fg7744e1b.js",
		      "dependency_script": "/node/srcs/dependency-3qn7e4b1q.js"
		    }
		  }
		  ```
			- If `dependency_script` changes, then its hash contained in the file name changes as well. In this case, we **only need to update the import map** to reflect the changed name of the module. We don't have to update the source of any JavaScript code that depends on it, because the specifier in the import statement does not change.
	- How do you apply a module to a HTML file?
	  collapsed:: true
		- you need to include `type="module"` in the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element, to declare this script as a module.
			- ```
			  <script type="module" src="main.js"></script>
			  ```
		- Alternatively, you can also embed the module's script directly into the HTML file by placing the JavaScript code within the body of the `<script>` element:
			- ```
			  <script type="module">
			    /* JavaScript module code here */
			  </script>
			  ```
			- The script into which you import the module features basically acts as the top-level module.
	- What are differences between modules and standard scripts?
	  collapsed:: true
		- You can only use `import` and `export` statements inside modules, not regular scripts.
		- You need to pay attention to local testing — if you try to load the HTML file locally (i.e. with a `file://` URL), you'll run into **CORS errors** due to JavaScript module security requirements. You need to do your testing through a server.
		- Also, note that you might get different behaviour from sections of script defined inside modules as opposed to in standard scripts. This is because modules use [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) automatically.
		- There is no need to use the `defer` attribute (see [`<script>` attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attributes)) when loading a module script; modules are deferred automatically.
		- Modules are only executed once, even if they have been referenced in multiple `<script>` tags.
		- Last but not least, let's make this clear — module features are imported into the scope of a single script — they aren't available in the global scope. Therefore, you will only be able to access imported features in the script they are imported into, and you won't be able to access them from the JavaScript console, for example. You'll still get syntax errors shown in the DevTools, but you'll not be able to use some of the debugging techniques you might have expected to use.
	- Are globally defined variables available in modules?
	  collapsed:: true
		- Yes:
		  ```
		  <!DOCTYPE html>
		  <html lang="en-US">
		    <head>
		      <meta charset="UTF-8" />
		      <title></title>
		      <link rel="stylesheet" href="" />
		    </head>
		    <body>
		      <div id="main"></div>
		      <script>
		        // A var statement creates a global variable.
		        var text = "Hello";
		      </script>
		      <script type="module" src="./render.js"></script>
		    </body>
		  </html>
		  ```
		- ```
		  /* render.js */
		  document.getElementById("main").innerText = text;
		  ```
	- What is the difference between default exports and exorts?
	  collapsed:: true
		- **default export** — this is designed to make it easy to have a default function provided by a module, and also helps JavaScript modules to interoperate with existing CommonJS and AMD module systems (as explained nicely in [ES6 In Depth: Modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/) by Jason Orendorff; search for "Default exports").
			- ```
			  export default randomSquare;
			  ```
			- ```
			  export default function (ctx) {
			    // …
			  }
			  ```
			- ```
			  import randomSquare from "./modules/square.js";
			  ```
		- it is just a **shorthand for**:
			- ```
			  import { default as randomSquare } from "./modules/square.js";
			  ```
	- What are three possibilities to avoid conflicting names (from different moduls)?
	  collapsed:: true
		- [Renaming imports and exports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#renaming_imports_and_exports)
		- [Creating a module object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#creating_a_module_object): Use the follow syntax
			- ```
			  import * as Module from "./modules/module.js";
			  ```
			- ```
			  Module.function1();
			  Module.function2();
			  ```
		- [Modules and classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#modules_and_classes): export a class
			- ```
			  export { Square };
			  ```
			- ```
			  import { Square } from "./modules/square.js";
			  ```
	- How can you aggregate moduls?
	  collapsed:: true
		- Syntax:
			- ```
			  export * from "x.js";
			  export { name } from "x.js";
			  ```
		- Example:
			- modul structure:
			  ```
			  modules/
			    canvas.js
			    shapes.js
			    shapes/
			      circle.js
			      square.js
			      triangle.js
			  ```
			- in [shapes.js](https://github.com/mdn/js-examples/blob/master/module-examples/module-aggregation/modules/shapes.js)
			  ```
			  export { Square } from "./shapes/square.js";
			  export { Triangle } from "./shapes/triangle.js";
			  export { Circle } from "./shapes/circle.js";
			  ```
				- The exports referenced in `shapes.js` basically get redirected through the file and don't really exist there, so you won't be able to write any useful related code inside the same file.
				- in the `main.js`:
				  ```
				  import { Square, Circle, Triangle } from "./modules/shapes.js";
				  ```
			-
		-
	- Where and how can you dynamically load modules?
	  collapsed:: true
		- use [`import()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import), assing it the path to the module as a parameter. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills with a module object (see [Creating a module object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#creating_a_module_object)) giving you access to that object's exports. For example:
			- ```
			  import("./modules/myModule.js").then((module) => {
			    // Do something with the module.
			  });
			  ```
		- **Note:** Dynamic import is permitted in the browser main thread, and in shared and dedicated workers. However `import()` will throw if called in a service worker or worklet.
		- dynamic imports is that they are always available, even in script environments.
		  ```
		  <script>
		    import("./modules/square.js").then((module) => {
		      // Do something with the module.
		    });
		    // Other code that operates on the global scope and is not
		    // ready to be refactored into modules yet.
		    var btn = document.querySelector(".square");
		  </script>
		  ```
	- Does a cyclic imports cause a error and how do you avoid it?
	  collapsed:: true
		- Cyclic imports don't always fail.
			- The imported variable's value is only retrieved when the variable is actually used (hence allowing [live bindings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import#imported_values_can_only_be_modified_by_the_exporter)), and only if the variable remains uninitialized at that time will a [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_access_lexical_declaration_before_init) be thrown.
		- You should usually avoid cyclic imports in your project, because they make your code more error-prone. Some common cycle-elimination techniques are:
			- Merge the two modules into one.
			- Move the shared code into a third module.
			- Move some code from one module to the other.
		- However, cyclic imports can also occur if the libraries depend on each other, which is harder to fix
	- How do you author "isomorphic" modules? (cross-platform for web browser and node.js)
	  collapsed:: true
		- Separate your modules into **"core" and "binding"**.
		  collapsed:: true
			- For the "core", focus on pure JavaScript logic like computing the hash, without any DOM, network, filesystem access, and expose utility functions.
			- For the "binding" part, you can read from and write to the global context.
			- For example, the "browser binding" may choose to read the value from an input box, while the "Node binding" may read it from `process.env`, but values read from either place will be piped to the same core function and handled in the same way. The core can be imported in every environment and used in the same way, while only the binding, which is usually lightweight, needs to be platform-specific.
		- **Detect whether a particular global exists before using it**.
		  collapsed:: true
			- For example, if you test that `typeof window === "undefined"`, you know that you are probably in a Node.js environment, and should not read DOM.
			- ```
			  // myModule.js
			  let password;
			  if (typeof process !== "undefined") {
			    // We are running in Node.js; read it from `process.env`
			    password = process.env.PASSWORD;
			  } else if (typeof window !== "undefined") {
			    // We are running in the browser; read it from the input box
			    password = document.getElementById("password").value;
			  }
			  ```
			- This is preferable if the two branches actually end up with the same behavior ("isomorphic"). If it's impossible to provide the same functionality, or if doing so involves loading significant amounts of code while a large part remains unused, better use different "bindings" instead.
		- Use a polyfill to **provide a fallback for missing features**.
		  collapsed:: true
			- For example, if you want to use the [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) function, which is only supported in Node.js since v18, you can use a similar API, like the one provided by [`node-fetch`](https://www.npmjs.com/package/node-fetch). You can do so conditionally through dynamic imports:
			- ```
			  // myModule.js
			  if (typeof fetch === "undefined") {
			  // We are running in Node.js; use node-fetch
			  globalThis.fetch = (await import("node-fetch")).default;
			  }
			  // …
			  ```
				- The [`globalThis`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/globalThis) variable is a global object that is available in every environment and is useful if you want to read or create global variables within modules.
	- What are some troubleshooting tips?
	  collapsed:: true
		- We mentioned this before, but to reiterate: `.mjs` files need to be loaded with a MIME-type of `text/javascript` (or another JavaScript-compatible MIME-type, but `text/javascript` is recommended), otherwise you'll get a strict MIME type checking error like "The server responded with a non-JavaScript MIME type".
		- If you try to load the HTML file locally (i.e. with a `file://` URL), you'll run into CORS errors due to JavaScript module security requirements. You need to do your testing through a server. GitHub pages is ideal as it also serves `.mjs` files with the correct MIME type.
		- Because `.mjs` is a non-standard file extension, some operating systems might not recognize it, or try to replace it with something else. For example, we found that macOS was silently adding on `.js` to the end of `.mjs` files and then automatically hiding the file extension. So all of our files were actually coming out as `x.mjs.js`. Once we turned off automatically hiding file extensions, and trained it to accept `.mjs`, it was OK.