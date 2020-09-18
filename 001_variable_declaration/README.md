# Variable Declaration

In the beginning the was the humble `var` declaration and it went like this `var a = 1;`.

Can anyone tell me how we can access `var a`? (`a`, `window.a`) Anything declared in the global scope is attached to it.

Can we assign a value to a variable without the variable declaration? Yes `b = 2;`. In an effort to help us JavaScript will create `b` and assign the value `2` to it, What scope will it be in? (Global) Keep this in mind for later.

Is this `var c = 3;` a single statement? No `var c;` (automatically assigned the special value `undefined`) is one statement and `c = 3;` is the second. When the JavaScript interpreter reads your code it divides this into two statements and lifts the variable declaration to the top of its scope. This is known as Hoisting and while mostly "solved" by `let` and `const` it's an important concept to be aware of.

Special JavaScript values undeclared. JavaScript will throw an error (in strict mode/most modern environments) if we try to reference a var that has not been declared. But watch out. As in example b assigning a value to an undeclared variable creates it in the global scope and operators like `typeof` will tell us it's undefined.

Undefined is the default value assigned to a variable if there is no immediate value assingment with `=`. A `const` can not be undefined.

Variables can be redeclared

`let` and const are hoisted but not initialized, `var` is initialized with undefined.

`let` can be re-assigned values but not redeclared

`const` cant be re-declared or re-assigned but the can be mutated!

## Further Reading

[Var, Let, and Const – What's the Difference?](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/#:~:text=Hoisting%20of%20const%20Just%20like%20let%2C%20const%20declarations,scoped%20while%20let%20and%20const%20are%20block%20scoped.)
