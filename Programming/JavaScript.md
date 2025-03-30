#javascript #programming #english
## Basic Syntax 

**1. Comments:**

- Start with `//` for single-line comments and `/* ... */` for multi-line comments.
- They help explain your code but are ignor ed by the computer.
```javascript
//Comment

/*
Multi line comment
*/
```

**2. Statements:**

- Each line of code ending with a `;` is a statement.
- Examples: assigning values, calling functions, printing output.

**3. Data Types:**

- Represent the kind of information a variable holds.
- Common types include numbers, strings (text), booleans (true/false), and objects.

**4. Variables:** [[JavaScript Variables]]

- Store data using names declared with `let`, `const`, or `var` (avoid `var` for modern JS).
- `let` and `const` control scope and reassignment.
```javascript
let x = 5;
const y = 6;

let z = x + y; // z will be 10
```

**5. Operators:**

- Perform calculations or comparisons on data.
- Math operators (+, -, \*, /), comparison operators (\==, !=, <, >), logical operators (&&, ||, !).

**6. Expressions:**

- Combine variables, operators, and values to produce a result.
- Example: `let result = 5 + 3 * 2;`

**7. Control Flow:**

- Decides which parts of code to execute based on conditions.
- `if` statements, `else if`, `else`, loops (for, while, do-while).

**8. Functions:**

- Blocks of reusable code that perform specific tasks.
- Defined with `function name(parameters) { ... }`.
- Can return values using `return`.

**9. Objects:**

- Collections of key-value pairs (properties) representing real-world entities.
- Used for structuring complex data and interactions.

JavaScript
```javascript
// Function to greet someone//
function greet(name) {
  // Concatenate a greeting with the name
  let message = "Hello, " + name + "!";
  // Print the message to the console
  console.log(message);
}

// Call the greet function with a name
greet("Alice");
```

## Leetcode

### Exercise 1

Write a function `createHelloWorld`. It should return a new function that always returns `"Hello World"`.

```javascript
function createHelloWorld() {
    function innerFunction() {
        return"Hello World"
        }
        return innerFunction
}
```
### Overview
  
  This question is intended as an introduction to JavaScript functions. This editorial willcover their syntax and topics like _**closures**_ and _**higher-order functions**_.

##### Basic Syntax

The syntax is:

```javascript
function f(a, b) {
    const sum = a + b;
    return sum;
}
console.log(f(3, 4)); // 7
```

In this example, `f` is the name of the function. `(a, b)` are the arguments. You can write any logic in the body and finally `return` a result. You are allowed to return nothing, and it will instead implicitly return `undefined`.

##### Anonymous Function

You can optionally exclude the name of the function after the `function` keyword.

```javascript
var f = function(a, b) {
    const sum = a + b;
    return sum;
}
console.log(f(3, 4)); // 7
```

##### Immediately Invoked Function Expression (IIFE)

You can create a function and immediately execute it in Javascript.

```javascript
const result = (function(a, b) {
    const sum = a + b;
    return sum;
})(3, 4);
console.log(result); // 7
```

Why would you write code like this? It gives you the opportunity to _**encapsulate**_ a variable within a new _**scope**_. For example, another developer can immediately see that `sum` can't be used anywhere outside the function body.

##### Functions Within Functions

A powerful feature of JavaScript is you can actually create functions within other functions and even return them!

```javascript
function createFunction() {
    function f(a, b) {
        const sum = a + b;
        return sum;
    }
    return f;
}
const f = createFunction();
console.log(f(3, 4)); // 7
```

In this example, `createFunction()` returns a new function. Then that function can be used as normal.

##### Function Hoisting

JavaScript has a feature called _**hoisting**_ where a function can sometimes be used before it is initialized. You can only do this if you declare functions with the `function` syntax.

```javascript
function createFunction() {
    return f;
    function f(a, b) {
        const sum = a + b;
        return sum;
    }
}
const f = createFunction();
console.log(f(3, 4)); // 7
```

In this example, the function is returned before it is initialized. Although it is valid syntax, it is sometimes considered bad practice as it can reduce readability.

##### Closures

An important topic in JavaScript is the concept of _**closures**_. When a function is created, it has access to a reference to all the variables declared around it, also known as it's _**lexical environment**_. The combination of the function and its enviroment is called a _**closure**_. This is a powerful and often used feature of the language.

```javascript
function createAdder(a) {
    function f(b) {
        const sum = a + b;
        return sum;
    }
    return f;
}
const f = createAdder(3);
console.log(f(4)); // 7
```

In this example, `createAdder` passes the first parameter `a` and the inner function has access to it. This way, `createAdder` serves as a factory of new functions, with each returned function having different behavior.

#### Arrow Syntax

The other common way to declare functions is with arrow syntax. In fact, on many projects, it is the preferred syntax.

##### Basic Syntax

```javascript
const f = (a, b) => {
    const sum = a + b;
    return sum;
};
console.log(f(3, 4)); // 7
```

In this example, `f` is the name of the function. `(a, b)` are the arguments. You can write any logic in the body and finally `return` a result. You are allowed to return nothing, and it will instead implicitly return `undefined`.

##### Omit Return

If you can write the code in a single line, you can omit the `return` keyword. This can result in very short code.

```javascript
const f = (a, b) => a + b;
console.log(f(3, 4)); // 7
```

##### Differences

There are 3 major differences between arrow syntax and function syntax.

1. More minimalistic syntax. This is especially true for anonymous functions and single-line functions. For this reason, this way is generally preferred when passing short anonymous functions to other functions.
2. No automatic hoisting. You are only allowed to use the function after it was declared. This is generally considered a good thing for readability.
3. Can't be bound to `this`, `super`, and `arguments` or be used as a constructor. These are all complex topics in themselves but the basic takeaway should be that arrow functions are simpler in their feature set. You can read more about these differences [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions).

The choice of arrow syntax versus function syntax is primarily down to preference and your project's stylistic standards.

#### Rest Arguments

You can use _**rest**_ syntax to access all the passed arguments as an array. This isn't necessary for this problem, but it will be a critical concept for many problems. You can read more about `...` syntax [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax).

##### Basic Syntax

The syntax is:

```javascript
function f(...args) {
    const sum = args[0] + args[1];
    return sum;
}
console.log(f(3, 4)); // 7
```

In this example the variable `args` is `[3, 4]`.

##### Why

It may not be immediately obvious why you would use this syntax because you can always just pass an array and get the same result.

The primary use-case is for creating generic factory functions that accept any function as input and return a new version of the function with some specific modification.

By the way, a function that accepts a function and/or returns a function is called a _**higher-order function**_, and they are very common in JavaScript.

For example, you can create a logged function factory:

```javascript
function log(inputFunction) {
    return function(...args) {
        console.log("Input", args);
        const result = inputFunction(...args);
        console.log("Output", result);
        return result;
    }
}
const f = log((a, b) => a + b);
f(1, 2); // Logs: Input [1, 2] Output 3
```

### Exercise 2

```javascript

var createCounter = function(n) {
    let counter = n - 1;
    return function() {
        counter++;
        return counter;
    };
};
```

### Overview

This question is intended as an introduction to _**closures**_. In JavaScript, functions have a reference to all variables declared in the same scope as well as any outer scopes. These scopes are known as the function's _**lexical environment**_. The combination of the function and it's environment is known as a _**closure**_.

#### Closure Example

In Javascript, you can declare functions within other functions and return them. The inner function has access to any variables declared above it.

```javascript
function createAdder(a) {
  return function add(b) {
    const sum = a + b;
    return sum;
  }
}
const addTo2 = createAdder(2);
addTo2(5); // 7
```

The inner function `add` has access to `a`. This allows the outer function to serve as a factory of new functions, each with different behavior.

#### Closures Versus Classes

You may notice that in the above example `createAdder` is very similar to a class constructor.

```javascript
class Adder {
  constructor(a) {
     this.a = a;
  }

  add(b) {
    const sum = this.a + b;
    return sum;
  }
}
const addTo2 = new Adder(2);
addTo2.add(5); // 7
```

Besides differences in syntax, both code examples essentially serve the same purpose. They both allow you to pass in some state in a "constructor" and have "methods" that access this state.

One key difference is that closures allow for true _**encapsulation**_. In the class example, there is nothing stopping you from writing `addTo2.a = 3;` and breaking it's expected behavior. However, in the closure example, it is theoretically impossible to access `a`. Note that as of 2022, true encapsulation is achievable in classes with [# prefix syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Private_class_fields).

Another difference is how the functions are stored in memory. If you create many instances of a class, each instance stores a single reference to the _**prototype object**_ where all the methods are stored. Whereas for closures, all the "methods" are generated and a "copy" of each is stored in memory each time the outer function is called. For this reason, classes can be more efficient, particularly in the case where there are many methods.

Unlike in languages like Java, you will tend to see code written with functions rather than with classes. But since JavaScript is a multi-paradigm language, it will depend on the particular project you are working on.