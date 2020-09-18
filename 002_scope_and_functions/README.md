# Scope

Every JS environment has a global scope. In the browser you can access it with `window` and in node `global`. This scope carries with it everything we need to run our programs but JavaScript environments are not all the same. For instance both node and browser have types; window.Array, global.Array. The browser provides events and the DOM api (and others) node does not. Node provides Buffer, File System access (and a lot more) where the browser does not. And both implement timers even though timers are not part of JavaScript.

We'll be discussing scope using the browser but what we learn here is applicable to Node. The important difference between the browser and node is that in node files create scopes and exports expose a public interface. In the window the script tag access the global scope directly.

## The global
Window is available and it has good things. (`a`, `myfunc`)

Anything we do here adds to variables to the global scope.

## Classic example
This is good because without this scope functions couldn't reference one another or variables. But it's also bad because we can over write portions of the program and change state in unpredictable ways. (classic example)

The example is a bit silly but it illustrates a point. Over time applications grow in complexity and maintaining all state and function references in the global scope would eventually lead to unmaintainable code.

## Functions are the primary way to create scopes
Functions create new scopes in JavaScript. A function's scope is fleeting. When we invoke a function in javascript that function goes on to the call stack. It creates its own environment in which to run and after running to completion the function pops off the call stack and thrown away.

## Local environment
Since the parameters passed to a function and the variables created within it are created locally when the function is being executed and then destroyed after the function is done executing. The only way to get a value out of a function is with the return statement.

A function's scope is "protected" from the outside. When we run `sum` the global area is not able to access `z`. And yet...

## A function can access ancestor scopes
A function can access an ancestor scope, as far as you'd like to go

__I hope I've convinced all of you that there is no way to access a function's environment from the outside world and that it's environment is destroyed when it's done executing.__

## Other scope rules
ES6 introduced block scope. A block scope is any statement that contains `{}` (`function`, `for`, `if`, `while,` `try, catch` & etc.). `let` and `const` respect that scope. That means a let or const created in a block `{}` can't be directly accessed from outside of the block.

Just like a functions scope is protected from the outside world.

## Further Reading

[Scope and Closure, Kyle Simpson](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/scope-closures)

[8.1 Lexical Environments, ECMAScript 2020 Language Specification](https://www.ecma-international.org/ecma-262/11.0/index.html#sec-lexical-environments)

[The Revealing Module Pattern, Addy Osmani, Learning JavaScript Design Patterns]
(https://addyosmani.com/resources/essentialjsdesignpatterns/book/#revealingmodulepatternjavascript)
