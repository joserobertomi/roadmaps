# JS variables

## Declaring

```js
let user = 'John';
let age = 25;
let message = 'Hello';
```

> -> **var instead of let**
    In older scripts, you may also find another keyword: var instead of let: `var message = 'Hello';`
    The var keyword is almost the same as let. It also declares a variable but in a slightly different, “old-school” way.
    There are subtle differences between let and var, but they do not matter to us yet. We’ll cover them in detail in the chapter The old "var"

- Variables are camel case
- Variables cant start with numbers and in middle have special chars
- Non-Latin letters are allowed, but not recommended
- Reserved words [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords]

```js
const myBirthday = '18.04.1982';
myBirthday = '01.01.2001'; // error, can't reassign the constant!
```

- Constants are record in `UPPER CASE`
  - There is a widespread practice to use constants as aliases for difficult-to-remember values that are known before execution.

### Summary

We can declare variables to store data by using the var, let, or const keywords.

- `let` – is a modern variable declaration.
- `var` – is an old-school variable declaration. Normally we don’t use it at all, but we’ll cover subtle differences from let in the chapter The old "var", just in case you need them.
- `const` – is like let, but the value of the variable can’t be changed.

Variables should be named in a way that allows us to easily understand what’s inside them.

## Hoisting

Hoisting is JavaScript’s behavior of moving **declarations** to the top of their scope during the compilation phase.
But **only the declarations are hoisted, not the initializations**. [Great resource](https://www.youtube.com/watch?v=EvfRXyKa_GI&ab_channel=WebDevSimplified)

### Example with `var`

```js
console.log(message); // undefined
var message = 'Hello';
```

- The code above looks like it should throw an error, but instead it prints `undefined`.
- That’s because `var` declarations are hoisted to the top and initialized with `undefined`.

Internally, it’s as if the code was:

```js
var message; // declaration hoisted
console.log(message); // undefined
message = 'Hello'; // initialization stays in place
```

### Example with `let` and `const`

```js
console.log(user); // ❌ ReferenceError
let user = 'John';
```

- `let` and `const` are **also hoisted**, but they stay in a **temporal dead zone (TDZ)** until the actual declaration line.
- You can’t access them before their declaration, which avoids the confusing `undefined` behavior of `var`.

### Function Hoisting

- **Function declarations** are fully hoisted, so you can call them before they are defined:

```js
sayHi(); // works!
function sayHi() {
  console.log('Hello');
}
```

- **Function expressions** (assigned to `let`, `const`, or `var`) behave like variables:

  - If declared with `var`, they’re hoisted but initialized with `undefined`.
  - If declared with `let`/`const`, they’re hoisted but stuck in the **TDZ**.

✅ **Summary of Hoisting Rules**

- `var` → hoisted, initialized with `undefined`.
- `let` / `const` → hoisted, but **TDZ** until declared (accessing early → ReferenceError).
- `function declarations` → hoisted completely.
- `function expressions` → behave like variables (`var` → undefined, `let`/`const` → TDZ).
